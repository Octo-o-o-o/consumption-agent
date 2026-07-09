# Part 6 · Architecture Notes

> A sketch, offered as a proposal to the community rather than a finished design: the render function generalized, the semantic middle layer that makes per-person rendering economically sane, when to sit directly on raw data versus pair with professional producers, and a draft artifact contract.
> These are engineering hypotheses (○) unless marked otherwise. As of 2026-07-09.

## 1. The render function, generalized

The naive form of the thesis is `render(content, person, moment)`. Working through concrete scenarios — one exam dataset viewed by teacher/parent/student, one group chat consumed by CEO/PM/engineering manager, five feeds merged into one morning story, one person's work and personal mailboxes — forces three generalizations:

```
render(source*, viewer, moment)

  source*  =  a multi-source set (cross-source dedup and merge; raw data is a
              legitimate semantic payload — a production agent upstream is
              OPTIONAL, not required)
  viewer   =  person × role × persona (one human instantiates several viewers;
              role templates can belong to an organization, personal tuning
              belongs to the person)
  moment   =  the current state (time, attention, device, cognitive load)
```

Three consequences:

1. **Per-role**: one body of fact, N legitimate views — personalization is not only "this person, this moment" but "different roles at the same moment." This upgrades workplace deployments from a side market to a structural home ground (organizations are natively multi-role) — and immediately raises the loyalty question that red line 8 answers: role templates may be organizational; **the cognitive profile never is**. Note also that *permission and perspective couple*: which slice you are allowed to see is part of the rendering (the anonymized distribution shown to other students is a permission decision executed at render time).
2. **Per-persona**: the same person's identities need **hard partitions** inside the taste passport (work-me and home-me must not leak into each other; a cross-partition leak is a privacy incident).
3. **Production is skippable**: a consumption agent need not sit downstream of a production agent — it can sit directly on raw data or live streams, absorbing "production" into the moment of consumption. The JIT metaphor, completed: from source data straight to a personal view, with no intermediate finished good at all.

**One structure unifies these cases: one body of raw fact, N legitimate views. Architecturally, a consumption agent = a semantic materialized-view engine + a permission system + a per-person renderer.**

## 2. The semantic materialization layer

Per-person, per-moment rendering is economically insane if every view recomputes from raw sources. The middle layer is not a cache; it is the heart:

```
┌─ Raw layer ────────────────────────────────────────────────────┐
│ source data / messages / feeds, immutable; the final target    │
│ of every anchor-back link. Versioned.                          │
├─ Semantic IR (viewer-INDEPENDENT) ─────────────────────────────┤
│ entity alignment, cross-source dedup, event/topic clustering,  │
│ action-item extraction, timelines, evidence chains, confidence │
│ annotation. Shared by ALL viewers → cost amortized over N.     │
│ Incrementally updated (streams append deltas). Long TTL.       │
├─ Rendition layer (viewer × moment DEPENDENT) ──────────────────┤
│ semantic IR × viewer × moment → the experience. Session-TTL,   │
│ disposable — the engineering home of "no re-emission."         │
│ Rendering from IR is an order of magnitude cheaper than from   │
│ raw text.                                                      │
└────────────────────────────────────────────────────────────────┘
```

