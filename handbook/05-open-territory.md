# Part 5 · Open Territory

> Where the vacancies are — for builders, for researchers, and for anyone who wants to claim a piece of an unnamed field. This chapter is deliberately an invitation.
> Evidence grades: ✅ verified · ◎ corrected wording · ◐ single source · ○ reasoning. Facts as of 2026-07-09.

## 1. Seven vacancies

### 1.1 The intent compiler — the "current state" engine ⭐ (first priority)

"I'm exhausted tonight but want to keep up with AI" → `{form: audio, density: low, duration: 15min, novelty-filter: high, challenge: 0}`. This is the consumption agent's query planner, and it is **completely empty**: every product on the market makes the user pick the format by hand (NotebookLM's wall of buttons); no one compiles *state* into *rendering parameters* automatically. Academic footholds exist at the edges: Malleable Prompting shows the forward direction (preferences → materialized controls) works, so state → parameters is its dual; ProactiveBench's When-to-Assist is the evaluation seed.

**Why first priority:** it is the *interpreter* — the scheduling intelligence whose absence shows up as the empty row in every capability matrix — and the taste passport (1.2) is merely its memory. The strategic asymmetry, made explicit after external review: **what can be carried away is data; what cannot be carried away is the interpreter** — the judgment quality that compiles a passport into "what to give you, right now." Play the passport as an open standard; hold the interpreter as the compounding asset.

### 1.2 The taste passport — a consumption-preference ontology (open standard play)

The status ◎ (corrected after verification): not "completely blank" anymore — Stanford's **Loyal Agents** project (with Consumer Reports; contributors across MIT/Stanford/Oxford/OpenMined/Microsoft Research) carries the **Human Context Protocol (HCP)**: "portable, persistent personal memory — a user-governed layer of context." There is a reference server; there is **no product adoption**. Two readings: the competitive signal is lit (what remains claimable is the reference implementation and the killer app), and — notably — HCP lives *inside a loyalty project*: the personal-memory line and the fiduciary line have already merged in the wild, exactly the pairing this framework treats as definitional.

What HCP does not cover — the consumption-specific ontology — is still unclaimed: a **form-preference matrix** (topic × situation → preferred form), a **cognitive profile** (known-territory graph; error-prone topics; desirable-difficulty tolerance), an **attention rhythm** (budget history, compliance patterns, interruption-regret record, weekly cadence), and a **trust graph** (personal source reputation; which topics demand the original).

Two structural constraints matter more than any field list. **First, the two-layer split** (see Part 1 §5): a descriptive layer learned from behavior, and a normative layer written by the user and never updated from behavior — the split itself is the defense against the objective-function pollution that would otherwise re-derive the dealer from the data loop. **Second, portability with a legal anchor**: GDPR Art. 20 and its analogues make "exportable, portable, deletable" not just an ethic but a compliance story. Strategy: build applications first, let the schema grow from real usage data (drawn from more than one person — an ontology grown from a single extreme user repeats the llms.txt mistake), stay HCP-compatible, and propose back — formats without a consumption side die of exposure.

### 1.3 Timing and cadence — the attention-budget steward

"You have 40 minutes of consumption budget today; here is the optimal allocation; the rest goes to the weekend digest." Simon's attention economics, turned into a product. Unoccupied and high-frequency; Pulse's one-batch-per-day / 24-hour-expiry was an embryo, but nobody has built the full loop of **budget → negotiation → carry-over → retrospective**. This is the coach archetype's most natural landing spot, and the corrected answer to Pulse's death: *explicitly negotiated* proactivity.

### 1.4 The agent firewall / verification layer

