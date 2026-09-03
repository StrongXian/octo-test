# Label System

本仓库使用统一 label 体系表达需求类型、优先级、状态与辅助信息。

## 一、类型
- `type/bug`：缺陷反馈
- `type/feature`：新功能或能力增强
- `type/question`：咨询类问题
- `type/task`：任务型事项

## 二、优先级
- `priority/p0`：紧急，高影响，需要最快处理
- `priority/p1`：高优先级，影响核心体验或关键流程
- `priority/p2`：中优先级，重要但不阻塞核心流程
- `priority/p3`：低优先级，优化项或观察项

## 三、状态
- `status/new`：新建，尚未分诊
- `status/triaged`：已完成初步分诊
- `status/prd-draft`：已进入 PRD 草稿阶段
- `status/in-review`：PRD 或方案处于 review 中
- `status/changes-requested`：review 后要求修改
- `status/approved`：review 通过
- `status/wontfix`：明确不做
- `status/closed`：事项关闭

## 四、辅助标签
- `source/exam`：考试场景产生
- `needs-info`：信息不足，需补充
- `needs-prd`：需要生成 PRD
- `kb-gap`：知识库存在空白，需补充
- `human-followup`：需人工进一步判断或处理

## 五、影响标签（可选）
- `impact/high`
- `impact/medium`
- `impact/low`

## 六、使用规则
1. 每个 issue 至少具备：
   - 1 个类型标签
   - 1 个优先级标签
   - 1 个状态标签

2. 初次归档默认：
   - `status/new`

3. 完成初步判断后：
   - 更新为 `status/triaged`

4. 需要产品整理时：
   - 增加 `needs-prd`
   - 状态更新为 `status/prd-draft`

5. 如被明确判定为不做：
   - 使用 `status/wontfix`
   - 不得用“未复现”替代“已修复”或“wontfix”
