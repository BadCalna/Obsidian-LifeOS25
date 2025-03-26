<%*
// --- Templater Script for Course Notes (v2 - Robust Naming & Escaping) ---

// Function to sanitize potential filename characters
function sanitizeFilename(name) {
  // Remove characters forbidden in Windows/Mac filenames and limit length
  // Adjust the regex as needed, this is a basic example
  return name.replace(/[\\/:*?"<>|]/g, '-').substring(0, 100);
}

// 1. Get Course Name and set Title
const courseNameInput = await tp.system.prompt("请输入课程名称", tp.file.title.replace(/\.md$/, ""));
const initialTitle = tp.file.title.replace(/\.md$/, "");
let finalCourseName = initialTitle; // Default to initial title

if (courseNameInput && courseNameInput.trim() !== "") { // If user provided valid input
    finalCourseName = sanitizeFilename(courseNameInput.trim()); // Sanitize user input
} else if (initialTitle === "Untitled" || initialTitle === "") { // If no input and title is "Untitled" or empty
    // Create a safer default name if input is empty and title is generic
    const dateTimeString = tp.date.now("YYYYMMDDHHmmss");
    finalCourseName = sanitizeFilename(`Untitled Course ${dateTimeString}`);
} else {
    // Keep the existing title if it's not "Untitled" and no input was given, but sanitize it just in case
    finalCourseName = sanitizeFilename(initialTitle);
}

// Rename only if necessary and the final name is not empty
if (finalCourseName && finalCourseName !== initialTitle) {
    try {
        await tp.file.rename(finalCourseName);
    } catch (e) {
        console.error("Templater: Failed to rename file:", e);
        // Use Obsidian's notice mechanism to inform the user
        new Notice(`Templater: Failed to rename file to "${finalCourseName}". Please rename manually.`, 10000); // Show notice for 10 seconds
        // Even if rename fails, proceed with 'finalCourseName' for content generation
    }
} else if (!finalCourseName) {
    // If somehow finalCourseName became empty, use a safe fallback
    const dateTimeString = tp.date.now("YYYYMMDDHHmmss");
    finalCourseName = `Recovered Course ${dateTimeString}`;
    console.warn("Templater: Course name was empty, using fallback:", finalCourseName);
}


// 2. Get Course URL
const courseURL = await tp.system.prompt("请输入课程链接 (URL)");

// 3. Get Status
// Handle potential cancellation of suggester (returns null)
const statusChoice = await tp.system.suggester(
    ["未开始", "进行中", "已完成"], // Display options
    ["未开始", "进行中", "已完成"], // Actual values to insert
    false, // Allow multi-select? No.
    "请选择当前学习状态" // Placeholder text
);
const status = statusChoice ?? '未开始'; // Use '未开始' if user cancels

// 4. Get Topic Tags (Optional)
const topicTagsInput = await tp.system.prompt("请输入主题标签 (用逗号分隔, 例如: 机器学习, Python, 可选)");
let topicTags = [];
if (topicTagsInput && topicTagsInput.trim() !== "") {
  topicTags = topicTagsInput.split(',')
                          .map(tag => tag.trim()) // Remove leading/trailing whitespace
                          .filter(tag => tag !== "") // Remove empty tags resulting from extra commas
                          .map(tag => `topic/${tag.replace(/\s+/g, '-')}`); // Add prefix and replace spaces with hyphens
}

// 5. Get Creation Date
const creationDate = tp.date.now("YYYY-MM-DD");

// --- Generate Frontmatter ---
tR += `---
course_name: "${finalCourseName.replace(/"/g, '\\"')}" # Escape double quotes in course name for YAML
url: "${courseURL || ''}"
status: ${status}
tags:
  - course
${topicTags.map(tag => `  - ${tag}`).join('\n')}
creation_date: ${creationDate}
---

# 🎓 ${finalCourseName}

> [!INFO] 核心信息
> **状态:** ${status}
> **课程链接:** ${courseURL ? \`[\${finalCourseName} Link](${courseURL})\` : '未提供'}
> **创建日期:** ${creationDate}

---

## 📚 课程概览

*   **课程目标:**
    *   (在此处简述课程的主要学习目标)
*   **内容概要:**
    *   (在此处简述课程涵盖的主要内容或模块)

---

## 🗓️ 课程大纲与笔记链接

*建议为每周或每个模块创建单独的笔记，并在此处链接。这有助于保持笔记的原子性和关联性。*

*   **Week 1 / Module 1:** [[${finalCourseName} - W1 内容概要]]
    *   [[${finalCourseName} - W1 视频笔记]]
    *   [[${finalCourseName} - W1 阅读材料]]
*   **Week 2 / Module 2:** [[${finalCourseName} - W2 内容概要]]
    *   ...
*   **(根据实际课程结构调整)**

*(点击灰色链接即可创建对应的笔记文件)*

---

## 💡 关键概念 / 术语表

> [!NOTE] Key Concepts
> *(在此记录学习过程中遇到的重要概念、定义或术语)*
>
> *   **概念 1:** 解释...
>     *   相关笔记: [[相关笔记链接]]
> *   **术语 A:** 定义...

---

## ✅ 作业 / 项目 / Quiz

*使用任务列表跟踪进度。可以为复杂的作业创建单独的笔记并链接。*

- [ ] 作业 1: (简要描述) - \`duedate:: YYYY-MM-DD\`
- [ ] Quiz 1: 完成情况或笔记链接 [[${finalCourseName} - Quiz 1 复盘]]
- [ ] 项目: (项目名称) - [[${finalCourseName} - 项目详情]]

---

## 🔗 相关资源

*   **官方资料:**
    *   [课程主页](${courseURL || '#'})
    *   [讲义/Slides](在这里添加链接)
    *   [代码库/数据集](在这里添加链接)
*   **推荐阅读:**
    *   [文章/书籍名称](在这里添加链接)
*   **实用工具:**
    *   [工具名称](在这里添加链接)

---

## 🤔 总结与反思

*(课程完成或阶段性学习后的总结、思考、收获和待办事项)*

*   **主要收获:**
*   **遇到的难点:**
*   **后续学习计划:**

---

## ✨ 相关子笔记 (Dataview)

*此部分自动列出与本课程相关的、位于同一个文件夹下的其他笔记。*

\`\`\`dataview
LIST
FROM [[]] AND !"templates" AND !#templates
WHERE contains(file.folder, this.file.folder) AND file.name != this.file.name
SORT file.cday ASC
\`\`\`

`; // End of tR +=
%>