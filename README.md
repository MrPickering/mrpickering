# Agentic systems that prove their work

I’m Mark Pickering, the engineer and systems architect behind [PickBits](https://pickbits.ai/). I build local-first, human-gated systems for research, software, media, education, and games.

The common pattern is simple:

**evidence → decision → production → verification → human approval → publish**

Different parts of the portfolio have reached different levels of maturity. Released tools, public previews, and work still being extracted are labeled separately below.

| If you are here to… | Start here |
| --- | --- |
| inspect the architecture, use the tools, or collaborate on agent infrastructure | **Stay on GitHub.** |
| learn to build and operate with AI, follow the research, or work with me | **[PickBits.ai](https://pickbits.ai/)** — University, CyberHawk, field notes, and consulting. |
| play the games or explore the creative work | **[PickBits.studio](https://pickbits.studio/)** — games, a book, art, and engine notes. |

<p align="center">
  <img src="./assets/pickbits-universe.gif" width="100%" alt="The PickBits universe: authoring and asset engines feed production systems, pass through a human operator gate, and reach public sites and store targets">
</p>

## The PickBits universe

PickBits is one operating environment made of deliberately separate systems:

- **Knowledge and decision engines** — Newsroom turns sourced reporting into evidence-backed editorial slates; University maintains research, lessons, outcomes, and skills; Infinite Arcade makes human-authorized product and experiment decisions; Silent Guardian and Weaver manage long-form narrative state.
- **Production engines** — Warehouse turns approved contracts into text, images, audio, video, and distribution packages. Game Dev and Asset Factory handle playable builds and manifest-driven art.
- **Operations and authority** — Company OS observes projects, schedules, and drift. Side effects stay behind explicit gates; publishing and connected-account actions require a human decision.
- **Public surfaces** — [PickBits.ai](https://pickbits.ai/) publishes the company, [University](https://pickbits.ai/university/), and [CyberHawk](https://pickbits.ai/cyberhawk/). [PickBits.studio](https://pickbits.studio/) publishes the [games](https://pickbits.studio/games/), [book](https://pickbits.studio/book/), and creative portfolio.

The systems do not all share one finished runtime yet. The point of the current open-source work is to extract the reusable loops without publishing private content, accounts, brand assets, or operating history.

## Open source you can inspect now

| Project | What is different about it | Verified state |
| --- | --- | --- |
| [Company OS](https://github.com/pickbitsai/company-os) | Builds a safe operational view across many local projects without centralizing their source or private contents. | Public source; consumer install and cross-platform CI verified; registry package pending |
| [Weaver](https://github.com/pickbitsai/weaver) | Treats narrative knowledge as derived state: revise an earlier scene and the affected downstream state becomes stale before the next release. | Public source; GitHub install and cross-platform CI verified; [quick-start update in review](https://github.com/pickbitsai/weaver/pull/1) |
| [Session Index](https://github.com/MrPickering/session-index) | Finds and resumes local Codex and Claude Code sessions without an account, telemetry, or cloud database. | Public, MIT, dependency-free at runtime |
| [PickBits Dependency Audit](https://github.com/pickbitsai/pickbits-dependency-audit) | Persists dependency evidence and prepares remediation requests without silently granting an agent patch authority. | Public, MIT; report, evidence store, admission audit, and tests run today |

Two more extractions are not being presented as finished releases:

- [Sprite Generator](https://github.com/pickbitsai/sprite-generator/pull/1) is in public release review with deterministic and known-bad visual identity fixtures.
- [enView](https://github.com/MrPickering/enView) has a working source tree and local test suite, but its npm package has not been published yet.

The detailed [open-source readiness scorecard](./docs/open-source-readiness.md) records what is proven, what remains coupled to the private production environment, and the evidence required before each release.

## Ideas I want to build in public

These are not new names for generic “multi-agent” wrappers. They are reusable patterns that emerged from operating PickBits:

- **Derived-state invalidation outside software builds.** Weaver already applies build-graph thinking to narrative continuity. The same pattern can protect curriculum, editorial research, and other knowledge products from silently stale downstream artifacts.
- **Evidence without authority.** A scanner or agent may collect facts, preserve a receipt, and propose a change without gaining permission to execute that change. PickBits Dependency Audit is the first public implementation of this boundary.
- **Proof-carrying handoffs.** A portable work receipt should identify the subject, contract version, source references, retry identity, requested outputs, verification evidence, and operator decision. Pieces exist across Newsroom, University, Warehouse, and Asset Factory; the shared contract is the next extraction.
- **Visual completion as a testable claim.** Generated art is not “done” because files exist. The reusable loop is manifest → generation → installation → runtime/render proof → human verification → receipt.

The static [Loop Atlas](./assets/agentic-systems-map.svg) shows how those ideas map across the current systems.

## The release bar

A flagship extraction should let a stranger:

1. install it outside the PickBits machine;
2. inspect its inputs, outputs, authority, retries, and stop conditions;
3. run a sanitized end-to-end example;
4. see both a good fixture pass and a deliberately bad fixture fail at the right gate; and
5. inspect the resulting artifacts and receipts.

If you are building serious agent workflows and want to test an extraction, contribute an adapter, or challenge an eval, [open an issue](https://github.com/MrPickering/mrpickering/issues).

---

**Contracts over vibes. Evidence over confidence. Human authority where consequences begin.**
