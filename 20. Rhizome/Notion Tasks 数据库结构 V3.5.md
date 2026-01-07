---
type:
  - 系统文档
uid: AD298CC2-0718-4700-88A0-AC7E6296DE1F
tags:
  - topic/Notion
  - topic/Minimal Attempt
  - topic/数据库设计
aliases: []
source: "[[Minimal Attempt V3.5 - Jaychen备份版本]]"
---
# Notion Tasks 数据库结构 V3.5

> 最后更新：2025-01-07
> 数据库ID：2cbc7f13-4876-81ff-97af-d79aee4790a0
> 来源：Minimal Attempt V3.5 - Jaychen备份版本

## 数据库概览

**名称**：Tasks
**创建时间**：2025-12-16
**最后编辑**：2025-12-16
**URL**：https://www.notion.so/2cbc7f13487681ff97afd79aee4790a0

## 字段定义

### 1. Name (任务名称)
- **类型**：Title
- **字段ID**：title
- **说明**：任务标题字段

### 2. Type (类型)
- **类型**：Select
- **字段ID**：E%5Bb
- **说明**：任务类型分类
- **选项**：
  - Misc (黄色) - 杂项任务
  - Project Task (蓝色) - 项目相关任务

### 3. Status (状态)
- **类型**：Status
- **字段ID**：FU%3FZ
- **说明**：任务当前状态
- **选项**：
  - To do (默认) - 待处理
  - Suspending (黄色) - 挂起，处理中止
  - Doing (蓝色) - 处理中
  - Drop (红色) - 废弃任务，不再执行
  - Done (绿色) - 完成

**状态分组**：
- To-do: To do
- In progress: Suspending, Doing, Drop
- Complete: Done

### 4. Priority (优先级)
- **类型**：Status
- **字段ID**：ZQ%3D%3D
- **说明**：任务优先级
- **选项**：
  - Low (棕色) - 低优先级
  - Medium (绿色) - 中等优先级
  - High (红色) - 高优先级

### 5. Due (截止日期)
- **类型**：Date
- **字段ID**：~%3C%5Cs
- **说明**：任务截止日期

### 6. Completed (完成日期)
- **类型**：Date
- **字段ID**：%60%3Ax%5C
- **说明**：任务实际完成日期

### 7. Related Project (相关项目)
- **类型**：Relation
- **字段ID**：XyM%5D
- **关联数据库**：Projects (2cbc7f13-4876-817c-9b5f-d2c686d2abc2)
- **双向关联字段**：Tasks (%3DERo)

### 8. RelatedArea (相关领域)
- **类型**：Relation
- **字段ID**：cJ~H
- **关联数据库**：Areas
- **双向关联字段**：RelatedTasks

### 9. RecurInterval (重复间隔)
- **类型**：Number
- **字段ID**：%3Cf%3A%5B
- **说明**：重复任务的间隔数值

### 10. RecurUnit (重复单位)
- **类型**：Select
- **字段ID**：zYz%5D
- **说明**：重复任务的时间单位
- **选项**：
  - years (蓝色) - 年
  - months (橙色) - 月
  - days (绿色) - 日

### 11. NextDue (下次截止日期)
- **类型**：Formula
- **字段ID**：PwPE
- **说明**：计算重复任务的下次截止日期
- **公式**：`Due日期 + RecurInterval个RecurUnit`

### 12. SmartList (智能列表)
- **类型**：Select
- **字段ID**：bMI%40
- **说明**：将任务标记到特定视图
- **选项**：
  - Milestone (红色) - 里程碑任务
  - HighLight (黄色) - 高亮任务
  - Someday (蓝色) - 将来某一天的任务
  - Float (绿色) - 浮动任务

### 13. WeekDay (星期几)
- **类型**：Formula
- **字段ID**：GhDU
- **说明**：显示Due日期对应的星期几
- **公式**：根据Due日期计算返回Monday到Sunday

### 14. MetaLabel (元标签)
- **类型**：Formula
- **字段ID**：~FR%60
- **说明**：根据任务状态自动显示标签
- **标签逻辑**：
  - 🚨 逾期任务
  - 🚨🚨🚨 逾期+高优先级
  - 🌟 HighLight任务
  - 🔁 重复任务
  - 🛟 Float任务

### 15. Complete (完成按钮)
- **类型**：Button
- **字段ID**：HOqy
- **说明**：一键标记任务为完成

### 16. Created (创建时间)
- **类型**：Created Time
- **字段ID**：X%3AH~
- **说明**：任务创建时间

### 17. Edited (编辑时间)
- **类型**：Last Edited Time
- **字段ID**：~So%5D
- **说明**：任务最后编辑时间

## 关联数据库

### Projects数据库
- **数据库ID**：2cbc7f13-4876-817c-9b5f-d2c686d2abc2
- **关联关系**：任务归属于某个项目
- **关联字段**：Related Project ↔ Tasks

### Areas数据库
- **数据库ID**：2cbc7f13-4876-810e-a097-f8dccbfb5675
- **关联关系**：任务归属于某个领域
- **关联字段**：RelatedArea ↔ RelatedTasks

## 数据库父级信息

- **父数据库ID**：2cbc7f13-4876-81ff-97af-d79aee4790a0
- **父块ID**：2cbc7f13-4876-81b1-b51d-cd45595fadff

## 设计特点

1. **灵活的状态管理**：除了常规的To do/Doing/Done，还支持Suspending（挂起）和Drop（废弃）状态
2. **重复任务支持**：通过RecurInterval和RecurUnit设置任务重复，NextDue自动计算下次截止日期
3. **智能标签系统**：MetaLabel字段根据任务属性自动显示表情符号标签，便于视觉识别
4. **优先级与状态分离**：Priority使用独立的Status类型，与任务执行状态Status分开管理
5. **时间维度完整**：包含创建时间、编辑时间、截止日期、完成日期等完整的时间追踪
6. **SmartList分类**：支持将任务分类到不同的智能列表，便于在不同视图下管理
7. **星期几显示**：WeekDay字段直观显示截止日期是星期几，方便周计划安排

## 公式亮点

### MetaLabel公式逻辑
使用`lets()`函数定义多个中间变量，组合显示多个标签：
- 逾期检测（包括高优先级逾期警告）
- HighLight标记
- 重复任务标记
- Float任务标记

### NextDue公式
利用`dateAdd()`函数实现动态计算下次重复任务的截止日期。

---

*此文档由Claude自动生成并同步*
