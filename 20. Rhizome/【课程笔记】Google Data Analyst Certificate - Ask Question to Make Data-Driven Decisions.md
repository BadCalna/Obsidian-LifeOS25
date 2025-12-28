---
type:
  - 课程笔记
uid: a326fcb0-d5d9-4fef-b0e9-86f2a8de5959
tags:
  - topic/数据分析
aliases: []
source: https://www.coursera.org/learn/ask-questions-make-decisions/
---
# 【课程笔记】Google Data Analyst Certificate - Ask Question to Make Data-Driven Decisions

## 📌核心结论 (The Gist)
> [在这里写下最重要的那句话，让未来的你一秒看懂]
- 
---
## 🧩课程内容(Content)
> 课程内容记录
- # Tools for visualizing data
	- 常用的有：表格工具(Spreadsheet)，Tableau
	- Spreadsheet便于呈现静态的、数据量较少的数据集
	- Tableau适用于数据量大的数据集，包含一些进阶的分析功能
- # Design compelling dashboards
	- 仪表盘用于监控“活的”、不断产生、多数据源的数据，能够节约时间
		- 好处
			- 无需时时维护
			- 监控活数据
			- 利益相关者友好（sb都看得懂）
	- 仪表盘自动变化仅限于现有结构下的数据变化，如果数据结构发生变化，那就需要重新调整仪表盘
	- 仪表盘设计思路
		- 确认对象及期望使用方法
		- 设计Tips
			- 清晰标题
			- 简短描述每个图表
			- 重要信息放顶部
		- 选择图表形式
		- 创造Filter便于利益相关者发现
