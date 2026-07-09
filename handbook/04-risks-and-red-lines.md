# Part 4 · Risks and Red Lines

> Framing first: **for every risk below, the counter-measure is exactly what pure platform logic refuses to do — the risk list IS the differentiation list.** These are design inputs, not disclaimers. Format per item: problem → evidence → counter.
> Evidence grades: ✅ verified · ◎ corrected wording · ◐ single source · ⚠️ unverified. Facts as of 2026-07-09.

## R1 · Distortion: facts break in transit【already happened】

- **Evidence**: Apple Intelligence notification summaries compressed BBC coverage into fabricated headlines ("Luigi Mangione shoots himself" — invented; a tennis star "comes out" — misattributed). After BBC protests and an RSF condemnation, iOS 18.3 suspended news summaries, later restoring them italicized with warnings ◈. The essence: compression is lossy; when the loss lands on facts, "reads it for you" becomes "lies to you" — **and it lies wearing the original masthead's icon: the damaged credibility belongs to someone else.** Aggravator: the **Accuracy Paradox** ◐ — the more accurate the system, the more blindly it is trusted; and personalized fact-selection bias exists at the model layer already (Lazovich ◐), no malicious platform required.
- **Counter**: mandatory provenance (one step back to the original); uncertainty labeling; high-stakes categories (news/medical/legal) degrade to *quote, don't paraphrase* + show-the-diff. Trust design outranks raw accuracy. **"Trustworthy paraphrase" is itself a selling point.**

## R2 · Injection and covert ads: hijacking the paraphrase【already happened】

- **Evidence** ◎: Brave's research line is real (white-on-white page text steering an agent across tabs, 2025-08; screenshot-embedded near-invisible text read via OCR as instructions, 2025-10). The circulating interception numbers (Atlas 5.8%, Comet 7%, Chrome 47% on 103 live phishing attacks) trace to **LayerX Security, 2025-11** — a vendor with commercial interest, single source, methodology not fully public: **medium-low confidence**.
- **The projection** ○: attacks will evolve from hijacking *actions* to hijacking *paraphrase* — SEO aimed at agents: content embedding persuasion payloads so that *your* delegate quietly flatters a product or omits a fact. The gray edge of the GEO industry is already adjacent.
- **Counter**: content/instruction channel isolation (the perceiver has no action rights); paraphrase-vs-original consistency self-checks; least privilege; logged-out defaults. **Make anti-manipulation the selling point, not a compliance cost — the "agent firewall" is a product** (see Part 5).

## R3 · Filter bubble squared【predicted repeatedly; structural】

- **Evidence**: the Sunstein 2001 → Pariser 2011 lineage ✅; CHI 2024 ◐ — conversational search **even when designed neutral** produces more confirmatory querying and stronger polarization than conventional search; sycophantic style aggravates, challenging style mitigates.
- **The deeper worry this framework adds** ○: once *form* is personalized too, even "we read the same article" stops being true — common knowledge erodes one layer deeper than link-level filtering. (The social effects of form-personalization are unstudied — a research gap.)
- **Counter**: a serendipity budget as a first-class parameter (Kevin Kelly's ideal-filter recipe, item four: *things I don't like but should learn to appreciate*); active counter-perspective injection (Particle's Opposite Sides is a working UI); periodic "information diet checkups"; a **common-ground mode** for groups (everyone gets their own rendering *plus* a shared anchor — Fishwrap's "Daily We" page solved this in 1994); personalization intensity as a user-visible dial (Negroponte drew it in 1995).

## R4 · Cognitive offloading and taste atrophy【structural; hardest to counter】

- **Evidence**: MIT's *Your Brain on ChatGPT* (arXiv:2506.08872 ◐) — weakest EEG connectivity in the LLM-assisted group; 83% unable to quote their own just-written text; "cognitive debt" persists across sessions. **Pattie Maes — who founded the "agents reduce information overload" program in 1994 — is a co-author: the lineage runs its own critique.** Methodological caveats stay attached: small sample, and the task was *writing* (production), so analogy to consumption requires care. Theory shelf: desirable difficulty (Bjork — frictionless knowledge doesn't stick), fluency illusion, "taste is a muscle of choosing: delegate all choosing → atrophy → deeper delegation," and *summary culture* — everyone reads paraphrases, no one reads originals, and style, humor, ambiguity, and silence evaporate from circulation.
- **Counter** (the watershed against "TL;DR everything"): **friction management, not friction elimination** — compress low-value content to 30 seconds AND reverse-invest in high-value content (nudge you to close notifications and read the original; quiz you afterward); a slow-consumption mode (literature/art default to companionship, not compression); forced active recall in learning contexts; a transparent **delegation ledger** ("how much understanding did you outsource this month"). **The coach/slow-reading positioning is counter-intuitive but sound** — and it is the only counter that directly faces this evidence line.

