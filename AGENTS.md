# Repository Guidelines


## Project Governance
在本 A 股交易辅助项目中，任何讨论、规划、代码修改或评审开始前，必须先读取 `PROJECT.md` 和 `docs/roles/` 下相关角色文档，并把它们视为当前项目记忆与角色契约。

每次产生有意义的变更或决策后，必须同步更新 `PROJECT.md` 和受影响的角色文档，记录新增需求、进展、约束、决策、开放问题和验证证据。不要只依赖聊天记录保存项目状态。

角色文档定义每条泳道要做什么、怎么做、做到什么质量、不能做什么。只要任务涉及某个角色，工作开始前必须读取该角色文档；角色契约变化时必须更新对应文档。

## Project Structure & Module Organization
This repository is currently a lightweight workspace for stock analysis work. Keep implementation code under `src/stock_analyz/` and mirror test coverage under `tests/`. Store notebooks or exploratory scripts in `notebooks/`, reusable data-processing utilities in `src/stock_analyz/`, and generated outputs in `reports/` or `artifacts/`. Keep raw or large market datasets out of Git; use `data/raw/` locally and commit only small fixtures under `tests/fixtures/`.

Example layout:

```text
src/stock_analyz/      # package modules
tests/                 # pytest tests
tests/fixtures/        # small deterministic sample data
notebooks/             # exploratory analysis, not production logic
```

## Build, Test, and Development Commands
No project build files are present yet. When adding Python code, prefer these standard commands and document any changes here:

- `python -m venv .venv && source .venv/bin/activate` — create and enter a local virtual environment.
- `pip install -e .[dev]` — install the package and developer tools once `pyproject.toml` exists.
- `pytest` — run the full test suite.
- `ruff check .` and `ruff format .` — lint and format Python code if Ruff is configured.

## Coding Style & Naming Conventions
Use Python 3, 4-space indentation, type hints for public functions, and concise module names such as `prices.py`, `signals.py`, or `portfolio.py`. Use `snake_case` for functions, variables, files, and test names; use `PascalCase` for classes. Keep analysis logic in importable modules instead of notebooks so it can be tested.

## Testing Guidelines
Use `pytest` for new tests. Name files `test_<module>.py` and tests `test_<behavior>()`. Prefer deterministic fixtures over live market API calls. If external data access is required, isolate it behind mocks or adapters and include small fixture CSV/JSON files in `tests/fixtures/`.

## Commit & Pull Request Guidelines
No usable Git history is available in this workspace. Use concise, intent-focused commit messages and include validation evidence. Follow the project Lore style when possible: explain why the change was made and add trailers such as `Tested: pytest` and `Not-tested: live broker/API integration`.

Pull requests should include a short summary, changed paths, test results, linked issues, and screenshots or sample report output when visual artifacts change.

## Security & Configuration Tips
Never commit API keys, brokerage credentials, or private datasets. Read secrets from environment variables or ignored local config files, and provide safe examples such as `.env.example` when configuration is needed.
