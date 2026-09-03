# octo-test

考试用的公开需求池与产品管家 Agent 配套仓库。

## 目标
为 `octo-server` 项目提供一套可在 Octo 群聊中工作的产品管理 Agent 体系，支持：

- 产品功能问答
- Bug / Feature / Question / Task 归档
- 基于 GitHub Issues 的需求池管理
- PRD 草稿生成与 review 流转
- 定时巡检需求池变化
- 仅在有变化时回报到考试群

## 仓库用途
本仓库作为考试期间的公开需求池与文档中心，供考官直接查看与操作。

## Agent 设计
### Agent A：问答收单 Agent
负责：
- 回答 `octo-server` 产品/源码问题
- 输出可核验的源码引用（路径 + 行号）
- 对反馈进行分类与归档
- 创建 issue 并打标签
- 协调需求状态流转
- 定时扫描需求池变化并回群通知

### Agent B：PRD / Review Agent
负责：
- 根据 issue 生成 PRD 草稿
- 发起与处理 review
- 根据 review 意见修改 PRD
- 保证 PRD 只写 What，不写 How

## 目录
- `docs/kb/`：`octo-server` 九大知识域知识库
- `docs/prd/`：PRD 模板与产物
- `docs/review/`：review 模板与产物
- `docs/runbooks/`：归档、巡检、通知规则
- `docs/exam/`：考试架构说明、亮点说明、冻结检查清单
- `logs/cron-runs/`：定时巡检执行记录
- `state/`：巡检状态文件

## 基本工作流
1. 群聊收到反馈
2. Agent A 判断类型、优先级、是否需要 PRD
3. 在本仓库创建 issue 并打标签
4. 需要产品整理时，Agent B 生成 PRD 草稿
5. PRD 进入 review，必要时修改
6. 定时任务扫描 issue / 评论 / 标签 / 状态变化
7. 仅在有变化时回群通知相关人和主考

## 设计原则
- 结论优先给证据
- 不确定就明确说不确定
- PRD 只写 What，不写 How
- 无变化不发消息
- 已修复 ≠ 未复现 ≠ wontfix
- 所有外部凭证不进群、不进 git

## 评分对应
- 知识库：`docs/kb/`
- PM 链路：issue → PRD → review
- 长时闭环：定时巡检 + 执行记录
- 归档质量：issue 模板 + label 体系
- 个人答题：`docs/exam/design-highlights.md` 等辅助材料
