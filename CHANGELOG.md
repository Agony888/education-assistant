# CHANGELOG

## v2.7.0 Adaptive Guidance

- 新增 `knowledge/adaptive-guidance-bank.md`，根据阻断程度、路径影响、冲突和信息增益动态选择下一问。
- 引导式不再机械问完固定清单；用户回答改变研究类型、数据条件或研究中心时，会更新后续问题。
- 新增 `templates/research-decision-log-template.md`，记录关键决定、备选方案、排除原因和状态。
- 新增决策变更传播：研究对象、核心概念、研究问题、研究类型或数据条件变化时，同步检查下游题目、理论、方法、工具和目录。
- 新增 `templates/session-checkpoint-template.md`，支持 `保存进度` 和 `恢复进度`。
- 检查点采用可复制 YAML，不声称在外部后台永久保存会话。
- 新增 `knowledge/output-profiles.md`，支持 `outline`、`standard`、`submission-ready` 和 `review-ready` 四种成果档位。
- 材料不能支持目标档位时，自动降级并说明原因。
- 更新 `SKILL.md`、`AGENTS.md`、README、使用说明、提示词手册、调用示例和 manifest。
- 当前清单：21 个模板、14 个知识库、11 个模式、4 条工作流、2 种入口、4 种成果档位。

## v2.6.1 Guided Workflow Entry

- 完整任务新增用户可选入口：`guided` 引导式与 `direct` 直接式。
- 引导式每轮只询问一个关键问题，逐步形成工作流输入包后再执行完整流程。
- 直接式使用现有材料立即执行用户所选工作流的全部阶段，明确标注缺失信息、暂定输入和必要假设。
- 明确“直接执行全部阶段”不是同时运行四条不同目标工作流。
- 明确引导式与直接式调用同一条目标工作流，不改变阶段、质量标准和最终交付物。
- 新增 `templates/guided-intake-template.md`。
- 强化 `workflow-state-template.md`，记录入口选择、输入包、入口切换和假设。
- 支持 `查看进度`、`修改`、`跳过`、`不确定`、`直接生成`、`重新开始` 和 `结束引导`。

## v2.6.0 Workflow Edition

- 新增 `workflow` 模式，支持单篇入库、文献综述、开题设计和论文设计四条连续流程。
- 新增阶段状态、质量门槛、中间产物和交接数据模板。
- 新增证据与来源忠实协议。
- 新增研究类型分流规则。
- 重写论文解析、综述、方法、开题和论文设计核心模板。
- 强化研究问题—数据—方法—分析—章节对齐。

## v2.5.1 Prompt Manual

- 新增 `docs/prompt-manual.md`。
- 将完整提示词手册纳入项目文档。
