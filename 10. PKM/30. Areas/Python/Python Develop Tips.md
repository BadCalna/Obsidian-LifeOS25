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