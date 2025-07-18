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