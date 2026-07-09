# Part 1 · The Concept

> What a consumption agent is, how to tell one when you see it, what it is made of, and why loyalty — not capability — is its first-order question.
> Evidence grades: ✅ verified · ◎ corrected wording · ◐ single source · ○ reasoning · ⚠️ unverified. Facts as of 2026-07-09.

## 1. Definition and contrast

**Production agent (supply-side automation).** Its goal is *to make the thing*. The output is an artifact added to the world — code, a report, a spreadsheet, an article. Even when a consumer uses it directly (drafting an email with ChatGPT), the act is still production.

**Consumption agent (demand-side automation).** Its goal is *for this person to consume just right, right now*. It adds no information to the world; it aligns information that already exists (including the output of production agents) with a specific person in a specific moment — **selecting, transforming, orchestrating, delivering — or blocking on your behalf**.

One sentence pins the essence (three research batches converged on the same insight through different metaphors — late binding, JIT compilation, score-and-performer):

> **The form of content is moving from being decided at production time to being decided at consumption time — the late binding of form.** Content is source code; the person is the target platform; the consumption agent is a just-in-time compiler. Meaning is produced once; the experience is compiled at the moment of consumption, used once, discarded, recompiled next time.

| | Production agent | Consumption agent |
|---|---|---|
| Represents | the task / the supply side | the person / the demand side |
| Output | an artifact (enters the world, persists) | an experience (generated for one person, one moment; disposable) |
| Optimizes for | the world's state correctly changed | the person's state properly served (experience return per unit of attention) |
| Failure mode | did it wrong | wrong timing, wrong density, wrong form; interrupted you; got you hooked |
| Evaluation | benchmarkable (SWE-bench et al.) | almost no benchmarks; long-run trust and well-being |
| Business-model sensitivity | low (pay for results) | **extreme** (who pays decides whom it serves) |

## 2. The test: three properties, four traits

Consumption agents generate tokens too — summaries, podcasts, ephemeral interfaces — so "does it generate?" cannot be the criterion. The real test:

**Three tests on the output:**
1. **Audience test** — made for the public record (production) or for one person in one moment (consumption)?
2. **Lifetime test** — must remain correct and citable (production), or disposable by design, legitimately different tomorrow (consumption)?
3. **Information test** — does the world gain a new piece of information (production), or does existing information gain a better fit to one mind (consumption)?

**Four traits of the agent:** it adds no information — its value comes from processing what exists; its input includes *the person's current state* — the same content for the same person should render differently at different moments; its loyalty runs to the consumer — the objective function is defined by the user, not by platform metrics; and it has **the right to refuse** — the standing and the motive to say *no* to content: filter it, block it, down-rank it, advise you not to look. Platform-owned agents structurally cannot satisfy the last trait.

A corollary: **disposability and privacy are virtues here, not defects** — a rendering made for one person, once, adds no slop to the commons, provided the "no re-emission" discipline holds (see [Part 4](04-risks-and-red-lines.md)).

**Calibration exercises.** TikTok's For You feed = a consumption agent, *owned by the platform* (satisfies trait 2, fails 3 and 4). The spam filter = the lineage's most familiar mass deployment, an heir rather than a founder (its ancestors run through Malone's Information Lens back to Luhn's SDI, 1958); it satisfies the traits in a minimal, degenerate form. Ad blockers and SponsorBlock = the prehistoric form. NotebookLM = close, but transformation only. ChatGPT in its default use = production. **Hybrids are legitimate** (read the material, then draft an action list): the boundary is drawn by intent and destination, and it is a spectrum, not a wall.

## 3. The capability stack (five axes, one system at different resolutions)

**Functional axis — the three-layer stack** (the most-used top map):

- **L1 Curation** — what deserves your attention at all; run in reverse, it is protection (blocking slop, clickbait, manipulative content);
- **L2 Transformation** — changing form. **The genuinely new capability LLMs add**; it did not exist before;
- **L3 Orchestration** — when to deliver, at what cadence, when to interrupt, when to stay silent. This is where the *agent-ness* lives: resident, stateful, spanning time.

Recommender systems do only L1. NotebookLM does only L2. **A resident L1+L2+L3 closed loop does not exist anywhere** — five research batches independently confirmed the same absence.

