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
- type: 说明本次提交