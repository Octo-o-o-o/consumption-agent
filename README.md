# Consumption Agents

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21274081.svg)](https://doi.org/10.5281/zenodo.21274081)

**The missing half of the AI agent landscape.**

> Production agents change the state of the world.
> Consumption agents change your interface to it.

*First published: 2026-07-09. This repository names and maps a category that, as of four independent literature searches (July 2026), no one has yet named.*

---

## The claim

Every AI agent you have heard of — coding agents, data agents, general assistants — is a **production agent**: intent goes in, an artifact comes out, and the world has one more thing in it. The better they get, the deeper we drown in their output.

The missing half is the **consumption agent**: it adds no new information to the world. It takes what already exists — articles, reports, feeds, and the output of production agents — and performs **selection, transformation, and orchestration** so that it fits *this person, in this moment*: their goal, their time, their device, their cognitive state. It helps you digest the world, or shields you from it.

It represents your **attention**, not your wallet.

The way we consume content is still industrial: an author produces one version, everyone consumes the same version, and the entire cost of adaptation is paid in human attention — skimming, abandoning, doomscrolling. Consumption agents flip this. **Content is source code; you are the target platform; the agent is a just-in-time compiler** — meaning is produced once, and the experience is compiled at the moment of consumption: a podcast segment for the commute, a one-screen brief between meetings, a conversation you can interrupt. Used once, discarded, recompiled differently tomorrow.

Recommendation algorithms decide *what* you see. Consumption agents decide *how* you see it — and they answer only to you.

## The test

"Does it generate tokens?" is not the dividing line — consumption agents generate plenty (summaries, audio, ephemeral interfaces). The real test is three properties of the *output*:

1. **Audience test** — is the output made for the public record (production), or for one person in one moment (consumption)?
2. **Lifetime test** — must it stay correct and citable (production), or is it disposable by design — legitimately different tomorrow (consumption)?
3. **Information test** — does the world gain a new piece of information (production), or does the same information gain a better fit to one mind (consumption)?

And four properties of the *agent*: it adds no information; its input includes the person's current state; its loyalty runs to the consumer; and it has **the right to say no** — to filter, block, or advise you not to look. Platform-owned agents structurally fail the last two.

By this test: the spam filter was the first mass-deployed consumption agent (all four properties, minimal intelligence). TikTok's For You feed is a consumption agent — *owned by the platform, not by you*. NotebookLM is close, but covers only transformation. The complete, resident, user-loyal stack — selection + transformation + orchestration — does not yet exist, commercially, in open source, or in academia.

## What this is not

- **Not agentic commerce.** A shopping agent represents your purchasing decisions; a consumption agent represents your attention and cognitive bandwidth. Shared infrastructure, different species.
- **Not the BI "consumption agent."** Vendor docs use the phrase for querying semantic models. Unrelated.
- **Not another summarizer.** Compression is one knob among seven (form, density, perspective, timing, interactivity, context-linking, accessibility) — and the knobs turn both ways. Sometimes the right rendering is *slower and harder* than the original. A consumption agent is a dietitian, not a juicer.

## The hard part: loyalty

Whoever pays the agent decides what it optimizes when it renders the world for you. Ad-funded rendering layers degrade into slot machines — we ran that experiment for twenty years; it is called the feed. User-funded, on-device, auditable is the only soil where an agent loyal to *you* can grow — and it is precisely the thing attention-monetizing incumbents structurally cannot build.

Money is only half of it. An agent that learns from your behavioral signals alone (what you tap, what you skip) is running the same gradient as engagement optimization, whoever pays. Loyalty has to be audited on **two channels: where the money flows, and what signals the model learns from.**

## The handbook

The full argument, in seven parts — adapted into English from an evidence-graded research base (six parallel research batches, adversarial verification, a falsification ledger; facts as of 2026-07-09). Each part is self-contained and independently citable:

| | Part | What it covers |
|---|---|---|
| 0 | [The Twelve Takeaways](handbook/00-twelve-takeaways.md) | the five-minute layer — every load-bearing claim, graded |
| 1 | [The Concept](handbook/01-the-concept.md) | definition, the three-test/four-trait criterion, the capability stack, three metaphors, loyalty (four archetypes, two channels), boundaries, the name |
| 2 | [The Case](handbook/02-the-case.md) | eighty years of lineage, why now, the empirical base, the naming vacancy |
| 3 | [The Landscape](handbook/03-the-landscape.md) | the product map, the casualty list, open-source bricks, the academic map, protocols & economics |
| 4 | [Risks and Red Lines](handbook/04-risks-and-red-lines.md) | eleven risks (each: evidence + counter = differentiation), eight non-negotiables |
| 5 | [Open Territory](handbook/05-open-territory.md) | seven vacancies, attention-ROI metrics, the artifact contract, seven research gaps |
| 6 | [Architecture Notes](handbook/06-architecture-notes.md) | the render function, the semantic materialization layer, direct vs. paired mode, a draft artifact contract |

Reading paths: 60 seconds — this page. Five minutes — Part 0. The whole case — Parts 1→6.

## Status & roadmap

- [x] Name the category, state the test *(this page, 2026-07-09)*
- [x] The handbook — full English adaptation in seven parts *(2026-07-09)*
- [ ] Position paper (interface-agent + sensemaking lineage)
- [ ] A small public benchmark for consumption quality (attention ROI, cross-modal fidelity, form-preservation)

## Citation

If you reference this framing, please cite (or use GitHub's "Cite this repository" button):

```
Yixiao Wang. Consumption Agents: The Missing Half of the AI Agent Landscape.
DOI: 10.5281/zenodo.21274081. https://github.com/Octo-o-o-o/consumption-agent,
first published 2026-07-09.
```

---

*Text licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — attribution required, reuse welcome.*