**Engineering axis — three building blocks:** context sensing (knowing your bandwidth right now — the weakest block, hence the opportunity), preference modeling (a long-lived personal model you can correct in natural language — memory infrastructure is commoditized, but no one has built the *consumption-preference ontology*), and modality transformation (maturing fastest). Block 3 alone = a format converter; 2+3 = a personalized content factory; **only 1+2+3 is an agent that knows how to serve you this, now**.

**Parameter axis — seven rendering knobs:** form (text ↔ audio ↔ video ↔ diagram ↔ interactive UI ↔ dialogue), density (10-second gist ↔ full text ↔ expanded tutorial — i.e., semantic zoom), perspective (neutral / adversarial / multi-source merge / bias made visible), pacing & timing, interaction depth, context linking ("this contradicts the piece you read last month"), language & accessibility. **The knobs turn both ways** — the core verb is *matching*, not compression: **it is a dietitian, not a juicer**.

**Product axis — a ten-function stack:** filter / schedule / transform / connect / pace / converse / verify / protect / remember / transact. Most existing products do one or two. **Scheduling, pacing, protection, and user-owned memory are nearly untouched.**

**Process axis — the consumption pipeline** (the engineering view):

```
ingest → personal context (long-term preferences + current state) → intent recognition
→ triage (decide what is NOT worth seeing — before retrieval)
→ structuring (topic graphs / evidence chains / points of conflict) → representation planning
→ narrative ordering → interaction management → credibility & source grading
→ memory & action hand-off → feedback loop (gets better with use)
```

Two under-appreciated stages: **triage precedes retrieval** (the core act is triage, not search), and the **action/memory hand-off** (consumption is not an endpoint but an interface in a loop — turning "understood" into something executable or memorable).

## 4. Three metaphors (memory anchors)

1. **JIT compilation of content.** Content used to be AOT — ahead-of-time compiled: the author fixes one version, a million people consume that one version, and all adaptation cost is paid by readers' attention (skimming, abandoning, swiping away). The consumption agent turns "compile once, run everywhere" into "compile at every act of consumption." Structural corollary: **the storage form and the consumption form of content will separate** (semantic layer vs. experience layer), as source code separated from machine code.
2. **The score and the performer.** Content is the score; the agent is the performer — the same score is played differently for different audiences, but the score itself is unchanged, citable, shared. This single image explains both "renderings are not worth re-emitting into the commons" and "the anchor to the original score must be preserved."
3. **Rectifying the name *User-Agent*.** In HTTP, the browser's formal name has always been *User-Agent* — the user's delegate. For thirty years it was in practice **the producer's executor**: page styling, ad placement, infinite scroll were all decided by the supply side; Reader Mode and ad blockers were the only small rebellions. The LLM consumption agent is the first time User-Agent becomes true to its name — which also explains the 2025 browser wars: what everyone is fighting over is precisely the *consumption delegate* position.

## 5. Loyalty: the first-order question

**Whom does this rendering layer work for?** The feed era already taught the lesson: when the rendering layer works for the platform and optimizes engagement, you get addiction design and information cocoons. Four archetypes:

| Archetype | Behavior | Optimizes | Funded by |
|---|---|---|---|
| **Dealer** | amplifies what you crave right now | engagement / time-on-app | advertising |
| **Butler** | obeys your explicit instructions | task completion | subscription / purchase |
| **Coach** | serves your long-term intent; dares to contradict your present comfort | long-term goals | user-funded + on-device + deep trust |
| **Overseer** (B2B failure mode) | makes sure you digest what the organization wants digested | throughput / read-rates | the organization |

**Who pays decides loyalty** (five research batches reached this independently): ad funding slides structurally toward the dealer; user funding and on-device operation are the only soil where a coach can exist. This is a business-model problem, not a technical one — and the reason incumbents structurally cannot occupy the niche: agent-mediated consumption kills advertising, and an ad company building it would be committing self-revolution.

**The second loyalty channel: the training signal** (added after external review, 2026-07-09). Money is only one channel. A preference model fed on behavioral signals alone — taps, skips, completions — is running the *same mathematical gradient* as feed-era engagement optimization, whoever pays. **Dealer dynamics can grow out of the data loop without any advertising.** The structural (not promissory) countermeasures:

1. Split the user model into two layers — a **descriptive layer** (how you actually consume; learned from behavior) and a **normative layer** (the consumer you intend to be; explicitly written by the user, modifiable only explicitly, never updated from behavioral data). The triage objective = descriptive fit *subject to normative constraints*. The two-layer structure itself — not extra fields — is what distinguishes a consumption-preference ontology from generic memory layers;
2. Coach parameters never enter the optimization loop; their effects go only into a user-visible retrospective. Otherwise short-cycle behavioral metrics quietly teach the agent to challenge you less (challenge reliably generates "regret" signals).

