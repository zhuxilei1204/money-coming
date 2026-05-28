# Deep Interview Spec: A-share Trading Assistant

## Metadata
- Profile: standard
- Context type: greenfield
- Final ambiguity: 14.6% (threshold: 20%)
- Context snapshot: `.omx/context/a-share-assistant-20260528T120757Z.md`
- Transcript: see latest `.omx/interviews/a-share-assistant-*.md`

## Intent
Build an A-share decision-support helper that starts with reliable information aggregation and summaries, then uses that evidence to assist analysis. It must not trade automatically, but may express scored buy/sell leaning under strict guardrails.

## Desired Outcome
V1 should ingest or prepare to ingest free/authorized sources for news, market information, announcements, research-report-like materials, macro market movement, and sector/theme information. It should produce traceable summaries and analysis-ready outputs for a limited watchlist/portfolio scope.

## In Scope for V1
- Information aggregation and summary as the primary product goal.
- Free or already-authorized data-source candidate research.
- Limited coverage: user holdings, watchlist, or selected sectors/themes; not all A-shares.
- Held-position-aware analysis path, including cost/position/risk context when data is provided.
- Scored directional leaning, not binary/imperative buy/sell wording.
- A durable project Markdown record, recommended as `PROJECT.md`, tracking requirements, progress, decisions, changes, constraints, and open questions.
- `AGENTS.md` must be updated in a later execution step to require every future agent/project iteration to consult and update `PROJECT.md` before/after work.

## Out of Scope / Non-goals
- No automated trading or order placement.
- No full-market coverage in V1.
- No paid data sources in V1 unless later explicitly approved.
- No realtime/high-frequency monitoring; prefer daily or intraday-batch cadence.
- No untraceable conclusions or unsupported investment claims.

## Decision Boundaries
Agents/team may decide autonomously:
- Candidate research for free/authorized data sources.
- Governance documentation structure and updates (`PROJECT.md`, AGENTS constraints).
- Offline test fixtures, mocks, and validation examples.

Require user confirmation before implementation:
- Final technology stack and repository structure.
- Actual data-source integration choices.
- Summary/analysis templates and scoring formula.
- Any expansion beyond free sources, limited coverage, or non-realtime cadence.

## Mandatory Safety / Analysis Guardrails
Every scored leaning must include:
- Evidence source and timestamp.
- Uncertainty, confidence, counter-evidence, and data gaps.
- Different handling for held vs not-held stocks.
- Human-confirmation language: final decision remains with the user.
- Disclaimer: not investment advice, no return guarantee, no automatic trading.
- Audit log: inputs, source snapshots, analysis version, output, timestamp.
- Scored output rather than binary or imperative “buy/sell” language.

## Team Work Configuration
Recommended lanes:

1. **Product / Requirements Owner**
   - Owns `PROJECT.md`, scope, change log, acceptance criteria, and AGENTS governance.
   - Output: updated project record, requirement diffs, decision log.

2. **Macro Market Source Researcher**
   - Researches market-wide/news/macro/broad-index information sources.
   - Output: source candidates, access limits, update cadence, reliability notes.

3. **Sector / Theme Source Researcher**
   - Researches industry, concept, theme, and board-level data/news sources.
   - Output: source map by sector/theme, feasibility and caveats.

4. **Data Engineering Executor**
   - Designs ingestion, parsing, deduplication, storage, and update jobs after source confirmation.
   - Output: testable ingestion modules and traceable raw/normalized records.

5. **Analysis Model Designer**
   - Designs summary fields, evidence chain, risk/opportunity labels, scored leaning, and held/not-held analysis rules.
   - Output: analysis schema and scoring proposal for user confirmation.

6. **Safety / Compliance Reviewer**
   - Verifies no auto-trading, required disclaimers, human-confirmation framing, auditability, and scored non-binary wording.
   - Output: safety checklist and review findings.

7. **Test / Verification Engineer**
   - Creates offline fixtures, mocks, regression checks, and acceptance examples.
   - Output: pytest-style test plan and fixture set.

## Testable Acceptance Criteria
- `PROJECT.md` exists and records requirements, progress, decisions, changes, constraints, and open questions.
- `AGENTS.md` contains a rule requiring future work to consult/update `PROJECT.md`.
- Data-source candidate report separates macro-market and sector/theme sources.
- V1 source research excludes paid sources unless explicitly approved.
- Analysis output examples include evidence, uncertainty, held/not-held distinction, disclaimer, audit fields, and scored leaning.
- No code path places trades or connects to brokerage order execution.
- Tests use offline fixtures/mocks rather than live paid/realtime sources.

## Recommended Handoff
Use `$ralplan` next to turn this spec into PRD + test-spec artifacts. After planning approval, use `$team` for coordinated execution because the task has distinct product, source-research, data, analysis, safety, and test lanes.
