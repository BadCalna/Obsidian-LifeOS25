---
type:
  - 工具
  - 研究
uid: 8529b6bc-e849-414a-adee-f173972981f8
tags:
  - learning/费曼练习
  - topic/生产力
  - topic/Notion
  - topic/系统设计
aliases: []
source: https://developers.notion.com/docs/working-with-page-content#modeling-content-as-blocks
---
# Notion API中的页面(Page)呈现

## 📌核心结论 (The Gist)
> [在这里写下最重要的那句话，让未来的你一秒看懂]
- **Notion页面由“属性”和“块”构成，其中页面内容（块）是树状**或**嵌套**结构，获取完整内容必须像**侦探追踪线索**一样，对具有 `has_children: True` 的块进行**递归/迭代**请求。
---
## 🧩背景/情景 (Context)
> 当时遇到了什么问题？或者想到了什么？
- 接入Notion API的过程中，由于其并未提供Python的SDK代码，所以只能采用[[什么是cURL？|cURL]]转Python代码的形式，按照API提供的每一个端点(endpoint)写成方法进行接入
> cURL转代码可以采用这个网站：[cURL converter](https://curlconverter.com/)
- 但是Notion官方文档对于整个Notion页面的理解和我的理解有点不同，下面在思考分析部分用一个示例说明一下
---
## 🧠思考与分析 (Thought & Analysis)
> Tips：“它让我怎么想？”比“它说了什么？”更重要，尝试用自己的话讲述
- 示例页面![[Pasted image 20251116151156.png]]
- Notion的页面(Page)分为两部分，上半部分（上图中“评论”上方的内容）被称为页面的**属性**，下半部分被称为页面的**内容**
	- 其中，**属性**是相对“结构化”的；**内容**是相对自由松散的
	- 举个例子，每个页面都是一个公民，“属性”就像是这个公民的身份证号、性别、身高体重等等，是相对而言比较“受限制”的——身份证号有一定的生成规则；性别只有男、女；身高体重一定是准确的数字。相对的，“内容“像是这个公民的外貌，没有固定、限制
- 页面的**内容**又是由一个个块(Blocks)组成的 —— 实际操作Notion软件的时候就会有感受，你的每一个段落、文本、表格，都是一个块；每个块都有一个类型，例如段落、标题或图像，某些类型的块自身就具有子元素（注意⚠️：页面本身也是一种特殊的块）
	- 可以理解为整个页面的内容就像是用块(Blocks)搭成的积木
- 所以上面的示例页面中，直接获取页面的块(Retrieve blocks)，会获取到：
	- 公式：Todo
	- 分割线
	- to-do列表：阅读文档
	- to-do列表：创建第一个Notion API实例
	- 二级标题：Instructions
- 其他部分是获取不到的，原因是：*其他部分不是这个页面的直接子元素，而是这个页面子元素的子元素*
- 因此，如果要完整展示整个页面的信息，需要对块的属性“has_children"为'True'的块，取其id进一步获取其子元素
---
## 🎬下一步行动 (Optional)
---

## 🔗关联笔记 (Connections)
---
- 