## R5 · Intent commoditization: hyper-personalized persuasion【early-warning stage】

- **Evidence**: Cambridge HDSR 2024 ◈ — LLMs can capture "the you before you want it": persuasion tuned to your phrasing habits, guard level, and mood, with intent auctioned *before it crystallizes*.
- **The essence** ○: the taste model a consumption agent accumulates is the most precise persuasion arsenal ever assembled. **It protects you only if it does not belong to someone who wants to persuade you.**
- **Counter**: local/self-hosted first; the taste model never leaves the user's domain unencrypted; fiduciary duty written into protocol and (where possible) law; refuse commissions and advertising. **Loyalty is the brand.**

## R6 · The creator-starvation death spiral【in progress】

- **Evidence chain** (multi-batch + verified): Pew (68,879 real searches) — with an AI summary present, link clicks fall 15%→8%, citation clicks 1%, ~2/3 of searches with no click to traditional results (includes browse-elsewhere/session-end) ◐; publisher Google traffic median −10% (worst −25%) ◐; cases: Wired −62%, The Verge −85%, Business Insider −55% over three years; Cloudflare's Prince: earning traffic by being crawled is ~750× harder via OpenAI and ~30,000× harder via Anthropic than old Google ✅. **Counter-evidence kept honestly** ◐: zero-click was already ~2/3 of searches before AI; with-AIO zero-click rates fell 45%→38% within 2025 (users adapt); Google disputes third-party measurement. The collapse is real; "AI caused all of it" is an oversimplification — cite both.
- **The loop** ○: agents consume for humans → original clicks vanish → creators exit → high-quality supply dries up → agents have only slop left to paraphrase → consumption quality collapses. **A consumption agent eats the content ecology; if it eats it bare, it dies too.**
- **Counter**: settlement is not optional — it is a survival condition (the full Part 3 §6 stack: 402/RSL/attribution/licensed shares); make "where my subscription money went, by creator" a *user-visible feature* — a loyal agent also discharges the user's duty to creators; Particle's licensed revenue-share is the proven lawful path.

## R7 · The AI-slop double edge【the demand driver is also a self-risk】

