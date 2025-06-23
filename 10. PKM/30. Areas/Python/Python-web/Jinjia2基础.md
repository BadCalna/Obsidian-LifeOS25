Jinja2 模板文件通常是 `.html` 格式，但它里面可以包含特殊的语法来表示逻辑和数据：
### 变量输出
- 使用双大括号 `{{ 变量名 }}` 来输出后端传递过来的数据。
	- eg. 
```html
<h1>Hello, {{ user_name }}!</h1>
```
#### 控制结构
- for 循环
```html
<ul>
    {% for item in items %}
        <li>{{ item }}</li>
    {% endfor %}
</ul>
```
