# Open-source readiness: extraction, not repository flipping

Snapshot: **2026-07-26**

The private PickBits repositories are production systems, not clean-room examples. Opening a repository is not the same as releasing a reusable engine. The goal is to extract the smallest honest loop, prove it outside the PickBits machine, and keep production data, accounts, content, and operating history behind the boundary.

## The release bar

A flagship public loop is ready when a stranger can:

1. install it in a blank project;
2. inspect a machine-readable graph of states, edges, retries, stops, and authority;
3. run a sanitized end-to-end example without PickBits credentials or sibling repositories;
4. see deterministic happy-path evidence and a deliberately bad fixture rejected by the right gate;
5. distinguish agent authority, human authority, and external side effects;
6. verify CI, license, security policy, contribution path, dependency audit, and publish-set leak scan; and
7. inspect structured receipts plus cost, latency, retry, intervention, and failure metrics.

The interoperability direction is established practice, not a private vocabulary:

- [OpenTelemetry](https://opentelemetry.io/docs/concepts/signals/) for traces, metrics, and structured logs;
- [SLSA provenance](https://slsa.dev/spec/v1.2/provenance) for verifiable artifact origin; and
- [OpenSSF Scorecard](https://www.scorecard.dev/) as a reference for repeatable open-source security checks.

These are design targets, not claims of certification.

## Current public baseline

| System | What is proven | Remaining depth |
| --- | --- | --- |
| [Weaver](https://github.com/pickbitsai/weaver) | Story-agnostic engine, loop contract, rejection paths, deterministic tests, clean consumer install, MIT/security/contribution docs, and green cross-platform CI | OpenTelemetry export and signed release receipts |
| [Company OS](https://github.com/pickbitsai/company-os) | Public source, portable build, leak scan, 22 tests, and a clean consumer install across Node 18/20/22 on Linux, macOS, and Windows | Merge the consumer-release gate, publish the package, then add cross-project loop telemetry |
| [Sprite Generator](https://github.com/pickbitsai/sprite-generator/pull/1) | Public extraction, explicit visual loop, known-good and known-bad identity evidence, clean consumer install, zero production advisories, 44-file package boundary, and green Node 20/22 CI on three operating systems | Merge the extraction and publish the package; provider-backed evals remain opt-in because they incur cost |

## Evidence from the private systems

This is a read-only structural scan of tracked files and repository metadata. “Host-coupled” means a tracked text file contains an absolute workstation path. “Environment-aware” means a file references an environment API; it does **not** mean a secret was found. Test counts are filename-based indicators, not coverage claims.

| System | Tracked shape | Existing proof surface | Why the repository cannot simply be made public |
| --- | --- | --- | --- |
| **Warehouse** | 6,135 tracked files; 4,806 (78%) are under `cyberhawk/` or generated `editions/`; 456 host-coupled files; 99 environment-aware files | CI exists; 13 test-like files; governance and typecheck commands; explicit human approval and dispatch rules | Runtime, brand media, published output, connected-account routing, provider operations, and a Node/Python/Remotion toolchain share one production floor. The package is private and has no public license, security policy, or contribution guide. |
| **Newsroom** | 377 tracked files; 228 (60%) are under `editions/` or `pickbits-daily/`; 107 scripts; 20 host-coupled files; 18 environment-aware files | Boundary, provenance, retrieval, scoring, gating, and repair commands exist | Corpus, editorial history, stores, model/provider access, and operating paths are still coupled. There is no CI, public license/security/contribution surface, or named test suite demonstrating deterministic rejection behavior. |
| **Infinite Arcade** | 74 tracked files; 43 (58%) are campaign, contract, dev-culture, GTM, or launch-readiness records; 15 host-coupled files; 4 environment-aware files | Five test-like files; contract validation/shipping; an explicit human-authorized scheduling loop | The repository itself says automated ingestion, gaming RAG, trend scoring, scheduled slate production, persona support, attribution, and continuous reprioritization are not live. Publishing the whole control room would expose business state while overstating the engine. |
| **University** | 697 tracked files; 460 (66%) are curriculum content; 47 audits; 46 scripts; 30 host-coupled files; 31 environment-aware files | Five test-like files; research-first contract; source sidecars; outcome, skill, freshness, and premium-leak gates | The reusable curriculum machinery is mixed with proprietary lessons, paid-tier policy, source corpus, preview output, and the PickBits.ai release path. There is no standalone package, CI, public license/security/contribution surface, or fictional course fixture. |

## The extraction gap

### 1. Infinite Arcade: publish the decision contract, not the unfinished platform

**Extract first:** a small `arcade-decision-loop` package containing the IA-A/IA-B schemas, validation, a synthetic game portfolio, human authorization, experiment state, and feedback receipts.

**Keep private:** campaigns, real games and launch verdicts, account schedules, community/channel configuration, attribution data, and cross-repository task runners.

**Exit proof:** one evidence → decision → authorization → experiment → feedback replay; a bad-evidence fixture; a missing-human-approval fixture; no external write adapter enabled by default. Do not claim the ingestion, RAG, trend, persona, or attribution systems until they exist and have evaluations.

### 2. Newsroom: separate the editorial kernel from the operating corpus

**Extract first:** a `newsroom-core` package for normalization, deduplication, provenance, retrieval, scoring, critique, repair/escalation, and slate approval behind store and model interfaces.

**Keep private:** the live corpus, editorial history, source accounts, production slates, dossiers, analytics, and Warehouse handoffs.

**Exit proof:** a synthetic corpus with labeled duplicates and unsupported claims; deterministic provenance and dedupe evals; model and in-memory adapters; a replayable slate receipt; CI on every supported runtime.

### 3. University: publish the curriculum compiler, not the curriculum

**Extract first:** a `curriculum-compiler` package for source sidecars, freshness checks, lesson/outcome/skill joins, approval state, package builds, and access-boundary validation.

**Keep private:** PickBits lessons, paid material, source corpus, pricing/tiering decisions, generated previews, and production publishing.

**Exit proof:** a fictional course fixture; stale-source, broken-skill-join, and premium-leak failures; a clean package build; a human approval interrupt; an adapter boundary for retrieval.

### 4. Warehouse: extract last, after upstream contracts stabilize

**Extract first:** a `warehouse-runtime` package with contract schemas, an allow-listed pipeline executor, artifact receipts, independent verification, approval state, and adapter interfaces. Use synthetic text, image, audio, and video fixtures.

**Keep private:** Asset Factory, brand kits, editions, real media, provider accounts, connected destinations, publishing schedules, performance history, and partner operations.

**Exit proof:** a synthetic contract → production → verification → human approval → fake distribution replay; known-bad rights, evidence, and provider-failure fixtures; no network side effect without an explicitly supplied adapter.

Warehouse is the eventual flagship because it composes the other contracts. It should not be the first extraction: publishing it before Newsroom and University stabilize their public contracts would freeze production coupling into the API.

## Sequence

**Infinite Arcade → Newsroom → University → Warehouse**

That order follows dependency and blast radius:

- Arcade is the smallest honest loop and forces the authority model to be crisp.
- Newsroom establishes evidence, provenance, and repair contracts.
- University reuses those source/provenance ideas while adding content-access boundaries.
- Warehouse consumes upstream contracts and carries the largest side-effect and data-exposure surface.

The portfolio claim is earned repository by repository: executable examples, visible failure behavior, and evidence that survives outside the machine that created it.
