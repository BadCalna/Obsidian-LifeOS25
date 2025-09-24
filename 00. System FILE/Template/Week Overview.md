---
# --- Metadata ---
course: "Supervised Machine Learning: Regression and Classification"
week: {{week_number}} 
module: "{{module_title}}" # 可选，如果一周内有明确的模块划分
topic: "{{topic_title}}" # 笔记核心主题，例如 "Linear Regression with One Variable"
type: Lecture | Concept | Algorithm | Math | CodeExample # 选择最相关的类型
status: Not Started | In Progress | Completed | Review Needed
tags: [course-c1, course-c1-w{{week_number}}] # 添加具体标签, e.g., regression, gradient-descent, cost-function
related_concepts: ["[[Relevant Concept 1]]", "[[Algorithm Name]]"] # 链接到相关笔记
source_url: "{{lecture_video_url}}" # Coursera 视频链接
creation_date: {{date}}
last_revised: {{date}} 
# --- End Metadata ---

# {{topic_title}}

## 🎯 学习目标 / 核心问题 (Learning Objectives / Key Questions)
> (本节课/本概念要解决什么问题？)
> - 
> - 

## 🔑 核心概念与定义 (Core Concepts & Definitions)
<!-- 使用黑体或链接到单独的概念笔记 -->
- **[[Concept Name 1]]**: 定义... *直观理解:* ...
- **[[Concept Name 2]]**: 定义... 
    - *例子:* ...

## 🧠 直观理解 / 类比 (Intuition / Analogy)
> (用简单的语言、例子或比喻解释核心思想)
> 

## ➗ 数学推导与公式 (Mathematical Formulation)
> (使用 LaTeX 语法 `$formula$` 或 `$$ block formula $$`)
> - **假设函数 (Hypothesis):** $h_\theta(x) = ...$
> - **参数 (Parameters):** $\theta_0, \theta_1, ...$
> - **成本函数 (Cost Function):** $J(\theta) = ...$
> - **目标 (Objective):** $\min_\theta J(\theta)$

$$
% 复杂公式块
J(\theta_0, \theta_1) = \frac{1}{2m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})^2
$$

## ⚙️ 算法步骤 (Algorithm Steps) (If Applicable)
1.  初始化参数 (Initialize parameters) ...
2.  重复直到收敛 (Repeat until convergence) {
    *   计算梯度 (Compute gradient): $\frac{\partial}{\partial \theta_j} J(\theta)$
    *   更新参数 (Update parameters): $\theta_j := \theta_j - \alpha \frac{\partial}{\partial \theta_j} J(\theta)$
}
<!-- 对于复杂算法，可以链接到单独的算法笔记 [[Gradient Descent Algorithm]] -->

## 💻 代码实现片段 (Code Implementation Snippets) (Python/NumPy/Scikit-learn)
```python
# 示例: 计算成本函数
import numpy as np

def compute_cost(X, y, theta):
  m = len(y)
  predictions = X.dot(theta)
  sqr_errors = (predictions - y) ** 2
  J = 1 / (2 * m) * np.sum(sqr_errors)
  return J