- # self-reflection-go-deeper-into-dashboards
	- 企业常用的三种仪表盘
		- 战略型：长时间维度内，跟踪KPI
		- 运营型：最常见，实时反应执行情况的数据
		- 分析型：数据团队维护使用，抽象程度高
	- 异同点
		- 同：都是可视化工具/利于协助分析师评估公司绩效
		- 异：时间差异
			- 战略 - 财年、季度
			- 运营 - 周、天
			- 分析 - 跳过具体时间范围，转而识别和跟踪用于评估战略与运营目标的各类KPI
	- 仪表盘可以帮助企业完成许多有用的任务
		- 例如：
			- 追踪历史和当前业绩
			- 制定长期或短期目标。
			- 定义关键绩效指标或衡量标准
			- 识别潜在问题或效率低下的环节
	- 虽然几乎所有公司都能从使用仪表盘中获益，但规模较大的公司以及拥有更广泛产品或服务的公司可能会受益更多(**因为能够积累更多数据**）。
	- 在市场波动或快速变化的市场（例如营销、销售和科技行业）中运营的公司也往往能够更快地获得洞察并做出数据驱动的决策。
- # Mathematical thinking
	- 一种把问题逐步拆分、分而治之的 研究思路
	- 大数据
		- 量大且不具体
		- 长时间范围内积累的数据
- # Big and small data
	- 描述![[Pasted image 20251215182630.png]]
	- 处理大数据的挑战
		- 数据过载，不重要数据夹杂重要数据
		- 数据不好访问
		- 算法偏见（现有工具的限制）
	- 优势
		- 经营模式优化，节约成本
		- 提升客户满意度（基于大数据做出客户购买趋势优化）
		- 深入了解市场
	- 大数据的4V
		- Volume：容量
		- Variety：多种多样
		- Velocity：处理速度
		- Veracity：数据质量和可置信度
- # 术语表
	- 算法（Algorithm）：为完成特定任务而遵循的一套流程或规则。
	- 大数据（Bigdata）：规模庞大、结构复杂的数据集，通常涵盖较长时间跨度，使数据分析师能够解决更宏观的业务问题。
	- 仪表板（Dashboard）：用于监控实时、持续流入数据的工具。
	- 数据启发式决策（Data-inspireddecision-making）：探索不同数据来源，找出它们共同点的过程。
	- 指标（Metric）：用于衡量的、单一且可量化的数据类型。
	- 指标目标（Metricgoal）：企业设定的可衡量目标，并通过指标进行评估。
	- 数据透视图（Pivotchart）：基于数据透视表字段生成的图表。
	- 数据透视表（Pivottable）：用于数据汇总的工具，可对数据进行排序、重组、分组、计数、求和或求平均。
	- 问题类型（Problemtypes）：数据分析师常见的问题类别，包括分类事物、发现关联、寻找模式、识别主题、进行预测、以及发现异常情况。
	- 定性数据（Qualitativedata）：对某种质量或特征的主观性、解释性度量。
	- 定量数据（Quantitativedata）：客观、具体的度量，例如数字、数量或范围。
	- 报告（Report）：定期提供给利益相关者的静态数据集合。
	- 投资回报率（ROI,Returnoninvestment）：利用投资与利润等指标来评估投资成功与否的公式。
	- 收入（Revenue）：通过销售商品或服务产生的总收入。
	- 小数据（Smalldata）：规模较小、具体的数据点，通常涉及较短时间周期，适合用于日常决策。
- # Basic spreadsheet tasks
	- 开源数据渠道：
		- World Bank
		- World Health Organization
		- Google Public Data Explorer
		- U.S. Census Bureau
- # Quick Reference: Formulas in Spreadsheet
	- 绝对引用：$
		- 加在行前 —— 绝对行
		- 加在列前 —— 绝对列
		- 行列都加 —— 固定单元格
		- 快捷操作：F4
- # Spreadsheet Error 
	- **DIV错误**：当公式试图将一个值除以零或空单元格时出现。可以使用IFERROR函数来避免此错误，自动插入“不可用”。
	- **ERROR错误**：表示公式无法被正确解析，通常是因为缺少分隔符（如逗号）
	- **N/A错误**：表示公式中引用的数据无法找到，通常是因为数据不存在。常见于VLOOKUP函数
	- name  error： 函数/方法名错误
	- value error：参数不符合预设类型
	- num error：输出不符合预设
	- ref error：引用格消失
	- 常见错误和解决方法
		- 筛选数据，使您的电子表格更简洁、更清晰。
		- 使用并冻结标题，以便即使在滚动时也能知道每一列的内容。
		- 进行乘法运算时，请使用星号（*）而不是X。
		- 每个公式和函数都以等号（=）开头。
		- 无论何时使用左括号，都要确保另一端有与之匹配的右括号。
		- 换一种易于阅读的字体。
		- 将边框颜色设置为白色，这样你就可以在一张空白的纸上工作了。
		- 创建一个只包含原始数据的工作表，再创建一个只包含所需数据的工作表。
	- Resources
		- [**当你的公式不起作用时：Google 表格中的公式解析错误**](https://www.benlcollins.com/spreadsheets/formula-parse-error/ "当你的公式不起作用时：Google 表格中的公式解析错误")
		- [**微软公式和函数**](https://support.microsoft.com/en-us/office/formulas-and-functions-294d9486-b332-48ed-b489-abe7d0f9eda9?ui=en-US&rs=en-US&ad=US#id0eaabaaa=errors "微软公式和函数")
	- 公式(formula): =a1 + b2
	- 函数(functions): =sum(a1,b2)
- # hands-on-activity-create-a-custom-data-table
	- 把Date转成月份
		- eg. 1/1/25 -> TEXT("1/1/25","mmmm") = "January"
- # Define a problem before solving them
	- 首先**确认 问题的范围(Problem Domain)**
		- 一个包含所有影响问题或被问题影响所有活动的明确的分析域
		-  **一个特定的分析范围，涵盖所有会影响该问题或受该问题影响的活动**
- # Scope of Work and Structural thinking
	- Scope of Work  - 工作范围(SoW)
		- def: an agreed-upon outline of the work you're going to perform on a project 
		- 一个**经各方一致认可的、你将在项目中开展工作的纲要/大纲**
	- v.s Statement of Work
		- 工作说明书是一份文件，它清晰地列出了供应商或承包商将向组织提供的产品和服务。它包括目标、指导方针、交付成果、进度安排和成本。
		- 工作范围是基于项目的，它设定了项目的预期目标和范围。工作范围可以包含在工作说明书中，以帮助定义项目成果。 
		- 作为一名初级数据分析师，通常情况下，你会被要求创建工作范围，而不是工作说明书。
- # Creating a scope of work
	- case：安排一个员工培训
	- 方法论：SoW
		- 交付物
			- 完成项目前一定要完成的任务
			- 可交付物可以是“系统上线运行的状态”、“员工通过培训的认证”或“授权协议”。它是**价值的交付点**，不限于实物。
		- 时间线
			- 交付物、里程碑、报告的到期时间
			- Q：如果一个 Deliverable (可交付物) 没有明确的 Timeline，会对项目管理带来什么直接风险？
				- A：没有 Timeline 的交付物在时间维度上是“**隐形**”的。这会导致团队无法分配优先级，由于没有 Due Date 约束，这个产出物可能会被无限期搁置，最终拖垮后续所有依赖它的 Milestone。
		- 里程碑：里程碑通常是一个**瞬间发生的、标志性事件**或节点，用来划分阶段
			- 一些需要按照时间表确认完成的重要任务，便于大家知道项目正在按计划进行
		- 报告
			- 当你最终确认了可交付物以及到达里程碑
			- Report 的核心作用是**实时对齐（Alignment）** 和风险预警。它是一种沟通契约，确保所有利益相关者在项目进行中（而非结束后）就知道进度是否偏离轨道
	- 推荐的SoW格式
		- Deliverables：明确、清晰的说明本项目正开展哪些工作并且需要向利益相关者交付哪些东西 —— 避免使用模糊的表述
		- Milestones：和Timeline息息相关。里程碑用来划分较大项目的不同阶段，可以由项目经理、利益相关者等一起确认
		- Timeline：与制定的Milestone紧密关联，主要用来规划项目每个部分需要的时间 —— 需要足够具体，以便同步各方项目推进正常
		- Report：明确如何与利益相关方汇报进度，沟通频率如何？是每周汇报？每月汇报？还是在里程碑完成后汇报？进度报告将包含哪些信息？
---
## 🧠思考与分析 (Thought & Analysis)
> Tips：“它让我怎么想？”比“它说了什么？”更重要，尝试用自己的话讲述
- 

---
## 🎬下一步行动 (Optional)
---

## 🔗关联笔记 (Connections)
---
- 

