# Role Docs Index

本目录定义 A股交易辅助帮手 V1 的角色职责、流程、产物、边界与维护协议。

## 使用规则
每次涉及某个角色的讨论、规划、代码或评审前，必须先读取：
1. `PROJECT.md`
2. 本索引
3. 对应角色文档

若讨论产生新职责、流程、边界、产物或验收标准，必须同步更新对应角色文档。

## 角色列表
- `product-requirements-owner.md` — 产品 / 需求负责人
- `macro-market-source-researcher.md` — 宏观市场数据源研究员
- `sector-theme-source-researcher.md` — 板块 / 方向数据源研究员
- `data-engineering-executor.md` — 数据工程执行者
- `analysis-model-designer.md` — 分析模型设计者
- `safety-compliance-reviewer.md` — 安全 / 合规审查者
- `test-verification-engineer.md` — 测试 / 验收工程师

## 全局禁止项
- 不自动交易，不接入下单能力。
- 不做未确认的数据源接入。
- 不绕过人工确认 gate。
- 不输出无证据、无不确定性、无审计记录的评分结论。
