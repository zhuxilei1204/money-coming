# Deep Interview Transcript: A-share Trading Assistant

## Metadata
- Profile: standard
- Context type: greenfield
- Final ambiguity: 14.6% (threshold: 20%)
- Context snapshot: `.omx/context/a-share-assistant-20260528T120757Z.md`

## Rounds
1. Core v1 scenario: user selected **information aggregation summary**.
2. V1 non-goals: no automated trading, no full-market coverage, no paid data sources, no realtime/high-frequency monitoring.
3. Decision autonomy: agents may autonomously research free source candidates, create/maintain governance docs, and create tests/fixtures. Tech structure and output templates require confirmation.
4. Output boundary pressure pass: v1 may include buy/sell leaning, but still no automated trading.
5. Safety guardrails: require evidence citations, uncertainty, held/not-held separation, human confirmation, disclaimer, audit log, and scored rather than binary/verbal buy/sell advice.
6. Team lanes: include product/requirements, data source research, data engineering, analysis design, safety review, and test verification. Split data-source research into macro-market and sector/theme source lanes.

## Pressure Pass Finding
The interview revisited the earlier non-goal decision around “strong buy/sell advice.” The resolved boundary is: scored directional leaning is allowed, but binary or imperative advice is not; every score must carry evidence, uncertainty, and human-confirmation framing.
