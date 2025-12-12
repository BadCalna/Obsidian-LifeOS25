---
type:
  - 工具
uid: 50bbe5ef-b5fb-413c-a726-2ad02fc3cd2c
tags:
  - topic/数据分析
  - tool/Google表格
aliases: []
source: https://keep.google.com/#NOTE/1xXF6Qm06WJHmYFcB2CNcpQSmHhx4W2plRqTHnNeva9Qspo2NYusHGtWWW3WM0cpjKimS
---
# Google Sheet - 多列排序

## 📌核心结论 (The Gist)
>[一句话：这个工具到底解决什么问题？]
- 不要用工具栏上的快捷排序按钮（那只能排单列）。 
- 必须进入 **Data -> Sort range -> Advanced** 菜单，才能实现“先按A列排，再按B列排”且**不打乱标题行**。
---
## 🧩适用场景 (Use Case)
> [什么时候用它？什么时候**不**要用它？]
* **痛点（The Trap）：** Google Sheet 的普通排序功能很容易把“标题行”也一起卷进去排序，或者只能排一列，导致想做复杂整理时很抓狂。 
* **关键入口（The Key）：** 藏得有点深，在 `Advanced` 里。
* **防坑点：** 必须勾选 `Data has header row`（数据包含标题行），否则标题会被当成数据排到中间去。
---
##  🧭避坑与指南 (Guide & Traps)
> Tips：“它让我怎么想？”比“它说了什么？”更重要，尝试用自己的话讲述
1. 选中所有数据；
2. 路径：`Data` -> `Sort range` -> `Advanced range sorting options`；
3. **关键步骤：** 勾选 `Data has header row`；
4. 依次添加排序规则（Sort by Column A, then by Column B...）。

---
## 🎬下一步行动 (Optional)
---

## 🔗关联笔记 (Connections)
---
- 

