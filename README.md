<h1><img src="https://emojis.slackmojis.com/emojis/images/1531849430/4246/blob-sunglasses.gif?1531849430" width="30"/> 
  
# Matías Iglesias

**Senior Data & AI Engineer building governed data systems, scientific infrastructure, and AI-enabled products that survive contact with real workflows.**

I work across software engineering, data engineering, applied AI, analytics, and empirical research. My strongest projects usually begin with fragmented data or ambiguous operational rules and end as something another person can actually inspect, run, validate, and use.

```text
messy problem
→ explicit boundaries and contracts
→ source-aware data / software pipeline
→ validation, provenance, and observability
→ decision surface, publication, or human handoff
```

My background combines engineering practice with a **PhD in Economics** and an **MSc in Physics**. I am most useful where software, data, research judgment, and operational reliability need to meet.

[Main site](https://main.matuteiglesias.link/) ·
[CV](https://main.matuteiglesias.link/docs/General/cv) ·
[Developer journal](https://journal.matuteiglesias.link/) ·
[Stack I actually use](https://github.com/matuteiglesias/awesome-automation)

## Current engineering surface

Recent work has concentrated on turning public-data and research pipelines into governed, reproducible systems rather than one-off analyses:

- **[IPC Argentina](https://github.com/matuteiglesias/IPC-Argentina)** now builds a source-backed national inflation consensus from a curated panel of official provincial series. The pipeline locks parser/source identities, preserves acquisition evidence, validates contributors independently, compares the new methodology against the historical series, and publishes immutable candidate releases behind an explicit maturity gate. Live adapters include exact parsing of Córdoba's official series and Neuquén's official calculator JSON API.
- **[samplerCensoARG](https://github.com/matuteiglesias/samplerCensoARG)** has been reworked around a vintage-neutral Census frame and deterministic household-selection kernel. It separates donor microdata custody from target-year population controls, supports governed 2024/2025 target-year releases, proves reference/streaming backend equivalence, and exposes a non-materializing planner so operators can validate sample plans before touching large local data.
- **[EPH Income Modeling](https://github.com/matuteiglesias/income-modeling-eph)** now has an exact durable EPH-parent intake boundary, a neutral analysis frame, household-grouped split primitives, and a governed reconstruction of the income-study cohort. Research semantics remain separate from Census scoring/runtime concerns.
- **[Accounting Workflows](https://github.com/matuteiglesias/accounting-workflows)** now carries transaction-evidence status into professional drill-downs through an optional validated sidecar, making linked, review-needed, and missing evidence visible instead of silently collapsing documentary uncertainty into accounting outputs.

That pattern—**source authority → explicit contract → deterministic transformation → independent checks → durable release or review surface**—is increasingly the common architecture across my public work.

## Selected systems

### [Matías Context MCP](https://github.com/matuteiglesias/matias-context-mcp)

A local, read-only MCP server and client that gives AI systems governed access to independent knowledge sources without exposing arbitrary filesystem access.

It uses logical resource identities, capability negotiation, explicit mappings, path-containment and symlink defenses, bounded reads, provenance-rich responses, structured failures, tests, and real client/server operation over `stdio`.

### [Atlas Económico de Argentina](https://github.com/matuteiglesias/atlas-economico-ar)

A reproducible economic-data and knowledge publication system for exploring questions, indicators, concepts, time series, and figures about the Argentine economy.

Its architecture separates semantic content and source measurements from compiled publication artifacts: economic contracts and series are validated, transformed into a static knowledge graph and figure corpus, and published through a Next.js read model. Human publication QA can mark technically valid evidence as historical or quarantine it from prominent surfaces without deleting provenance.

### [FCV Scientific Instrument / Africa Observability Lab](https://github.com/matuteiglesias/fcv-spatial-data-research-onboarding)

A multi-repository empirical research system designed to keep **source facts, reusable measurements, scientific use, and instrument calibration** separate.

The stack includes:

- [empirical-data-contracts](https://github.com/matuteiglesias/empirical-data-contracts) for typed identity, provenance, grain, coverage, measurement, QA, and run contracts;
- [spatial-data-foundation](https://github.com/matuteiglesias/spatial-data-foundation) for reusable geography, time indexing, spatial membership, and materialization provenance;
- [fcv-empirical-data](https://github.com/matuteiglesias/fcv-empirical-data) for source-native ACLED, investment, and DHS empirical products without experiment-role leakage;
- [fcv-experiment-harness](https://github.com/matuteiglesias/fcv-experiment-harness) for explicit experiment projection, gates, calibration, falsification, synthetic observability, and known-behavior commissioning.

The current system can characterize what its empirical design is capable of observing rather than treating every coefficient as a substantive result. The [onboarding surface](https://fcv-spatial-data-research-onboardin.vercel.app/) documents the scientific boundaries, evidence state, benchmark program, and collaboration model.

### [Accounting Workflows](https://github.com/matuteiglesias/accounting-workflows)

A Python/SQL accounting and analytical-data system that turns messy ledger evidence into governed semantic marts, debt and cash positions, reconciled treasury flows, metrics, drill-downs, and professional reports.

The system progressively replaces competing historical definitions with explicit typed authorities, preserves native-currency and stock-vs-flow semantics, reconciles downstream products to physical accounting motors, exposes residuals instead of hiding them, and protects those decisions with regression tests. Documentary evidence is now modeled as an optional validated relation rather than being conflated with ledger truth, so professional drill-downs can expose evidence coverage and review state explicitly.

### [Media Monitor](https://github.com/matuteiglesias/media_monitor)

A **deployed governed news-intelligence and editorial publishing system** for Argentina. Its public path is broader than “generate a draft”:

```text
source ingestion
→ immutable run artifacts and versioned contracts
→ deterministic indexes
→ AI-assisted editorial briefs / drafts
→ explicit human publication gate
→ published_article.v1
→ publication-aware site_snapshot.v2
→ request-time freshness health
→ guarded scheduled deployment
```

The public outlet deliberately separates monitored external-source signals from Media Monitor editorial analysis. A generated draft is never treated as publication authority, and “live/current” is not inferred from the existence of a URL: the public health surface owns freshness truth.

[Open the canonical outlet](https://mediamonitor-psi.vercel.app/) ·
[Check public health](https://mediamonitor-psi.vercel.app/api/health) ·
[Read the documentation](https://github.com/matuteiglesias/media_monitor/tree/main/docs)

### [Evaluar App](https://github.com/matuteiglesias/evaluar-app)

A production-shaped teaching and content platform built around immutable versioned exercises, complete course publications, course-scoped membership, Google OpenID Connect, deterministic content compilation, checksum-verified atomic publishing, optional tutoring/support workflows, PostgreSQL, and explicit operational readiness gates.

The project retains its older Flask implementation as characterized compatibility history while the packaged production runtime is Django.

## Public-data production systems

### [IPC Argentina](https://github.com/matuteiglesias/IPC-Argentina)

A governed inflation-series pipeline built from official Argentine provincial sources. The current v2 path separates source acquisition, locked parser identity, contributor eligibility, consensus construction, conversion, scientific comparison, release preflight, and publication. Candidate releases are immutable and source-backed; insufficient contributor maturity remains visible rather than being papered over.

### [samplerCensoARG](https://github.com/matuteiglesias/samplerCensoARG)

A bounded producer of deterministic Census household samples. Its newer frame architecture is feature-independent and vintage-neutral: Census identity and custody remain upstream of any EPH-compatible modeling projection. The same selection semantics can be exercised through reference and streaming backends, with explicit parity tests and target-population controls.

These components are part of a larger Census/EPH modeling path alongside [eph-censo-aligner](https://github.com/matuteiglesias/eph-censo-aligner) and [income-modeling-eph](https://github.com/matuteiglesias/income-modeling-eph). The important boundary is deliberate: sampling, semantic alignment, and modeling are separate authorities rather than one script that silently owns all three.

## Reusable libraries and infrastructure

### [empirical-data-contracts](https://github.com/matuteiglesias/empirical-data-contracts)

A **published Python package** for small, immutable contracts used by reproducible empirical-data systems. It deliberately describes identity, provenance, grain, geography/time, coverage, measurements, QA, and runs without importing pandas, GeoPandas, DuckDB, raster tooling, or source-specific semantics.

```bash
pip install empirical-data-contracts
```

### [spatial-data-foundation](https://github.com/matuteiglesias/spatial-data-foundation)

Reusable spatial/time infrastructure for research systems: geography authority, immutable source registration, GADM materialization, period indexing, auditable point membership, content hashes, QA, and run provenance.

### [KB Artifacts](https://github.com/matuteiglesias/kb-artifacts)

A deterministic, read-only evidence-selection and corpus-exploration package with typed JSON queries, source profiles, `describe/facet/count/sample` operations, provenance-rich manifests, staged atomic promotion, CLI and public API surfaces, and installed-distribution verification.

Together with [KB Contracts](https://github.com/matuteiglesias/kb-contracts), [Knowledge Inspect](https://github.com/matuteiglesias/knowledge-inspect), and Context MCP, these repositories form a governed knowledge path without collapsing source authority into one monolithic application. Knowledge Inspect also now includes bounded index/query consumers for speech-like text chunks, keeping retrieval identity explicit instead of hiding it behind an opaque application layer.

## Applied modeling and consulting cases

- **[EPH Income Modeling](https://github.com/matuteiglesias/income-modeling-eph)** — reproducible ML experiments for income prediction on Argentina's Permanent Household Survey, with exact parent-release intake, a neutral analysis frame, household-grouped splits, explicit target/feature contracts, leakage exclusions, guarded training runs, and evidence packaging.
- **[GitHub Stars Consulting Case](https://github.com/matuteiglesias/consulting-case-github-stars)** — a time-constrained analytics case that separates prediction, description, and interpretation; requires feature-timing review; and keeps the notebook as a thin presentation layer over validated artifacts.
- **[Bank Marketing Consulting Sprint](https://github.com/matuteiglesias/bank_marketing_consulting)** — a stage-gated analytical execution bundle from data audit through modeling and operational targeting policy, with explicit machine/human responsibility boundaries.

These are case-study surfaces, not substitutes for production systems or causal research claims.

## How I engineer systems

- **Small, reliable components over invented universal platforms.**
- **Source identity, contracts, and provenance over hidden assumptions.**
- **Bounded access and explicit authority over convenient overexposure.**
- **Tests, gates, run records, and evidence over undocumented success.**
- **Human-reviewable handoffs over opaque automation.**
- **Explicit non-goals when a problem is not yet justified or identified.**

## Research depth

Research is part of my foundation, but not the organizing principle of this profile.

- **[PhD thesis portal](https://thesis.matuteiglesias.link/)** — long-form evidence of original economic research and sustained analytical work.
- **[Concentration Is Not Scaling](https://github.com/matuteiglesias/concentration-is-not-scaling)** — a reproducibility repository with formal results, deterministic demonstrations, identity tests, manuscript builds, and release artifacts.
- **Earlier economic-geography tools:** [geo-correlation-structures](https://github.com/matuteiglesias/geo-correlation-structures), [pRCA](https://github.com/matuteiglesias/pRCA), and [spatial-coexistence-metrics](https://github.com/matuteiglesias/spatial-coexistence-metrics).

My academic path includes research experience at the **Harvard Kennedy School Growth Lab** and **Caltech**, alongside applied work in economics, public data, spatial analysis, and government data systems.

## Teaching and public-service products

I teach computer science and data-oriented university courses at the University of Buenos Aires.

- **[Egreso LCD](https://github.com/matuteiglesias/egreso-lcd)** — a deterministic guidance product for the final academic/administrative journey of the FCEN-UBA Data Science degree, driven by versioned evidence and journey-state contracts rather than a chatbot.
- **[SQL Static Trainer](https://github.com/matuteiglesias/sql-trainer)** — a small browser-only SQLite practice application with deterministic evaluation and local progress.
- **[Computational Linear Algebra](https://github.com/matuteiglesias/labo-algebra-lineal)** — notebooks, datasets, exercises, and laboratory material connecting numerical linear algebra with practical computation.

## Stack

Core working tools include **Python, SQL, Bash, pandas, scikit-learn, REST APIs, LLM APIs, MCP, JSON Schema, SQLite/PostgreSQL, BigQuery, FastAPI/Django/Flask, Docker, GitHub Actions, React/Next.js, Docusaurus/VitePress, and Vercel**.

For the longer evidence-backed inventory, see **[Awesome Automation I Actually Use](https://github.com/matuteiglesias/awesome-automation)** — a field-tested catalog tied back to public repositories and engineering notes rather than a keyword list.

## Contact

Buenos Aires, Argentina · English and Spanish

[LinkedIn](https://www.linkedin.com/in/matiasiglesias/) ·
[GitHub](https://github.com/matuteiglesias) ·
[Email](mailto:matuteiglesias@gmail.com)