Injection is systematized (Brave's research line); "covert ads aimed at agents" are the predictable next step; anti-manipulation is productized by no one. Shippable as middleware any agent can mount: injection detection, paraphrase-vs-original consistency checking, persuasive-content labeling, source reputation. B2B willingness to pay already exists in the security budget.

### 1.5 The slow-consumption companion

Everyone builds compression and speed; no one builds *helping you go slower, better*: companion annotations, active recall, spaced repetition, cross-book linking. The cleanest objective function in the whole field — and the only product thesis that directly answers the cognitive-debt evidence line (R4).

### 1.6 Group consumption / common ground

The same substance rendered per family member or per team role — the child gets the diagram, the engineer gets the data, the manager gets the audio — **with a shared anchor preserved so everyone can still discuss the same thing**. Both a feature and the product-level answer to "personalization erodes the public sphere" (R3). The 1994 precedent: Fishwrap's "Daily We."

### 1.7 The non-English niche

In the Chinese-language world, the local term is captured by shopping agents and companionship apps: **"a consumption delegate loyal to the user" is unclaimed as a concept and unoccupied as a product**. Structurally: higher walled gardens make aggregation harder — and make a wall-crossing consumption layer *more* valuable, not less. (Details of that ecosystem are out of scope here; the takeaway is that the vacancy is global, not an artifact of English.)

## 2. Two cross-cutting layers

**The metrics layer — attention ROI.** Production metrics (completion rate, output quality, time-on-task) do not transfer. The indicator family that does: *process* — time-to-relevance, irrelevant-exposure rate, interruption-regret rate, source-check rate; *outcome* — comprehension (can you restate it), calibrated confidence (neither blind trust nor blanket doubt), decision latency, 24h/7d retention, action conversion; *health* — diversity (anti-cocoon), steerability (can the user change granularity/medium/order), long-term alignment, trust-repair rate. The sentence that anchors the family: **"what matters is not how short the summary is, but whether the user met the right content at the right time at the right granularity — and knows how reliable it is."** One measurement discipline learned the hard way: coach-stance parameters must never be optimized against short-cycle behavioral metrics (challenge reliably produces "regret" signals); their effects belong in a user-visible retrospective, outside the loop.

**The interface layer — the artifact contract.** Production-agent output should carry consumption metadata: importance, audience, confidence, evidence, points of contention, dependencies, expiry, actionability, privacy level, **interruptibility** (is this worth an interruption at all), audio-suitability. The consumption agent orchestrates by contract instead of re-deriving everything. The claimable standardization question: *should upstream output be not merely machine-readable but human-consumption-ready?* (A fuller sketch in [Part 6](06-architecture-notes.md).)

## 3. Seven research gaps (the academic agenda)

1. **A metrology of consumption quality** — task work has SWE-bench; "were these ten minutes well spent" has nothing. Probably the single most valuable academic contribution available; the parts exist (GenUI multi-dim evaluation, UIST load estimation, BEAM preference-decay, learning-science transfer tests) and the integrated benchmark does not.
2. **Rendering fidelity** — no benchmark for semantic preservation across form transformations (text→audio→diagram→interactive).
3. **A taxonomy of "do not transform"** — form-preserving content classification (genre + author declaration + user override) is handled by no one.
4. **Cross-source user models** — a standard schema for taste/knowledge-state/attention-budget plus an edge-first federated privacy architecture: both blank.
5. **Formalizing serendipity** — Kevin Kelly's fourth ingredient ("what I don't like but should learn to appreciate") has no explicit algorithmic literature.
6. **Autonomous state sensing** — audience adaptation today is prompt-declared (the GenUI paper's own stated limit); inferring time/attention/device/cognitive load is essentially unstudied.
7. **Three communities that don't cite each other** — RecSys (L1), NLP summarization (L2), and HCI interfaces (L2/L3) are working the same problem without shared references; the integration layer is itself a publishable gap.

## 4. Open problems (carried honestly)

**Conceptual** — how to measure consumption quality (gap #1); the minimal sufficient sensor set for "current state"; a working detector for form-preserving content; how to formalize serendipity without formalizing annoyance; the precise treatment of hybrids on the production/consumption spectrum.

**Engineering** — does triage start from rules or from a small model; the least-intrusive interaction primitive for budget negotiation (ask nightly? weekly default with daily nudge? infer from calendar and confirm?); the local/cloud split (preferences at the edge, semantics in the cloud?); how to test cross-modal semantic fidelity; **where the semantic middle layer's thickness boundary lies** — which semantic operations are genuinely viewer-independent? Thicken the shared layer and viewer-dependent judgments fossilize inside it (sameness returns one level down, invisible from any single user's view); thin it and the cost amortization vanishes. The LLVM analogy has a limit: natural-language semantics has no formal definition (see [Part 6](06-architecture-notes.md)).

**Architectural** — do sensitive passport fields (the cognitive profile) ever leave the device, and what does encrypted sync look like; in workplace deployments, which parts of the passport belong to the person and which to the organization (role templates inherit; cognitive habits travel — but the boundary needs case law of its own); once consumption agents expose interfaces, how do you keep "a platform agent wearing a user-agent skin" out.

**Ecosystem** — the coach's license to contradict the user: where does it end (a philosophy problem wearing a product hat); is a walled-garden ecosystem a fatal barrier or a natural moat for wall-crossing layers; when creator declarations ("do not transform") collide with consumer needs, where is the line — and does accessibility constitute an exemption; and if consumption agents win, what stops the winner from becoming the next gatekeeper (R8 — the honest answer today is: open source, portability, and regulation, i.e., structure, not virtue).

---

*Next: [Part 6 · Architecture Notes](06-architecture-notes.md) — the render function, the semantic materialization layer, direct vs. paired deployment, and a draft artifact contract.*
