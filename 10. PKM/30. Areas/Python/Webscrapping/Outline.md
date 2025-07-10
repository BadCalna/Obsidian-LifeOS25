## Python 网络爬虫完整课程大纲
### 第一课：网络基础与 HTTP/HTTPS 协议
这节课是爬虫的基石，我们将深入了解互联网数据传输的原理。
1. **课程教学部分**：
    - **什么是网络爬虫？** 为什么我们需要它，它能做什么。
    - **客户端与服务器模型**: 浏览器如何与服务器交互。
    - **HTTP/HTTPS 协议详解**:
        - **请求（Request）与响应（Response）**: 它们的结构、组成部分（请求行、请求头、请求体，响应行、响应头、响应体）。
        - **请求方法**: GET、POST、PUT、DELETE 等常用方法的区别与应用场景。
        - **状态码**: 200、301、302、403、404、500 等常见状态码的含义。
        - **头部信息（Headers）**: 重要的请求头（User-Agent, Referer, Cookie, Accept-Encoding 等）和响应头。
        - **Cookies 与 Session**: 它们在网站登录和状态保持中的作用。
    - **抓包工具简介**: 简单介绍 Fiddler 或 Wireshark 等工具的作用，帮助理解网络请求。
2. **实战案例**：
    - 使用 `curl` 命令或浏览器开发者工具分析一个简单网页的 HTTP 请求和响应，理解请求头和响应头的具体内容。
3. **重点知识总结**：
    - HTTP/HTTPS 是网络通信的基础。
    - 理解请求与响应的构成、请求方法、状态码和头部信息是爬虫的关键。
    - Cookies 和 Session 用于维护用户登录状态。
4. **配套知识编程题**：
    - **题目**：请解释 GET 和 POST 请求方法的主要区别和各自适合的使用场景。
---
### 第二课：HTML 与 CSS 基础——网页的骨架与样式
理解网页结构是提取数据的关键。
1. **课程教学部分**：
    - **HTML 基础**:
        - **HTML 文档结构**: `<!DOCTYPE>`, `<html>`, `<head>`, `<body>`。
        - **常用标签**: `<div>`, `<span>`, `<a>`, `<p>`, `<h1>` - `<h6>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<img>`, `<form>`, `<input>` 等。
        - **标签属性**: `id`, `class`, `href`, `src`, `name`, `value` 等。
        - **DOM (文档对象模型)**: 树形结构的概念，它是如何表示 HTML 文档的。
    - **CSS 基础**:
        - **CSS 作用**: 美化网页、定位元素。
        - **常用选择器**: 元素选择器、类选择器 (`.class`)、ID 选择器 (`#id`)、属性选择器、后代选择器、子选择器。
        - 了解 CSS 如何影响元素的显示，从而帮助我们定位元素。
2. **实战案例**：
    - 打开一个常见的网页，例如某个新闻网站的首页。
    - 使用浏览器开发者工具（Elements 标签页），分析其 HTML 结构，尝试定位新闻标题、链接、发布时间等信息，并观察其对应的 CSS 类或 ID。
3. **重点知识总结**：
    - HTML 提供了网页的骨架和内容，DOM 是 HTML 文档的内存表示。
    - CSS 决定了网页的样式，其选择器是定位元素的强大工具。
    - 熟练使用浏览器开发者工具是分析网页结构的核心技能。
4. **配套知识编程题**：
    - **题目**：假设有一个 HTML 元素 `<div class="product-info" id="item-123"><p class="title">商品名称</p><span class="price">¥99.99</span></div>`。
        - 请写出获取 class 为 "product-info" 的 `div` 元素的 CSS 选择器。
        - 请写出获取 `id` 为 "item-123" 的 `div` 元素的 CSS 选择器。
        - 请写出获取 class 为 "title" 的 `p` 元素的 CSS 选择器。
---
### 第三课：Python `requests` 库——发起 HTTP 请求
这节课我们将学习如何用 Python 来模拟浏览器发送请求。
1. **课程教学部分**：
    - **`requests` 库安装与基本用法**: `pip install requests`。
    - **发起 GET 请求**: `requests.get()` 方法，传递 URL、参数 (`params`)。
    - **发起 POST 请求**: `requests.post()` 方法，传递 URL、数据 (`data` 或 `json`)。
    - **定制请求头**: `headers` 参数的使用，模拟浏览器 User-Agent。
    - **处理响应**: 响应对象 (`Response`) 的属性和方法（`status_code`, `text`, `content`, `json()`, `encoding`）。
    - **超时设置**: `timeout` 参数，避免程序长时间等待。
    - **代理设置**: `proxies` 参数，通过代理服务器发送请求。
    - **Cookies 处理**: 从响应中获取 Cookies，在后续请求中携带 Cookies。
    - **会话（Session）对象**: `requests.Session()` 的作用，自动处理 Cookies 和持久化连接。
