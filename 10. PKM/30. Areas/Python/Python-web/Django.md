## Django 概览：功能、特点与基本用法
---
### 1. Django 是什么？
- Django 是一个用 Python 语言编写的**高级 Web 框架**。它的核心理念是 **“DRY”（Don't Repeat Yourself - 不要重复自己）** 和 **“快速开发”**。Django 致力于使 Web 开发变得高效且愉快。
- 它被称为“带电池的框架”（"The Web framework for perfectionists with deadlines." / "The batteries included web framework."），因为它提供了大量开箱即用的功能和工具，涵盖了 Web 开发的方方面面，让你无需从零开始构建。
### 2. Django 的架构：MTV 模式
---
- Django 采用的是一种类似于 MVC（Model-View-Controller）的架构模式，但它通常被称为 **MTV 模式**：
- **M - Model (模型):**
	- **功能:** 负责处理应用程序的**数据逻辑**。它定义了你的数据结构（例如，数据库中的表），以及数据如何存储、检索、验证和行为。
	- **特点:** Django 的模型层使用 **ORM (Object-Relational Mapper - 对象关系映射器)**。这意味着你可以使用 Python 类来定义数据库表，而无需直接编写 SQL 语句。ORM 会将 Python 对象的操作自动转换为数据库操作。
	- **基本用法:**
		- 在 `models.py` 文件中定义 Python 类，每个类对应数据库中的一张表。
		- 定义类的属性，每个属性对应表中的一列。
		- 通过 `python manage.py makemigrations` 生成迁移文件，记录模型的变化。
		- 通过 `python manage.py migrate` 将模型变化同步到数据库。
		- 通过 ORM 提供的 API 进行数据查询、插入、更新、删除。
```python
# models.py 示例
from django.db import models

class Article(models.Model):
    title = models.CharField(max_length=100)
    content = models.TextField()
    pub_date = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title

# 使用ORM（在shell或views中）
# from myapp.models import Article
# article = Article.objects.create(title="My First Article", content="Hello world.")
# all_articles = Article.objects.all()
# specific_article = Article.objects.get(pk=1)
```
- **T - Template (模板):**
	- **功能:** 负责呈现用户界面。它定义了数据的**展示方式**，通常是 HTML 文件，其中嵌入了 Django 模板语言（DTL）的标签和变量，用于动态地显示数据。
	- **特点:** 模板系统将逻辑和展示分离，使得设计师和开发者可以并行工作。它提供了强大的模板继承、包含、过滤器等功能。
	- **基本用法:**
	    - 在 `templates/` 文件夹下创建 HTML 文件。
	    - 使用 `{{ variable }}` 来显示从视图传递过来的数据。
	    - 使用 `{% tag %}` 来控制模板的逻辑（例如循环 `for`，条件 `if` 等）。
```html
<h1>文章列表</h1>
<ul>
    {% for article in articles %}
        <li>
            <h2>{{ article.title }}</h2>
            <p>{{ article.content|truncatechars:50 }}</p>
            <small>发布日期: {{ article.pub_date|date:"Y-m-d" }}</small>
        </li>
    {% endfor %}
</ul>
```