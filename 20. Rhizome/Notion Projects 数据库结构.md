# Notion Projects 数据库结构

> 最后更新：2025-01-06
> 数据库ID：196c7f13-4876-803e-b07b-000b0080d54a
> 来源：Notion Workspace

## 数据库概览

**名称**：Projects
**创建时间**：2025-02-10
**最后编辑**：2025-07-15
**URL**：https://www.notion.so/196c7f13487680e98619fb0e9a44872f

## 字段定义

### 1. Project (标题字段)
- **类型**：Title
- **字段ID**：title
- **说明**：项目名称

### 2. Description (描述)
- **类型**：Rich Text
- **字段ID**：kuS~
- **说明**：项目的详细描述

### 3. Status (状态)
- **类型**：Status
- **字段ID**：VhN`
- **说明**：
  - Planned - 已经规划好的
  - On Hold - 因某种原因暂停
  - Ongoing - 将持续很长时间且持续进行
  - Doing - 正在进行的项目
  - Done - 项目完成，标记为已归档

**状态分组**：
- To-do: Planned, On Hold
- In progress: Ongoing, Doing
- Complete: Done

### 4. StartDate (开始日期)
- **类型**：Date
- **字段ID**：~T{^
- **说明**：项目开始日期

### 5. EndDate (结束日期)
- **类型**：Date
- **字段ID**：^DAB
- **说明**：项目结束日期

### 6. Progress (进度)
- **类型**：Formula
- **字段ID**：<Vn~
- **说明**：自动计算进度（已完成任务数 / 总任务数 * 100%）

### 7. Tasks (任务)
- **类型**：Relation
- **字段ID**：Oiuo
- **关联数据库**：Tasks (197c7f13-4876-80c7-9650-fb562d87fe73)
- **双向关联字段**：Project (YSdO)

### 8. RelatedNotes (关联笔记)
- **类型**：Relation
- **字段ID**：Di@V
- **关联数据库**：Notes (19dc7f13-4876-8070-a457-000b17e49f92)
- **双向关联字段**：Projects (JZ[`)

### 9. Income (收入)
- **类型**：Rollup
- **字段ID**：ZWIR
- **说明**：从Tasks关联中汇总收入数据
- **汇总方式**：Sum（求和）
- **源字段**：Tasks.Income (k}sY)

### 10. tags (标签)
- **类型**：Select
- **字段ID**：jFK{
- **选项**：
  - Personal (个人) - 绿色
  - Work (工作) - 粉色

## 关联数据库

### Tasks数据库
- **数据库ID**：197c7f13-4876-80c7-9650-fb562d87fe73
- **关联关系**：一个项目可以包含多个任务

### Notes数据库
- **数据库ID**：19dc7f13-4876-8070-a457-000b17e49f92
- **关联关系**：一个项目可以关联多则笔记

## 数据库父级信息

- **父数据库ID**：196c7f13-4876-80e9-8619-fb0e9a44872f
- **父块ID**：1a0c7f13-4876-80bc-bbd5-ed0b605c0c99

---

*此文档由Claude自动生成并同步*
