---
type:
  - 系统文档
uid: 8925C9AA-2ED0-4A82-BD25-D8ABDD97990C
tags:
  - topic/Notion
  - topic/Minimal Attempt
  - topic/数据库设计
aliases: []
source: "[[Minimal Attempt V3.5 - Jaychen备份版本]]"
---
# Notion Projects 数据库结构 V3.5

> 最后更新：2025-01-07
> 数据库ID：2cbc7f13-4876-817c-9b5f-d2c686d2abc2
> 来源：Minimal Attempt V3.5 - Jaychen备份版本

## 数据库概览

**名称**：Projects
**创建时间**：2025-12-16
**最后编辑**：2025-12-16
**URL**：https://www.notion.so/2cbc7f134876817c9b5fd2c686d2abc2

## 字段定义

### 1. Name (项目名称)
- **类型**：Title
- **字段ID**：title
- **说明**：项目标题字段

### 2. Description (描述)
- **类型**：Rich Text
- **字段ID**：z%D%<%
- **说明**：项目的详细描述

### 3. Status (状态)
- **类型**：Status
- **字段ID**：iL|k
- **说明**：项目当前状态
- **选项**：
  - On Hold (红色) - 暂停
  - Planned (默认) - 已计划
  - In Progress (蓝色) - 进行中
  - Done (绿色) - 已完成

**状态分组**：
- To-do: On Hold, Planned
- In progress: In Progress
- Complete: Done

### 4. Priority (优先级)
- **类型**：Select
- **字段ID**：o%E<CS
- **说明**：项目优先级分类
- **选项**：
  - P1 - Core Focus (红色) - 与年度/季度目标直接挂钩，必须完成，投入大量时间的项目
  - P2 - Secondary Focus (绿色) - 重要但不紧急，或对核心目标有间接帮助，或个人兴趣的项目
  - P3 - Exploration/Maintenance (灰色) - 探索性学习、系统维护、或者暂时不会立即启动的项目

### 5. TimeFrame (时间框架)
- **类型**：Date
- **字段ID**：J[p?
- **说明**：项目时间范围

### 6. RelatedArea (相关领域)
- **类型**：Relation
- **字段ID**：%DYU<C
- **关联数据库**：Areas
- **双向关联字段**：RelatedProjects

### 7. Tasks (任务)
- **类型**：Relation
- **字段ID**：%3DERo
- **关联数据库**：Tasks (2cbc7f13-4876-81ff-97af-d79aee4790a0)
- **双向关联字段**：Related Project (XyM%5D)

### 8. Notes (笔记)
- **类型**：Relation
- **字段ID**：nFXJ
- **关联数据库**：Notes
- **双向关联字段**：Related Projects

### 9. Resources (资源)
- **类型**：Relation
- **字段ID**：G%E@|
- **关联数据库**：Resources
- **双向关联字段**：Projects

### 10. Progression (进度)
- **类型**：Formula
- **字段ID**：DX%ES
- **说明**：自动计算项目完成进度
- **公式**：`(已完成任务数 + 已废弃任务数) / 总任务数 * 100%`

## 关联数据库

### Tasks数据库
- **数据库ID**：2cbc7f13-4876-81ff-97af-d79aee4790a0
- **关联关系**：一个项目可以包含多个任务
- **关联字段**：Tasks ↔ Related Project

### Notes数据库
- **数据库ID**：2cbc7f13-4876-81b4-8cc3-f90ba9a63a59
- **关联关系**：一个项目可以关联多则笔记
- **关联字段**：Notes ↔ Related Projects

### Areas数据库
- **数据库ID**：2cbc7f13-4876-810e-a097-f8dccbfb5675
- **关联关系**：项目归属于某个领域
- **关联字段**：RelatedArea ↔ RelatedProjects

### Resources数据库
- **数据库ID**：2cbc7f13-4876-8130-a46a-fbe9e68ada37
- **关联关系**：项目使用的资源
- **关联字段**：Resources ↔ Projects

## 数据库父级信息

- **父数据库ID**：2cbc7f13-4876-817c-9b5f-d2c686d2abc2
- **父块ID**：2cbc7f13-4876-81b1-b51d-cd45595fadff

## 设计特点

1. **优先级分层**：使用P1/P2/P3三级优先级系统，清晰区分项目重要性
2. **状态追踪**：包含On Hold状态，可以处理暂时搁置的项目
3. **自动进度计算**：基于关联的Tasks自动计算完成度
4. **多维度关联**：关联Notes、Resources、Areas等多个数据库，形成完整的知识管理网络

---

*此文档由Claude自动生成并同步*