- **Evidence**: NewsGuard's 49 AI-generated fake-news sites ✅; "dead internet" entering mainstream discourse ◐.
- **The bite** ○ (the skeptic's sharpest charge): the curation intake is being polluted by slop (garbage in), while **the L2 transformation pipeline is technically the same machinery as the slop production pipeline** — the only difference is *for whom, at whose request, transforming what*. A product must answer this boundary explicitly.
- **Counter**: the **no re-emission** red line (below); a verification layer (source reputation, AI-generation detection); and the honest sentence in public: a rendering made for one person, once, is the anti-slop configuration of this technology.

## R8 · Platform recapture and the gatekeeper paradox【happening】

- **Evidence chain**: entries — every free "your agent" is platform-subsidized; memory layer — Limitless→Meta (2025-12), Bee→Amazon (2025-07) ✅; mindshare — the local-language term already captured by commerce/companionship; capability — platform recommenders going generative (HSTU +12.4% ◎).
- **The paradox** ○: if consumption agents win, they are the new gatekeepers — owning the last inch of the demand side; producers start courting the agent (GEO experiments: +115% visibility from adding statistics ◐ — writing for machine readers has begun); whatever falls off the *agent shelf* is never seen by a human at all. Aggregator logic doesn't die; it changes hosts.
- **Counter**: open source + forkable, and a portable taste passport — **the only structural insurance against history repeating**; auditable loyalty; middleware-style regulatory advocacy (mandated API openness; algorithmic choice frameworks extend naturally to agents); prefer open protocols and licensed supply over gray scraping.

## R9 · Responsibility and paternalism【design dilemma】

- **The dilemma**: the agent blocked something you'd have wanted — who answers for it? Short-term wish (one more hour of scrolling) vs. long-term interest (sleep) — whom does the agent obey? Over-obedience = an addiction accomplice; over-intervention = digital paternalism. The Maes–Shneiderman debate (CHI 1997 ◈) replays intact on agent autonomy. The **accessibility paradox**: the same transformation that liberates a dyslexic reader may de-skill an able one — a feature's ethics flip with user state.
- **Counter**: a user-authored, amendable **constitution** (values and intervention boundaries, with appeal); graduated intervention with post-hoc review; every block queryable ("why didn't I see this?"); the **autonomy slider** — independently invented three times (Negroponte's knob 1995, Spotify's vibe control, Karpathy's slider) — treat it as a settled design pattern.

## R10 · Timing risk【the steelmanned opposition — keep it on file】

- Context sensing is immature: guessing wrong is *worse* than not adapting (the Clippy lesson; ProactiveBench's When-to-Assist exists to measure exactly this; Pulse is the newest data point). Cost: full-pipeline re-rendering per person per moment — the GenUI paper itself brackets generation latency out of its evaluation; the architecture answer is **cache the semantic layer, recompile only the experience layer**. Behavioral inertia: maybe most people just want the infinite feed — "healthier consumption" has historically never sold (the graveyard of mindful-tech products). **Therefore: enter where the pain already exceeds the switching cost** — information-drowning professionals, accessibility users, parents — and do not start by reforming mass entertainment.

## R11 · Adaptation rights and derivative works【early-warning; the second legal front】

- **Problem**: re-rendering (especially cross-modal transformation and narrative restructuring) touches the **derivative-work right** (17 U.S.C. §106(2) and equivalents) — a different and harder battlefield than "training is fair use," because renderings *substitute for the original in the market*, and market substitution is the heaviest fair-use factor. (Public debate has focused almost entirely on the access question — Amazon v. Perplexity — leaving this front largely unexamined.)
- **Risk gradient**: private, ephemeral, non-distributed renderings are low-exposure in most jurisdictions — **the "no re-emission" red line doubles as the primary legal firewall**; the moment renderings enter commercial redistribution, the risk goes live.
- **Counter**: private-and-ephemeral as default; licensed revenue-share as the proven path (Particle × Reuters/Fortune); prefer user-owned content (a "ruminator" over your own highlights has zero copyright exposure); form-preserving restraint on artistic works (red line 4) is simultaneously an ethical and a legal shield; commercial distribution only over licensed pools.
- **Status**: no case law yet targets *personal consumption rendering*; the output-side claims in NYT v. OpenAI are the nearest reference. Fast-moving; revisit.

---

## The eight red lines (non-negotiable)

1. **No re-emission** — renderings are private and short-lived by default; nothing returns to the commons unlabeled. The dividing line against the slop machine, and the primary legal firewall (R11);
2. **Anchor-back** — every rendering carries a canonical anchor to its source; two people seeing different renderings can still discuss the same thing. The minimum protection for shared facts;
3. **Show the original / show the diff** — one-tap restore; in high-stakes domains, display *what the transformation changed* (Apple already paid this tuition — no need to pay it again);
4. **Works vs. information** — informational content (form = packaging) transforms freely; artistic works (form = meaning: novels, poems, films) default to companionship, not conversion. **Knowing when not to transform is the highest capability**;
5. **The coach stance is configurable and transparent** — when to comply, when to challenge: the parameters belong to the user, not the platform;
6. **The user model belongs to the user** — the taste passport is exportable, portable, deletable (the legal anchor already exists: GDPR Art. 20 data portability and its analogues, e.g. China's PIPL Art. 45);
7. **Loyalty is auditable — on all three channels** — open source, or at minimum explainable logs; the audit covers *where the money flows*, *what signals the model learns from* (is the normative layer being contaminated by behavioral data?), and *whose model does the interpreting* (a declared, swappable interpreter). And the audit descends with the architecture: the semantic middle layer's editorial decisions (merging, down-ranking, dedup) are logged and appealable too — a gatekeeper that retreats from the rendering layer into the semantic layer is *more* hidden, not less;
8. **The B2B loyalty firewall** — the organization may define role views and role templates (inheritable across personnel); **the individual's cognitive profile is never visible to the organization**; triage must not optimize organizational metrics (read-rates, throughput). This is the loyalty axiom's survival clause in workplace deployments — the guard against sliding into the *overseer* archetype.

---

*Next: [Part 5 · Open Territory](05-open-territory.md) — the seven vacancies, the two cross-cutting layers, seven research gaps, and the open problems.*