2. **实战案例**：
    - 使用 `requests` 库访问一个公开的 API 接口（例如：[JSONPlaceholder](https://jsonplaceholder.typicode.com/)），获取模拟的用户列表数据。
    - 尝试修改请求头中的 `User-Agent`，观察对响应的影响（如果目标网站有反爬）。
3. **重点知识总结**：
    - `requests` 库是 Python 中最常用的 HTTP 请求库，功能强大且易用。
    - 掌握 GET/POST 请求、请求头定制、超时和代理是爬虫的基础操作。
    - `Session` 对象对于模拟登录和维持会话非常重要。
4. **配套知识编程题**：
    - **题目**：请编写一个 Python 程序，使用 `requests` 库向 `http://httpbin.org/get` 发送一个 GET 请求，并在请求头中添加 `User-Agent` 为 "MyCustomSpider"。打印响应的状态码和响应的 JSON 内容。
---
### 第四课：Python `Beautiful Soup` 库——解析 HTML
学习如何从杂乱的 HTML 中提取出我们想要的数据。
1. **课程教学部分**：
    - **`Beautiful Soup` 库安装与基本用法**: `pip install beautifulsoup4`。
    - **解析器**: 介绍 `html.parser`, `lxml`, `xml` 等解析器的选择。
    - **创建 `BeautifulSoup` 对象**: `BeautifulSoup(html_doc, 'parser_name')`。
    - **定位元素**:
        - **标签名查找**: `soup.title`, `soup.a`。
        - **`find()` 和 `find_all()` 方法**: 根据标签名、属性、文本内容查找单个或所有匹配的元素。
        - **CSS 选择器查找**: `select()` 方法，使用 CSS 选择器进行复杂查找。
        - **通过属性查找**: `attrs` 参数。
    - **提取数据**:
        - **获取标签文本**: `tag.get_text()`。
        - **获取属性值**: `tag['attribute_name']`。
        - **导航关系**: `.parent`, `.children`, `.next_sibling`, `.previous_sibling` 等。
2. **实战案例**：
    - 选择一个简单的静态新闻网页（例如，维基百科的一个页面），使用 `requests` 获取其 HTML 内容。
    - 然后使用 `Beautiful Soup` 解析 HTML，提取页面中的所有标题（`<h1>` - `<h6>`）和所有链接 (`<a>` 标签的 `href` 属性)。
3. **重点知识总结**：
    - `Beautiful Soup` 是一个强大的 HTML/XML 解析库。
    - `find()`, `find_all()` 和 `select()` 是最常用的元素定位方法。
    - 掌握如何提取文本内容和属性值是数据提取的核心。
4. **配套知识编程题**：
    - **题目**：给定以下 HTML 片段：
        HTML
        ```
        <div class="container">
            <h2 id="title">最新文章</h2>
            <ul>
                <li class="item"><a href="/article/1">文章1</a></li>
                <li class="item"><a href="/article/2">文章2</a></li>
                <li class="item"><a href="/article/3">文章3</a></li>
            </ul>
        </div>
        ```
        请使用 `Beautiful Soup` 编写 Python 代码：
        1. 获取 `id` 为 "title" 的 `h2` 标签的文本内容。
        2. 获取所有 `class` 为 "item" 的 `li` 标签中的 `a` 标签的 `href` 属性和文本内容。
---
### 第五课：XPath 与 `lxml`——更高效的解析利器
了解另一种强大的解析方式，尤其在处理复杂文档时效率更高。
1. **课程教学部分**：
    - **XPath 简介**: 什么是 XPath，为什么它比 CSS 选择器更强大。
    - **XPath 语法**:
        - **节点选择**: `/`, `//`, `.` , `..`。
        - **谓词 (Predicates)**: `[]` 筛选，例如 `//div[@id="xxx"]`。
        - **轴 (Axes)**: `parent::`, `child::`, `ancestor::`, `descendant::`, `following-sibling::` 等。
        - **常用函数**: `text()`, `contains()`, `starts-with()`, `last()` 等。
    - **`lxml` 库**:
        - **安装**: `pip install lxml`。
        - **结合 `requests` 获取 HTML**: `response.text`。
        - **解析 HTML**: `etree.HTML()`。
        - **使用 XPath 表达式提取数据**: `tree.xpath('xpath_expression')`。
        - **与 `Beautiful Soup` 的对比**: 效率和语法差异。
2. **实战案例**：
    - 重新使用第四课的静态新闻网页。
    - 尝试用 `lxml` 结合 XPath 提取相同的数据（标题和链接），比较其语法和效率。
    - 尝试用 XPath 表达更复杂的定位需求，例如：获取某个 `div` 下的第三个 `p` 标签的文本。
3. **重点知识总结**：
    - XPath 是一种强大的 XML/HTML 路径语言，能够精确、灵活地定位元素。
    - `lxml` 库提供高效的 HTML/XML 解析和 XPath 支持。
    - 掌握 XPath 语法能让你在复杂网页中游刃有余。
4. **配套知识编程题**：
    - **题目**：给定以下 HTML 片段：
        HTML
        ```
        <div id="products">
            <div class="item">
                <h3>产品A</h3>
                <span class="price">¥100</span>
            </div>
            <div class="item">
                <h3>产品B</h3>
                <span class="price">¥200</span>
            </div>
        </div>
        ```
        请使用 `lxml` 和 XPath 编写 Python 代码：
        1. 获取所有产品 `item` 的 `h3` 标签的文本内容。
        2. 获取 `产品B` 对应的价格（即第二个 `item` 下的 `span` 标签的文本内容）。
---
### 第六课：数据存储——将爬虫成果落地
爬取到的数据需要被妥善保存才能发挥价值。
1. **课程教学部分**：
    - **文本文件存储**:
        - **CSV 格式**: 逗号分隔值，简单易用，适合表格数据。
        - **JSON 格式**: JavaScript 对象表示法，适合结构化数据，易于程序解析。
        - 文件读写操作：`open()`, `write()`, `close()`, `with open() as f:`。
    - **数据库存储**:
        - **关系型数据库简介**: 表、行、列的概念。
        - **SQLite3**: Python 内置的轻量级数据库，适合小型项目和本地存储。
            - 连接数据库、创建表、插入数据、查询数据。
        - **MySQL/PostgreSQL (概念性介绍)**: 更大型、专业的数据库，了解其在爬虫中的应用场景。
    - **MongoDB (概念性介绍)**: 非关系型数据库（NoSQL），适合存储非结构化和半结构化数据。
2. **实战案例**：
    - 延续之前的爬取案例（例如新闻标题和链接）。
    - 将爬取到的数据保存为 CSV 文件。
    - 尝试将数据保存为 JSON 文件。
    - 使用 SQLite3 创建一个数据库，并将爬取到的数据插入到数据库表中。
3. **重点知识总结**：
    - 根据数据类型和项目需求选择合适的存储方式。
    - CSV 和 JSON 是常用的文件存储格式。
    - SQLite3 简单易用，适合本地数据存储和小型项目。
    - 数据库存储能更好地管理和查询大量结构化数据。
4. **配套知识编程题**：
    - **题目**：假设你爬取到了一系列电影信息，每部电影包含 `title` (电影名) 和 `score` (评分)。请编写 Python 代码，将这些电影信息保存到一个名为 `movies.json` 的 JSON 文件中，并同时保存到一个名为 `movies.db` 的 SQLite 数据库表中。
        Python
        ```
        movies_data = [
            {"title": "肖申克的救赎", "score": 9.7},
            {"title": "霸王别姬", "score": 9.6},
            {"title": "阿甘正传", "score": 9.5}
        ]
        ```
---
### 第七课：高级爬虫技巧与反爬策略（上）
网站为了防止被恶意爬取，会采取各种反爬措施。这节课我们学习如何应对。
1. **课程教学部分**：
    - **模拟登录与会话管理**:
        - **基于表单提交的登录**: POST 请求发送用户名和密码。
        - **基于 Cookies 的登录**: 登录后获取 Cookies，后续请求携带 Cookies。
        - **`requests.Session` 再次深入**: 维持登录状态的利器。
    - **代理 IP 池**:
        - **为什么需要代理**: 应对 IP 限制。
        - **免费代理与付费代理**: 各自的优缺点。
        - **代理的使用**: `proxies` 参数，如何构建和管理代理池。
        - **代理的有效性检测**: 简单检测代理是否可用。
    - **User-Agent 轮换**:
        - 为什么网站会检查 User-Agent。
        - 如何维护一个 User-Agent 列表并随机选择。
2. **实战案例**：
    - **模拟登录一个允许的网站**（例如，一个测试网站或你自己搭建的网站，切勿尝试在未经授权的生产网站上进行）。演示如何通过 `requests.Session` 保持登录状态并访问登录后才能看到的页面。
    - 集成一个简单的代理 IP 列表，尝试使用代理访问一个受限网站（如果目标网站有 IP 限制）。
3. **重点知识总结**：
    - 模拟登录需要理解网站的认证机制，`requests.Session` 是核心。
    - 代理 IP 池是应对 IP 封禁的有效手段。
    - 轮换 User-Agent 能够模拟更真实的浏览器行为。
4. **配套知识编程题**：
    - **题目**：请编写一个 Python 函数，接受一个 URL 列表和一个代理 IP 列表。函数应该随机选择一个代理 IP，并使用该代理 IP 访问 URL 列表中的每个 URL。如果访问失败（例如，状态码不是 200），则尝试下一个代理 IP。
---
### 第八课：高级爬虫技巧与反爬策略（下）
继续学习更复杂的反爬虫技术和应对方法。
1. **课程教学部分**：
    - **验证码识别**:
        - **图片验证码**:
            - 人工打码平台（概念性介绍）。
            - OCR (光学字符识别) 技术：`Pillow` (PIL) 库进行图像处理，`pytesseract` 调用 Tesseract OCR 引擎 (概念性介绍)。
        - **滑动验证码/点选验证码**: 介绍其原理和大致的应对思路（例如，缺口识别、模拟轨迹等，不要求实操）。
    - **页面渲染延迟与 Ajax 加载**:
        - 为什么有些数据直接 `requests` 拿不到。
        - 理解 Ajax (Asynchronous JavaScript and XML) 的原理。
        - 如何通过浏览器开发者工具的 **Network 标签页** 找到隐藏的 Ajax 请求。
    - **多线程/异步并发**:
        - **为什么需要并发**: 提高爬取效率。
        - **多线程 `concurrent.futures.ThreadPoolExecutor`**: 简单实现并发请求。
        - **异步 `asyncio` + `aiohttp` (概念性介绍)**: 更高效的并发方式，尤其适合 I/O 密集型任务。
2. **实战案例**：
    - 选择一个通过 Ajax 动态加载内容的网页（例如，某些评论区或商品列表）。
    - 使用浏览器开发者工具分析其 Ajax 请求，找到实际的数据接口。
    - 直接使用 `requests` 库向该 Ajax 接口发送请求，获取动态加载的数据。
3. **重点知识总结**：
    - 验证码是常见的反爬机制，可以通过 OCR 或第三方服务应对。
    - Ajax 是动态加载内容的关键，直接请求 Ajax 接口通常比模拟浏览器更高效。
    - 并发技术是提高爬虫效率的必要手段。
4. **配套知识编程题**：
    - **题目**：请编写一个 Python 程序，模拟并发请求。定义一个函数 `fetch_url(url)`，该函数使用 `requests` 访问给定的 URL 并返回响应状态码。然后使用 `ThreadPoolExecutor` 创建 5 个线程，并发地访问以下 URL 列表，并打印每个 URL 的状态码：
        ```
        urls = ["http://httpbin.org/status/200", "http://httpbin.org/status/404", "http://httpbin.org/status/500", "http://httpbin.org/status/200", "http://httpbin.org/status/403"]
        ```
---
### 第九课：JavaScript 逆向工程（上）——动态渲染与自动化工具
这一课开始进入高级阶段，我们将学习如何处理 JavaScript 渲染的网页。
1. **课程教学部分**：
    - **为什么需要 JS 逆向**: 传统 `requests` 无法获取 JS 动态生成的内容。
    - **动态渲染网页**: 客户端 JavaScript 在浏览器中渲染 HTML 内容。
    - **`Selenium` 库**:
        - **安装**: `pip install selenium`。
        - **WebDriver**: 驱动浏览器（Chrome/Firefox）进行自动化操作。
        - **基本操作**: 打开网页、查找元素（`find_element_by_*`）、点击、输入、等待（隐式等待、显式等待）。
        - **获取动态 HTML**: `driver.page_source`。
        - **处理 `iframe` 和弹窗**: 切换上下文。
    - **`Playwright` 库 (概念性介绍)**: 另一个优秀的自动化库，提供异步支持和更现代的 API。
    - **无头模式 (Headless Mode)**: 在没有图形界面的情况下运行浏览器。
2. **实战案例**：
    - 选择一个需要 JS 渲染才能看到完整内容的网页（例如，一个有“加载更多”按钮的商品列表或评论区）。
    - 使用 `Selenium` 启动一个浏览器，访问该网页，点击“加载更多”按钮，然后获取加载完成后的页面 HTML 内容。
    - 从获取的 HTML 中提取数据。
3. **重点知识总结**：
    - `Selenium` 和 `Playwright` 是处理 JavaScript 动态渲染网页的利器。
    - 它们通过模拟真实的浏览器行为来获取最终渲染的 HTML。
    - 熟练掌握 WebDriver 的操作方法是使用这些工具的关键。
4. **配套知识编程题**：
    - **题目**：请编写一个 Python 程序，使用 `Selenium` 打开 `http://quotes.toscrape.com/js/` (一个专门用于练习 JS 爬取的网站)，等待页面加载完成（例如，等待某个元素出现），然后打印页面中所有的名言文本内容。
---
### 第十课：JavaScript 逆向工程（下）——分析与模拟
这是爬虫领域最核心和最具挑战性的部分。
1. **课程教学部分**：
    - **浏览器开发者工具高级应用**:
        - **Network 标签页**: 分析 Ajax/XHR 请求、JS 文件加载、Headers、Payload、Preview。
        - **Sources 标签页**: 断点调试 JavaScript 代码、查看变量值、单步执行。
        - **Console 标签页**: 执行 JS 代码、打印调试信息。
    - **JS 加密与混淆**:
        - **常见加密算法**: MD5, SHA1, AES, RSA (概念性介绍)。
        - **JS 混淆**: 代码压缩、变量名替换、控制流平坦化等。
        - **逆向思路**: 定位关键代码、分析加密/签名算法、模拟实现。
    - **Hook 技术 (概念性介绍)**: 在运行时修改或拦截 JavaScript 函数。
    - **AST (抽象语法树) (概念性介绍)**: 对 JavaScript 代码进行结构化分析。
    - **实际案例分析方法论**: 遇到 JS 逆向问题时，如何一步步分析和解决。
2. **实战案例**：
    - 选择一个带有简单 JS 加密参数的网站（如果找不到公开的，我们可以模拟一个场景，例如某个网站的请求参数或 cookie 值是由一段 JavaScript 计算生成的）。
    - **通过浏览器开发者工具分析其 Network 请求和 Sources 代码**，找出生成关键参数的 JavaScript 片段。
    - **尝试用 Python 模拟该 JavaScript 计算过程**，生成相同的参数，然后使用 `requests` 库携带这些参数发送请求。
3. **重点知识总结**：
    - **浏览器开发者工具是 JS 逆向的“瑞士军刀”**。
    - JS 逆向的核心是分析并模拟 JavaScript 的行为，尤其关注数据加密、签名和动态加载逻辑。
    - 这个过程需要耐心、细致的分析和一定的编程功底。
4. **配套知识编程题**：
    - 题目：假设有一个网页，它的某个数据请求（POST 请求）的 data 中有一个 sign 参数，这个 sign 是由 JavaScript 代码 MD5(timestamp + "some_secret_key") 生成的，其中 timestamp 是当前时间戳（秒级）。
        请你：
        1. 用 Python 计算出当前的 `timestamp`。
        2. 结合给定的“秘钥”`"some_secret_key"`，计算出对应的 MD5 值作为 `sign`。
        3. 使用 requests 库向 http://httpbin.org/post 发送一个 POST 请求，请求体中包含 timestamp 和 sign 参数，并打印响应。
            提示：Python 的 hashlib 库可用于计算 MD5。
---
## 课程最终实战项目：综合爬虫项目挑战
在完成所有课程后，你将面对一个综合性的实战项目，它会要求你运用学到的所有知识和技能。
### 项目目标：
爬取一个特定网站（我会提供一个适合练习的，或者我们共同选择一个），获取其多页数据，并处理可能存在的反爬机制、JS 动态渲染甚至简单的 JS 逆向挑战。
### 项目要求：
1. **多页数据抓取**: 能够自动抓取多页内容。
2. **数据解析**: 准确提取目标数据（例如，商品名称、价格、评论、发布时间等）。
3. **反爬处理**:
    - 使用 `User-Agent` 轮换。
    - 如果网站有 IP 限制，尝试使用代理 IP。
    - 处理简单的图片验证码（如果存在，可使用第三方打码服务或简单 OCR 尝试）。
4. **动态内容处理**:
    - 如果数据是 JS 动态加载的，需要使用 `Selenium` 或 `Playwright`。
    - 如果数据通过 Ajax 请求获取，则需要分析 XHR 请求并直接抓取。
5. **JS 逆向 (如果适用)**: 如果网站的关键参数通过 JavaScript 加密或混淆生成，你需要逆向分析并用 Python 模拟其生成过程。
6. **数据存储**: 将爬取到的数据保存到 CSV 文件或 SQLite 数据库中。
7. **代码结构**: 编写清晰、模块化、有注释的代码。
8. **错误处理**: 妥善处理网络请求失败、解析错误等异常情况。