**The third loyalty channel: the rented interpreter** (added 2026-07-09, after the paper's external review). Most consumption agents will not own their own judgment: the interpreting model is rented from a foundation-model vendor, and it arrives with dispositions nobody chose — sycophancy is documented as a systematic byproduct of human-feedback training, exactly the direction a coach must resist — plus the vendor's content policies and commercial relationships, riding in on the weights. You can own the passport and still not own the interpreter. The countermeasures parallel the other two channels: interpreter portability (the model as a swappable component), cross-model divergence checks on the same triage, and a local model as an audit baseline.

**Positioning, precisely:** what incumbents cannot build is the *loyalty architecture*; the coach is the ceiling that architecture makes possible, not a precondition. A butler — obedient but loyal, subscription-funded — is equally impossible for an ad-funded platform. **Butler value carries the commercial floor (the done-for-the-day feeling of a budget honored, triage that saves time); coach is the upside differentiation** — a configurable stance and a brand value, falsifiable early at small scale.

The coach stance is not rhetoric; it has data ◐: a CHI 2024 experiment showed sycophantic conversational search *increases* confirmation bias while a challenging style mitigates it. Coaching also means preserving **desirable difficulty** (Bjork): if everything is flattened into the most comfortable form, the capacity to chew hard text atrophies. A coach sometimes adds weight to the bar. Searls's distinction transfers directly: **personal AI (one you own) ≠ personalized AI (a platform that knows you better)**.

One warning from a deeper layer (Cambridge HDSR 2024 ◐): LLMs make *intent* inducible, harvestable, predictable — and **pre-sellable**. The taste model a consumption agent holds is the most precise persuasion arsenal in history. **It protects you only on the condition that it does not belong to someone who wants to persuade you.** The two futures of the intention economy (Searls's optimistic version vs. Cambridge's pessimistic one) fork on exactly one variable: who owns the intent data and the delegation.

## 6. Boundaries and the name

**Against neighboring concepts.** vs. **recommender systems**: they solve "which one"; a consumption agent also solves "what it becomes once chosen, and how it unfolds" — the feed picks the groceries, the consumption agent cooks. vs. **chat assistants**: not one more chat box, but a different rendering engine — chat is just one of its many surfaces. vs. **RAG / chat-with-docs**: "answer questions from documents" ≠ "how do I most effectively consume this corpus" — path, pacing, medium, evidence, review are not what RAG naturally solves. vs. **agentic commerce** (an explicit cut — the Chinese term has already been captured by shopping agents): a commerce agent delegates your *transaction decisions*; a consumption agent delegates your **attention and cognitive bandwidth**. Shared infrastructure; entirely different value proposition. vs. **TikTok** (the reference anti-pattern, three defining differences): it selects but does not render; it optimizes platform time, not user well-being; you cannot correct it in natural language.

**The name — status and recommendation.** The typology vacancy is confirmed (four independent searches ✅), but term erosion is accelerating: "consumption agent" is already locally occupied by BI (Microsoft's own docs: "Consume a data agent") and by energy analytics ("peak consumption agent"). Recommendation: use **consumption agent** externally and cut in the first sentence ("it delegates your attention, not your wallet"); use **experience compiler** to explain the mechanism; use **consumption orchestration layer** in architecture contexts; anchor academically to the interface-agent + sensemaking lineages. Slogan candidates: *AI that consumes before you consume* / "production agents help the world make more information; consumption agents help humans reclaim the ability to digest it."

## 7. The elevator pitch (reusable verbatim)

> For the past three years, every agent has helped people produce: write code, make reports, run data. Nobody stands guard for the consumer. The way we consume content is still industrial: the author produces one version, everyone consumes the same version, and the entire adaptation cost is paid by human attention. The consumption agent flips this: it knows where you are right now, how much time you have, how deep you want to go — and compiles the meaning the world has already produced into the one version that belongs to you in this moment: a podcast segment, a one-screen brief, a conversation you can interrupt. Used once, discarded, recompiled next time. Content is source code; you are the target platform; it is the compiler. Recommendation algorithms decide what you see; the consumption agent decides how you see it — and it answers only to you.

---

*Next: [Part 2 · The Case](02-the-case.md) — eighty years of lineage, why now, the empirical base, and the naming vacancy stated precisely.*
