## Learning with Gemini
---
### **CSS：网页的“化妆师”**
---
既然我们有了网页的“骨架”HTML，接下来就要让它变得漂亮了！这就是 **CSS (Cascading Style Sheets)** 的作用。
如果说 HTML 是房子的骨架，那 CSS 就是房子的**装修和美化**。它负责控制网页的样式和布局，比如文字的颜色、大小、字体，元素的边距、背景，以及如何排列等等。CSS 让你的网页看起来更专业、更吸引人，而不是单调的黑白文字。
### **CSS 代码解释：选择器和属性**
---
CSS 的基本语法非常简单：它由**选择器**和**声明块**组成。
- **选择器 (Selector):** 告诉浏览器你要对哪个 HTML 元素应用样式。在上面的例子中，`body`、`h1`、`p` 和 `img` 都是选择器，它们直接选择了对应的 HTML 标签。
- **声明块 (Declaration Block):** 包含了一系列用大括号 `{}` 包裹的声明，每个声明由一个**属性 (Property)** 和一个**值 (Value)** 组成，中间用冒号 `:` 分隔，末尾用分号 `;` 结束。
    - 例如：`color: #007bff;` 这里 `color` 是属性，`#007bff` 是值。
### **常用 CSS 属性关键字**
---
一些常用的 CSS 关键字，这很有帮助！CSS 属性非常多，但有一些是你在日常开发中会频繁用到的“明星选手”。我们来介绍几个常见的：
1. **颜色 (Color):**
    - `color`: 设置文本颜色。
    - `background-color`: 设置元素的背景颜色。
2. **字体和文本 (Font & Text):**
    - `font-family`: 设置字体类型（例如：`'Arial', sans-serif`）。
    - `font-size`: 设置字体大小（例如：`16px`, `1.2em`）。
    - `font-weight`: 设置字体粗细（例如：`bold`, `normal`, `700`）。
    - `text-align`: 设置文本对齐方式（例如：`left`, `right`, `center`, `justify`）。
    - `line-height`: 设置行高，影响行与行之间的垂直空间。
3. **盒模型 (Box Model) - 布局和间距：** 这是 CSS 中一个非常核心的概念，所有 HTML 元素都可以看作是一个“盒子”。
    - `width`: 设置元素的宽度。
    - `height`: 设置元素的高度。
    - `margin`: 设置元素**外边距**，即元素边框以外的空白区域，用于控制元素与其他元素之间的距离。你可以设置 `margin-top`, `margin-right`, `margin-bottom`, `margin-left`，或者简写 `margin: 10px 20px;` (上下，左右)。
    - `padding`: 设置元素**内边距**，即元素内容与边框之间的空白区域。同样可以设置 `padding-top` 等，或简写 `padding: 10px;` (所有方向)。
    - `border`: 设置元素的边框（例如：`border: 1px solid black;`）。
4. **显示和定位 (Display & Positioning):**
    - `display`: 控制元素如何显示以及如何与其他元素交互（例如：`block`, `inline`, `flex`, `grid`）。`block` 元素独占一行，`inline` 元素并排显示。
    - `position`: 控制元素的定位方式（例如：`static`, `relative`, `absolute`, `fixed`, `sticky`）。
这只是一小部分常用的属性，但它们会构成你大部分的样式基础。
---
