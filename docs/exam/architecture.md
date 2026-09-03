# Exam Architecture

## 方案概述
本次考试采用双 Agent 方案：

- Agent A：问答收单 Agent
- Agent B：PRD / Review Agent

并使用 `StrongXian/octo-test` 作为公开需求池仓库。

## 架构目标
1. 回答 `octo-server` 产品/源码问题，并给出可核验源码引用
2. 将群聊中的反馈归档到 GitHub 需求池
3. 通过 issue → PRD → review 形成 PM 闭环
4. 通过定时巡检自动发现变化并按规则通知

## 设计理由
- 双 Agent 分工更贴近真实产品协作
- 问答与文档分离，减少上下文污染
- 证据优先，降低错误结论风险
- 静默巡检，减少群噪音