**Why it is the heart — five arguments.** (1) *Cost*: the answer to R10's compute objection in full — semantic work is O(content) and amortized across N viewers; per-view work is light. (2) *Shared intermediate computation*: every role view is a projection of the same IR; without it, each view recomputes from raw at N×M cost. (3) *Stream processing*: group chats and feeds are continuous — the IR layer is where incremental materialization lands. (4) *The permission execution point*: anonymization and aggregation happen at the IR→view projection (row-level security, semantically). (5) *The loyalty and provenance execution point*: canonical IDs are assigned here (anchor-back's carrier); triage decisions are logged here (auditable loyalty's landing site); confidence propagates from here (low-confidence content degrades gracefully in every view).

**The strongest analogy is LLVM** — source languages → LLVM IR → per-target machine code; content → semantic IR → per-viewer views. And the analogy's limit is the field's hardest open problem: **LLVM IR works because language semantics are formally defined; natural language has no formal semantics.** Which brings the traps.

**Four traps.**

1. *Premature IR schema* — you don't know what views need before you've built views. Derive the IR from one or two real views, then abstract.
2. *The middle layer swells into yet another data-warehouse project* — materialize lazily: only what consumption has proven useful.
3. *Hallucination amplification* — an extraction error entering the IR is inherited by N views (wrong once, wrong everywhere). Every IR node carries confidence + anchor; the dual benefit is that corrections amortize identically (fix once, everyone healed).
4. *The IR is the least loyal component in the architecture — governance must descend with it.* Entity alignment, event clustering, dedup, and confidence scoring carry the most editorial judgment in the system; every viewer inherits the same bias; and because each person sees a *different* rendering, **no user can detect a shared bias from their own view**. The gatekeeper retreating from the rendering layer into the semantic layer is more hidden, not less. Auditable loyalty therefore cannot stop at triage logs: IR construction decisions (what got merged, what got down-ranked, what counted as duplicate) must be logged and appealable too. And there is an epistemic trade-off with no free setting: evidence says summaries and presentation preferences are person-relative (PersonalSum; κ = 0.25), so "viewer-independent semantic operations" is a spectrum, not a given — **thicken the IR and viewer-dependent judgment fossilizes into the shared layer (sameness returns, one level down); thin it and the amortization vanishes.** Where that boundary sits is the architecture's genuinely hard question.

## 3. Direct mode vs. paired mode

Two deployment patterns, one criterion:

- **Direct mode** — the consumption agent sits straight on raw data (exam records, group chats, mailboxes): appropriate when the semantic layer **requires no professional judgment** (structure is self-evident or extractable).
- **Paired mode** — professionals × production agents prepare the semantic layer first; consumption agents render from it: required when the semantic layer **embeds professional judgment** (metric definitions, data lineage, business rules — "the metric's meaning" is a human decision that cannot be extracted away).

**The criterion in one line: does building the semantic layer require professional judgment?** Both modes share the same consumption-side runtime; they differ only in who materializes the IR. The paired pattern already has a ready-made hand-off artifact in the data world — the semantic layers BI spent a decade building (metrics layers, semantic models) are the data-domain IR. What is missing there is not the IR but the per-viewer renderer sitting on top of it: which is why data consumption is the cheapest place for this architecture to land.

The generalization beyond data: every "professionals cook, non-professionals eat" organizational scene has this shape — legal (counsel prepares diligence; business consumes risk points), medical (the lab produces; the patient consumes the report), engineering (builders produce; PMs and leadership consume progress). **That translation layer is today performed by humans who are good at slideware; it is about to be an agent.** Two enterprise pain points name the market: the *dashboard graveyard* (expensively built data assets with near-zero consumption — the agent raises the asset's turnover) and *analysts eaten by reporting* (professionals spending their week translating their own work for each audience layer).

## 4. Consumption as the demand sensor

When a viewer's follow-up question ("why did region X drop?") exceeds what the semantic layer contains, the correct behavior is not to hallucinate an answer but to **route the question upstream** as a demand ticket. This closes an organizational flywheel:

```
follow-ups / skips / expansions on the consumption side
  → demand signals → guidance for what the production side materializes next
  → the semantic layer grows the missing dimension → deeper drill-downs become
    possible → more follow-ups …
```

**The consumption agent is the demand sensor; the production agent is the supply executor; the middle layer is their contract.** Consumption-side telemetry is also the honest signal source for lazy materialization (trap 2).

## 5. A draft artifact contract

The interface-layer proposal from [Part 5](05-open-territory.md), sketched as fields. Production-agent output (reports, briefs, analyses, alerts) should ship with consumption metadata:

```yaml
artifact_contract:
  importance:        # why this matters, to whom (audience-addressed, not generic)
  audience:          # roles/personas this was produced for
  confidence:        # graded, not binary — propagates into every rendering
  evidence:          # anchors to sources; the anchor-back carrier
  contention:        # known points of disagreement (enables opposite-sides rendering)
  dependencies:      # what this supersedes or relies on
  expiry:            # when this stops being true/useful
  actionability:     # decision required? by when? by whom?
  privacy_level:     # personal / team / org / public
  interruptibility:  # is this worth an interruption at all (feeds L3 directly)
  modality_hints:    # audio-suitable? diagram-preferred? must-read-verbatim?
```

Design intent: the consumption agent orchestrates *by contract* instead of re-deriving importance and urgency from scratch per artifact; missing contracts are back-filled by the consumption side's own annotator (so adoption is incremental, not all-or-nothing). The standardization question this repo claims as open territory: **upstream output should be not merely machine-readable, but human-consumption-ready.** If you are building agent frameworks and want to experiment with the contract, that conversation is exactly what this repository is for.

---

*Back to the [README](../README.md) · or start over with [Part 0 · The Twelve Takeaways](00-twelve-takeaways.md).*
