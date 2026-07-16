# Codebook — Classifying One Act of an AI System (v0.9.2, 2026-07-13)

> **What this document is.** This codebook is the operational form of the two-level criterion in *Consumption Agents* §2.2, and it is **the instrument under test** in the inter-rater study: what the study measures is whether trained annotators can apply *these instructions* consistently. Every decision rule below quotes the criterion text it operationalizes; no rule without a textual basis has been added. The codebook is published with the study (it is citable as the criterion's operationalization of record).
> **Status:** frozen at main annotation start; pilot-stage amendments are numbered and logged.
> **Pre-freeze revision (2026-07-13, with paper v0.9.2; before pre-registration hash):** Q0 gains the "single run, opposite sides" wording and its basis now quotes the revised §2.3 hybrid clause and the revised calibration example; a principal-identification rule and a generation-time-intent rule are added to §0, each with its §2.2 textual basis (the paper text was revised first — criterion and operationalization move together, before the hash). Trail: paper-criterion revision-candidates document (2026-07-12) → P4 decision → codex re-review, 2026-07-13.
> **Annotator-facing note.** You will classify short descriptions of *one system performing one concrete run* ("an act"). There are no trick questions about facts: everything you need is in the vignette (and, in Task B, the fact card). Where you feel information is missing, use the flag — but still choose.

## 0 The unit: an act

You classify **one run and its output** — not the company, not the product line. The same product can perform acts of different kinds; that is expected, not a contradiction. *(Basis: "the unit is a run and its output, and a product is a distribution over acts.")*

**When was the destination decided?** An act is classified by the destination its output was **intended for at generation time**: a draft commissioned for someone else's inbox is production from the start, even if the person edits it before sending; passing something on *after* the fact is a **new act** by whoever decides it, and does not reclassify the original. *(Basis: "an act classifies by the destination intended at generation time: a draft commissioned for someone else's inbox is production from the start, while re-emission decided only after the fact is a new act belonging to whoever decides it.")*

**Who is the principal?** The principal is the consumer for whom the output is rendered in that moment — one person, or a bounded group consuming together — **not necessarily whoever deploys or pays for the system**. An employer-deployed tool that renders a summary for an employee has *the employee* as the principal of that act; who controls the objective, and whose metrics the system answers to, belong to Task B (traits 3–4), not to placement. This does not exempt reporting flows: a report or metric stream the system sends to a deployer is itself an output, and the information test reads it like any other — it leaves the reading employee's sphere. *(Basis: "the principal of level one is the consumer for whom the output is rendered in that moment — one person or a bounded group — not necessarily whoever deploys or pays for the system … any report or metric stream the system emits to a deployer is itself an output, and the information test reads it like any other output.")*

## 1 Decision procedure (follow in order)

### Step 0 — Decomposability check (hybrid gate)

**Q0. Is this act a single run with separable output components whose destinations fall on opposite sides of the principal's sphere — one component producing something that persists in the record beyond the principal's control, another producing something only for the principal's own moment?**

- **YES →** classify **hybrid**. Write one line naming the production-side component and the consumption-side component. Do not proceed to Steps 1–4. *(Basis: "a hybrid act is a single run with separable output components, at least one of which leaves the principal's sphere as a durable record while at least one remains a momentary rendering within it"; the calibration example "Read corpus, brief me now, and post the action list to the team board" is classified "legitimate hybrid: one run, two destinations.")*
- **NO →** proceed. A non-decomposable act is never hybrid; disagreements among the three tests are resolved in Step 4, not by choosing hybrid.

*Guidance:* incidental byproducts (logs, cached files, the system's own memory updates) do **not** count as a production component — see Step 3 guidance on control-plane state. Two runs that happen in sequence are two acts, not one hybrid. And reading or gathering done *in service of* the output is internal processing, not a consumption-side component: a system that reads a corpus in order to post one list to a board performs a production act with no split. *(Basis: "a crawler's read is production-side work (feeding an artifact).")*

### Step 1 — Audience test

**Q1. Is the output made for the open record, or for an identified principal — one person, or a bounded group consuming together — in one moment?**
*(Basis: "Is the output made for the open record (production), or for an identified principal — one person, or a bounded group consuming together — in one moment (consumption)?")*

- Open record / anyone who comes later → **P**
- An identified person or bounded group, now → **C**
- *Bounded group* means the members are enumerable and consume together (a family, a team, a named community); "everyone who subscribes" to an open publication is the open record, not a bounded group.

### Step 2 — Lifetime test

**Q2. Must the output stay correct and citable, or is it disposable by design — legitimately different tomorrow?**
*(Basis: "Must it stay correct and citable (production), or is it disposable by design — legitimately different tomorrow (consumption)?")*

- Must remain right; others may rely on or cite it later → **P**
- Used once, then discarded; regenerating it differently tomorrow would be fine → **C**
- The question is about the output's *design contract*, not whether a copy technically survives somewhere.

### Step 3 — Information test

**Q3. Does the world gain a new piece of information, or does existing information gain a better fit to its principal?**
*(Basis: "Does the world gain a new piece of information (production), or does existing information gain a better fit to its principal (consumption)?")*

- "The world" means **the record beyond the principal's control**. *(Basis: "'The world' here means the record beyond the principal's control: … the test asks whether those bits leave the principal's sphere as a durable artifact (a drafted email that leaves your outbox has, however small its audience), or remain the principal's own momentary rendering (a private note does not).")*
  - Output leaves the principal's sphere as a durable artifact — even to a single recipient → **P**
  - Output stays inside the principal's sphere as a momentary rendering → **C**
- **Control-plane state is not a contribution to the record:** the system's own preference models, feedback logs, and audit records live inside the principal's sphere. *(Basis: "The agent's own persistent state — preference models, feedback logs, audit records — also lives inside the principal's sphere: control-plane state, not a contribution to the record beyond it.")* Do not classify an act as production merely because the system remembers something.
- A purchase, booking, or other transaction **creates a durable record beyond the principal's control** (an order in a merchant's system) → **P** on this test.

### Step 4 — Placement

- All three tests agree → that side is the **placement**.
- Tests disagree (on a non-decomposable act) → **the information test governs.** *(Basis: "When they disagree, the information test governs: it is the direct reading of value flow, and the audience and lifetime tests are its two symptoms.")*
- Record all four fields (three tests + placement) — the tests are data, not scratch work.

**Two cautions** *(both from the criterion text)*:
- Placement is **loyalty-blind**: a platform's feed and a spam filter can both place on the consumption side. Do not let your opinion of the vendor move the placement. *(Basis: "Level one is loyalty-blind.")*
- Placement is **not** the engineer's read/write split: an agent writing to your private notes can be performing a consumption act; a crawler's read is production-side work (feeding an artifact). *(Basis: "Nor is the axis the engineer's read/write-path split in disguise.")*

### Confidence, slider, flags

After placement: mark the 1–5 production↔consumption slider (your sense of where on the spectrum the act sits — the criterion says "it is a spectrum, not a wall"); confidence 1–5; the insufficient-information flag if you needed facts the vignette did not give (you must still choose); for adversarial-stratum items, one line of rationale.

## 2 Task B — the four loyalty traits (fixed subset only)

Frame: **assume the act places on the consumption side**; judge whether the *system as deployed in this vignette* satisfies each trait, using the vignette + fact card. Scale: ✓ satisfied ｜ ◐ partially / degenerately satisfied ｜ ✗ failed.

- **T1 — adds no information to the shared record.** *(Basis: "It adds no information to the shared record — its value comes from processing what exists.")* ✓ = nothing leaves the principal's sphere; ◐ = minor/optional leakage paths exist; ✗ = output routinely enters the shared record. (T1 largely re-checks Step 3; it is analyzed as a consistency check.)
- **T2 — input includes the person's current state.** *(Basis: "Its input includes the person's current state — in the limit, the same content for the same person renders differently at different moments; weaker systems satisfy this only per-person, not per-moment.")* ✓ = per-moment (time, attention, device, situation shape the output now); ◐ = per-person only (a standing profile, no sense of the moment); ✗ = same output for everyone.
- **T3 — objective function set by and answerable to the user.** *(Basis: "Its objective function is set by and answerable to the user … not by platform metrics.")* ✓ = the user defines/adjusts what the system optimizes, and the fact card shows no overriding platform metric; ◐ = user has partial, coarse, or nominal control (a few settings around a fixed platform objective); ✗ = the optimization target is the operator's metric (engagement, throughput, read-rates, conversion).
- **T4 — the right to refuse.** *(Basis: "It has the right to refuse — the standing and the motive to say no to content: filter it, block it, down-rank it, advise against looking at it (a graduated, appealable license, not a blank one).")* ✓ = the system can and does decline/withhold/advise-against, and the user can appeal; ◐ = refusal exists but is marginal (an optional mode beside a core loop that never says stop); ✗ = the system structurally cannot or will not say no.

If the fact card does not settle a trait, choose the best-supported value and mark low confidence — the study is measuring exactly whether these traits are judgeable from public information.

## 3 Worked examples (training only — never in the case set)

**W1 — production act.** A marketing team's writing assistant drafts a product-announcement blog post; a human approves it and the system publishes it to the company's public site. *Q0: no split — one output, one destination. Q1: open record → P. Q2: must stay correct, will be linked → P. Q3: the public web gains a post → P. Placement: production.* (Whoever benefits, the act makes a durable public artifact.)

**W2 — consumption act.** During a commute, an assistant takes the three newsletters its user already subscribes to and turns them into an eight-minute audio digest for that ride; the audio is not saved. *Q0: no split. Q1: one person, one moment → C. Q2: disposable by design; tomorrow's digest may differ → C. Q3: no new item beyond the user's sphere; existing text gained fit to one listener → C. Placement: consumption.* (Task B sketch: T2 would be ✓ — the ride's length shaped the output.)

**W3 — hybrid act.** After a project meeting, an assistant (a) posts the official minutes to the team's shared wiki and (b) gives each attendee a private one-screen "what you personally need to do" view that expires at day's end. *Q0: YES — component (a) enters the shared record (production side); component (b) is per-person, momentary (consumption side). Classify hybrid, name both components. Steps 1–4 skipped.*

## 4 What not to do

- Do not classify the company or brand — only the described act.
- Do not import outside knowledge about the named system; the vignette and fact card are the whole record. (Most cases are de-branded for this reason.)
- Do not choose hybrid to express uncertainty — hybrid requires a nameable component split (Step 0); uncertainty goes in the confidence score and the flag.
- Do not discuss cases with other annotators; questions go to the written FAQ, whose answers are shared with everyone.
