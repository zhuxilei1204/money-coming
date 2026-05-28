# A股交易辅助帮手项目记录

## 当前目标
构建 A 股交易辅助帮手 V1：优先做信息聚合摘要，在严格安全护栏下输出评分式方向倾向；不自动交易。

## 当前阶段
角色与功能细化阶段。当前已完成 deep-interview 与 ralplan 共识规划，下一步围绕每个角色持续细化职责、流程、产物与边界。

## 事实源与规划产物
- Deep Interview Spec: `.omx/specs/deep-interview-a-share-assistant.md`
- PRD: `.omx/plans/prd-a-share-assistant-role-detail.md`
- Test Spec: `.omx/plans/test-spec-a-share-assistant-role-detail.md`
- Handoff: `.omx/plans/handoff-a-share-assistant-role-detail.json`
- Role Docs: `docs/roles/`

## 全局约束
- 不自动交易，不接入下单或券商订单 API。
- V1 不覆盖全 A，不接入付费源，不做实时高频。
- 买卖倾向只能以评分方式表达，不输出命令式、二元化买卖建议。
- 每个评分必须包含证据、不确定性、适用前提、失效条件、免责声明、审计字段和人工确认提示。
- 技术栈、具体数据源、评分公式、首版交互形态在实现前必须确认。

## 工作协议
每次讨论、规划或编码前：
1. 读取本文件。
2. 读取相关角色文档：`docs/roles/*.md`。
3. 若修改了范围、职责、流程、约束、验收标准或产物要求，必须同步更新本文件和相关角色文档。

每次工作结束前：
1. 在“进展记录”追加日期、事项、影响文件、待确认问题。
2. 保持新决策可追溯到来源或用户确认。

## 待确认问题
- 首版技术栈与目录结构。
- 实际接入的数据源与优先级。
- 评分区间、权重、阈值和展示模板。
- 持仓数据输入格式。
- 首版交互形态。

## 进展记录
- 2026-05-28: 完成 deep-interview，明确 V1 为信息聚合摘要，允许评分式倾向但禁止自动交易。
- 2026-05-28: 完成 ralplan，形成角色职责、V1 功能清单、测试规格和 handoff。
- 2026-05-28: 创建 `PROJECT.md` 与 `docs/roles/` 角色文档体系，更新 `AGENTS.md` 治理要求。
- 2026-05-28: 初始化 Git 上传准备，新增 `.gitignore`；保留可追溯规划产物，排除 `.omx` 运行日志/状态、本地环境、密钥文件和私有原始数据。
