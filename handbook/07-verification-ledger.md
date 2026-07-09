# Part 7 · The Verification Ledger (Public Digest)

> The audit trail behind the evidence grades. This digest publishes the falsification record — the claims that *died* during research and review — because a corpus that only shows what survived is not auditable. Facts as of 2026-07-09.

## 1. Method

- **Six parallel research batches**, cross-read against each other; contradictions arbitrated against primary sources by dedicated verification agents.
- **Every number returns to a primary source** before it is quoted; where it cannot, it is marked ◐ (single source) or ⚠️ (unverified) and treated as non-load-bearing.
- **Evidence grades carried on every fact**: ✅ verified (adversarial three-vote or primary-source word-for-word) · ◎ corrected wording (do not quote older figures) · ◐ single source · ⚠️ unverified.
- **Grades may only be lowered, never raised, when a fact moves between documents** (a discipline adopted after violation #11 below).
- The position paper distilled from this corpus then absorbed **four internal adversarial reviews and six commissioned external LLM reviews**; every comment was adjudicated — accepted with a fix, logged as a deliberate design choice, or rejected with a recorded reason. Several review claims were themselves falsified against primary sources before rejection; several of our own verified-marked facts were falsified by reviewers and corrected. Both directions are recorded below.

## 2. Falsified claims (removed or corrected — the record of being wrong)

| # | Claim that died | How it died |
|---|---|---|
| 1 | Google GenUI "47% preference / task steps −30%" | Neither number exists in the paper, the blog, or Nielsen's commentary; the entire item was dropped |
| 2 | Instant Checkout "buy-button conversion <1% (industry 3–4%)" | No primary source; replaced with the first-party framing (a merchant executive's "~3× worse than own site") |
| 3 | RSL launched with "50+ publishers" | Official release names ~16; "50+" has no official source |
| 4 | "Atlas 5.8% interception from a GitHub PoC repo" | True origin is LayerX Security (vendor, methodology not fully public); downgraded to medium-low confidence |
| 5 | Nielsen's "users prefer human design 56% vs 43%" | The underlying paper reports 50.0/35.3/14.7; Nielsen's rendering is a distortion — not used |
| 6 | "open-notebooklm cloned NotebookLM within weeks" narrative | Failed adversarial verification; not used |
| 7 | "2026: first year non-human traffic passed half the internet" (as a general fact) | Cloudflare-network measure only; Imperva's methodology reported >50% back in 2024. Restated as vendor-scoped; the precise 57.5% figure was later demoted from the paper's body text after two reviewers could not reconcile it with public Radar cuts |
| 8 | Learn Your Way "+11 pp *long-term* retention" | Real number, wrong framing: it is a 3–5-day test; and the day-3–5 gap mirrors the immediate gap (advantage forms at encoding, does not grow in consolidation); control is a digital PDF reader and the treatment embeds retrieval practice — confounds stated wherever quoted |
| 9 | "InfoCocoon: a multi-agent bubble-breaking system" | Not a system name — a PDF filename on a co-author's homepage; the CHI 2024 prototype has no proper name |
| 10 | "All four of Maes's 1994 example agents were consumption scenarios" | The CACM original lists email handling, **meeting scheduling**, news filtering, entertainment selection: three consumption, one task-side. Had survived three-vote verification; fell only when two independent external reviewers challenged it and we re-read the primary source. Lesson: when two independent challenges hit the same fact, re-verify against the original — do not cite your own verification record as a defense |
| 11 | "mem0 LoCoMo 92.5 with ~7K tokens per retrieval" | The score does not appear in the paper's abstract; two reviewers independently flagged it (public reporting clusters in the 60–70 range). Withdrawn to a qualitative vendor-reported statement. Lesson: the source table carried ⚠️, but a downstream document had silently upgraded it to ✅ — grades must never rise in transit |
| 12 | "Fishwrap kept a shared *'Daily We'* front page (1994)" | The shared community page is real (MIT News verified); the *name* is Sunstein's 2001 Boston Review title — an anachronism introduced in paraphrase. The contradicting evidence sat in our own reference list the whole time. Lesson: a quoted term plus a precise year is the highest-risk combination; named concepts must be cross-checked against the namer's original |

## 3. Major omissions caught and repaired

- **Amazon v. Perplexity injunction was stayed**: all research batches stopped at "preliminary injunction, 2026-03"; in fact the Ninth Circuit stayed it 2026-03-30 pending appeal, oral argument 2026-06-11, no ruling as of 2026-07-09. Without this, a reader concludes "the courts closed the door" — the door is in active litigation.
- **Instant Checkout's two successor routes were conflated** (ACP discovery + merchant-site checkout vs. in-chat merchant apps); now stated separately.
- **Cloudflare's 2026-09 default-blocking policy scope**: applies to new customers/new zones/free tier — not a retroactive network-wide switch.

## 4. Honest list: still unverified (quote with care)

Gartner "$30T machine customers by 2030" (second-hand chain) · Qwen app "120M orders in six days" (single source) · llms.txt "8.8× growth / 97% zero requests" (single trade-press source; direction corroborated) · Negroponte 1970s Architecture Machine Group primary texts (not page-verified) · the Cloudflare one-year-review 57.5% figure's precise locator (pending; the paper's body claims only "past half").

## 5. Why this file exists

The handbook and the position paper both argue that consumption agents must prove loyalty **with architecture, not promises** — auditable channels, logged decisions, appealable calls. The research process is held to the same standard: this ledger is the audit log, the falsifications above are the appeals that succeeded, and the correction history is public in this repository's commits (see the errata for Maes's prototypes, the mem0 score, and the "Daily We" attribution).

---

*Next: back to [Part 5 · Open Territory](05-open-territory.md), or the [README](../README.md).*
