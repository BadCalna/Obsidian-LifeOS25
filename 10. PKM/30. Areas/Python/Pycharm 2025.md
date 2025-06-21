## 快捷键
---
- option + enter: **预览警告并应用快速修复**，几乎可以在任何地方使用这个快捷键组合
	- 甚至可以反转if、应用德摩根定律
- double Shift: **随处搜索**
	- 甚至可以改变字符串的大小写

## **JupyterNotebook**
---
- control + enter:  运行
- 在数据视图中打开，可以将结果以dataFrame的模式打开
- shift + esc: 关闭工具窗口
- option + shift + B: 添加代码块
- shift + cmd + -: 在当前行拆分单元
- control + option + shift + enter: 运行全部

## **编辑器基础知识**
---
#### 搜索
- shift + cmd + A: 查找操作
- 也可以双击shift，切换到操作页签
#### 文本操作
- option + ⬆️
	- 点击一次：选择文本光标处的单词
	- 两次：整个字符串
	- 三次：字符串+引号
	- 四次：整个调用
#### 注释
- cmd + / : 注释，可多行注释或者取消注释
#### 移动代码段
- option + shift + ⬆️/⬇️：向上/下拉取当前行
- shift + cmd + ⬆️/⬇️：向上/下拉取当前方法
#### 复制和删除行
- cmd + D: 复制文本光标所在的行
- cmd + 🔙：删除文本光标所在行
- cmd + X: 剪切文本光标所在行
#### 收起代码段
- cmd + ➖/🟰 ：收起/展开代码段
- shift + cmd + ➖/🟰： 全部收起/展开
#### 包围/解包
- option + cmd + T：包围所选代码段
	- 可选if/while/try-except/try-finally/
- shift + cmd + 🔙：（好像没用）可以双击shift，搜索解包，选择对应条目即可
#### 多选
- control + G: 选择光标处符号
	- 可选择下一个与光标处符号匹配的匹配项
	- ***可用于选择变量批量更名***
- shift + control + G: 取消上一个匹配项
- control + cmd + G：选中文档中的全部匹配项
	- 此时输入值可以批量替换
	- esc退出多光标模式
## **代码补全**
---
#### 基本补全

^6d6da7

- control + fn(没开fnlock时，即直接按F系列键可以触发功能时) + space：基本补全，可以选择补全内容
#### 标签页补全
- control + fn + space：选择到希望替换的内容（变量名、方法等），按tab 替换
#### 后缀名补全：在当前方法或变量后输入‘.’即可触发后缀补全
- 示例
```python
movies_dict.get('year')
# 补全为if x is not none
movies_dict.get('year').ifnn
选定
```
#### 类型匹配补全
- 对于未知类型，pycharm无法直接提供[[Pycharm 2025#^6d6da7|基本补全]]
- 可以尝试通过以下快捷键，pycharm将尝试基于上下文补全
	- control + shift + space
#### F-string自动补全
- 直接在字符串内键入【{ +变量名】后使用基本补全，即可转换当前字符串为f-string