### **JavaScript：网页的“大脑”和“魔法师”**
---
如果说 HTML 是骨架，CSS 是装修，那么 **JavaScript** 就是网页的**大脑**和**魔法师**。它是一种**编程语言**，让网页不再是静态的图片和文字，而是能够响应用户的操作、动态更新内容、执行复杂计算等等。
你可以用 JavaScript 来：
- **响应用户操作：** 比如点击按钮后显示/隐藏内容，鼠标悬停时改变样式。
- **动态修改内容：** 无需重新加载页面就能更新文本、图片等。
- **进行表单验证：** 检查用户输入是否符合要求。
- **实现动画效果：** 让元素平滑地移动、淡入淡出。
- **与服务器通信：** 在后台获取或发送数据（比如你刷微博、微信朋友圈时，新的内容都是通过 JavaScript 从服务器加载的）。
简而言之，JavaScript 让你的网页有了**交互性**和**生命力**。
---
### **如何在 HTML 中使用 JavaScript**
和 CSS 类似，你可以在 HTML 中通过 `<script>` 标签来引入 JavaScript 代码。通常，我们会把 `<script>` 标签放在 `<body>` 的**末尾**（`</body>` 标签之前），这样可以确保 HTML 内容加载完毕后，JavaScript 再开始执行，避免出现找不到元素的错误。
```JavaSript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>我的交互式网页</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f8f8;
            color: #333;
            margin: 20px;
        }
        h1 {
            color: #0056b3;
            text-align: center;
        }
        p {
            font-size: 18px;
            line-height: 1.6;
        }
        img {
            border: 5px solid #ddd;
            border-radius: 8px;
            display: block;
            margin: 20px auto; /* 修正后的上下20px外边距，左右居中 */
        }
        button { /* 给按钮添加一点样式 */
            background-color: #4CAF50; /* 绿色背景 */
            color: white; /* 白色文字 */
            padding: 10px 20px; /* 内边距 */
            border: none; /* 无边框 */
            border-radius: 5px; /* 圆角 */
            cursor: pointer; /* 鼠标悬停变手型 */
            display: block; /* 独占一行 */
            margin: 20px auto; /* 居中显示 */
            font-size: 16px;
        }
        button:hover { /* 鼠标悬停效果 */
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>我的个人介绍</h1>
    <p>我喜欢阅读，尤其喜欢科幻小说。</p>
    <img src="https://via.placeholder.com/200" alt="This is a picture.">

    <button onclick="showAlert()">点击我！</button>

    <script>
        // 定义一个JavaScript函数
        function showAlert() {
            alert('你点击了按钮！这是JavaScript的魔力！');
        }
    </script>
</body>
</html>
```
### **JavaScript 代码解释：事件和函数**
- `<button onclick="showAlert()">点击我！</button>`:
    - 这是一个 HTML **按钮**。
    - `onclick="showAlert()"` 是一个 **HTML 事件属性**。它告诉浏览器：当这个按钮被**点击 (click)** 时，就执行名为 `showAlert()` 的 JavaScript **函数**。
- `<script>` 标签: 包含了我们的 JavaScript 代码。
- `function showAlert() { ... }`: 这是一个 JavaScript **函数定义**。函数是一段可重复使用的代码块。
- `alert('你点击了按钮！这是JavaScript的魔力！');`: `alert()` 是 JavaScript 内置的一个函数，它会在浏览器中弹出一个带有指定文本的**警告框**。
```js
<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <title>My To-do List</title>  
  <style>  
    body{  
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", ui-system, sans-serif;  
      background-color: #f8f8f8;  
      color: #333;  
      margin: 20px;  
      padding: 20px;  
    }  
    h1{  
      text-align: center;  
      color: #0056b3;  
      margin-bottom: auto;  
      margin-top: auto;  
    }  
    input{  
      width: 100%;  
      padding: 10px;  
      margin-bottom: 10px;  
      border: 1px solid #ccc;  
    }  
    button{  
      color: cornflowerblue;  
      background-color: white  
    }  
    button:hover{  
      background-color: cornflowerblue;  
      color: white;  
    }  
    li{  
      list-style: circle;  
      padding: 10px;  
      margin-bottom: 10px;  
      background-color: white;  
      border: 1px solid #ccc;  
      border-radius: 5px;  
    }  
  </style>  
</head>  
<body>  
  <h1>My To-do List</h1>  
  <input type = 'text' id = 'input' placeholder = 'Add a task'>  
  <button id = 'add' onclick="addTask()">Add</button>  
  <button id = 'clear' onclick="clearTask()">Clear</button>  
<!--  <li id="branding"></li>-->  
  <ul id = 'list'></ul>  
<script>  
  function addTask(){  
    const input = document.getElementById('input')  
    const list = document.getElementById('list')  
    const li = document.createElement('li')  
      if(input.value === ''){  
        alert('Cannot add an empty task!')  
        return  
      }  
    li.innerText = input.value  
    list.appendChild(li) // 添加到列表  
    input.value = '' // 清空输入框  
  }  
  function clearTask(){  
    const list = document.getElementById('list')  
    list.innerHTML = ''  
  }  
</script>  
</body>  
</html>
```