# Deep Interview Context Snapshot: A-share Trading Assistant

## Task statement
User wants to design an A-share trading assistance helper. It should not execute trades directly; it should support decision-making.

## Desired outcome
A clarified, execution-ready specification and team-work configuration for a project that can collect market/news/research information, analyze stocks reasonably, and analyze stocks already held by the user.

## Stated solution
Initial capabilities mentioned:
- Crawl or ingest current affairs news, stock information, financial资讯, research reports, and other sources to be decided.
- Analyze stocks with reasonable, contextual logic.
- Analyze already-held positions.
- Use team work / multi-agent collaboration.
- Maintain a project Markdown file recording requirements, progress, changes, constraints, and decisions.
- Update AGENTS.md so every project advance follows and updates that project record.

## Probable intent hypothesis
User wants a controlled, auditable decision-support system for A-share investing, with clear boundaries against automated trading and with durable project memory so agents do not drift across iterations.

## Known facts/evidence
- Repository currently contains only `AGENTS.md`; no source, tests, package config, or valid Git metadata were found.
- Existing `AGENTS.md` is a contributor guide created for an empty/lightweight stock analysis workspace.
- Project is greenfield from an implementation perspective.

## Constraints
- No direct trading/execution.
- Requirements/progress/change/constraint tracking must be persisted in a Markdown project record.
- Future agent work should follow that record and update it.
- Information-source choices are intentionally unresolved.
- A-share context implies Chinese market data/news/report sources and likely compliance/financial-risk constraints.

## Unknowns/open questions
- Primary user outcome: monitoring, research summarization, position risk, buy/sell decision support, alerts, reports, or all of these.
- Information sources and licensing/API constraints.
- Analysis methodology and acceptable level of financial advice.
- User portfolio data format and privacy constraints.
- Team lanes and responsibilities.
- UI/UX and delivery surface.
- Frequency and latency requirements.
- Success criteria and evaluation method.

## Decision-boundary unknowns
- What the agent/team may decide without confirmation.
- Which data sources may be added or paid for.
- Whether recommendations can include explicit buy/sell language or only risk/opportunity summaries.
- Whether live APIs, web crawling, or manual uploads are acceptable.

## Likely codebase touchpoints
Future likely paths:
- `PROJECT.md` or `docs/project.md` for durable requirements/progress/change log.
- `AGENTS.md` update to require consulting/updating the project record.
- `src/stock_analyz/` for implementation.
- `tests/` and `tests/fixtures/` for validation.

## Prompt-safe initial-context summary status
not_needed
