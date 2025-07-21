### 1. 日志记录
---
```python
import logging

# 使用日志记录，比 print 更专业
logging.basicConfig(level=logging.INFO, format='%(asctime)s - %(levelname)s - %(message)s')
```
### 2. Git约定式提交(Conventional Commits)
---
- 标准格式
```xml
<type>[optional scope]: <description>
[optional body]
[optional footer]
```
- type: 说明本次提交更新的类型
	- feat: 新功能 (feature)
	- fix: 修复 bug
	- docs: 仅仅修改了文档 (documentation)
	- style: 代码格式的修改，不影响代码逻辑 (比如修改缩进、空格、分号等)
	- refactor: 代码重构，既不是新增功能，也不是修复 bug (比如重命名变量、提取函数)
	- perf: 提升性能的修改 (performance)
	- test: 增加或修改测试用例
	- build: 修改项目构建系统或外部依赖 (比如修改 requirements.txt, package.json)
	- ci: 修改持续集成（CI）的配置文件和脚本
	- chore: 其他不修改源码或测试的杂项修改 (比如修改 .gitignore)
	- revert: 回滚到之前的某次提交
- [optional scope] (范围) - 可选
	- 用于说明本次提交影响的范围，比如某个功能模块或组件
- [description] (描述) 
	- 必需用一句话简短地描述本次提交的目的，不超过50个字符。、
	- 使用祈使句，如 "add"、"change"、"fix"，而不是 "added"、"changed"、"fixed"。
	- 首字母小写。
	- 结尾不加句号。
-  [optional body] (正文) 
	- 可选如果需要更详细的解释，可以添加正文。正文部分应该详细说明修改的动机和前后的对比。
- [optional footer] (脚注) 
	- 可选用于记录一些特殊信息，最常见的是：
		- 关联 Issue: Closes #123, Fixes #456 (当这次提交关闭了某个 issue 时使用)
		- 不兼容变更 (Breaking Change): 以 BREAKING CHANGE: 开头，描述不兼容的变更和迁移方法。