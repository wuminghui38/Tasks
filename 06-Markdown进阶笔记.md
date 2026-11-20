# Markdown 进阶笔记

## 一、Markdown 的底层原理

Markdown 本质是**纯文本 + 一套约定符号**。浏览器看到排版，不是它自己“懂”格式，而是中间有个解析器在工作：

- Markdown 文本
- 解析成语法树（AST）
- 生成 HTML
- 浏览器渲染

所以同一份 .md 在不同工具里显示可能略有差别，因为解析器不同。为了统一，社区定了标准 **CommonMark**；GitHub 在它基础上做扩展，叫 **GFM**（GitHub Flavored Markdown），表格、任务列表、脚注、数学公式、mermaid 流程图都是它的扩展。

## 二、Markdown 和常见格式的对比

| 格式 | 本质 | 优点 | 缺点 |
| --- | --- | --- | --- |
| .md | 纯文本 | 体积小、能逐行对比、任何工具都能开 | 排版能力有限 |
| .docx | 压缩的 XML 包 | 排版强、支持批注和审阅 | 体积大、几乎没法做版本对比 |
| .txt | 纯文本 | 最通用 | 没有任何结构 |

**关键差别**：`.md` 和 `.txt` 是纯文本，git 能逐行对比；`.docx` 是二进制包，改完之后 diff 出来全是乱码。这就是代码和文档都用纯文本的原因。

## 三、为什么 AI 更偏爱 .md

我的理解有三点：

1. **结构清晰**：标题、列表、表格本身就是层级信息，模型不用猜哪句是小标题
2. **纯文本无噪声**：没有样式、宏和二进制，token 利用率更高
3. **语料多**：GitHub 上大量 README 和文档都是 md，训练数据里天然就多

## 四、进阶语法

任务列表：

- [x] 已经完成的任务
- [ ] 未完成的任务
- [ ] 今天要写代码

代码块（三个反引号包住，第一行写语言名，会有语法高亮）：

```python
def hello():
    print("这是一段 Python 代码")
```

除了这些，GitHub 还支持脚注、数学公式、mermaid 流程图。

## 五、局限与替代

Markdown 不擅长这几类：

- 杂志式排版、精细的图文混排
- 批注审阅（多人改同一份文档留意见）
- 复杂的嵌套表格

遇到这类文档我会用 Word 或 LaTeX；日常笔记和代码说明，用 md 最省事。

## 六、学习资料

- [CommonMark 规范](https://commonmark.org/)
- [GitHub Flavored Markdown 官方说明](https://github.github.com/gfm/)
- [GitHub Docs：写入 GitHub](https://docs.github.com/zh/get-started/writing-on-github)
