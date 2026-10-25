<div align="center">

# 📝 MDtoAll

### 强大的 Markdown 多格式转换工具 | Powerful Markdown Conversion Toolkit

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![GitHub release](https://img.shields.io/github/v/release/AIPMAndy/MDtoAll)](https://github.com/AIPMAndy/MDtoAll/releases)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/AIPMAndy/MDtoAll/pulls)

[English](#english) | [中文](#中文)

</div>

---

## 中文

### 🎯 这是什么？

MDtoAll 是一个基于 [Quarkdown](https://github.com/iamgio/quarkdown) 的 Markdown 增强转换系统。它让你用一份 Markdown 源文件，轻松生成多种专业格式的文档。

**一次编写，随处发布** —— 从笔记到论文，从演示文稿到技术文档，一个工具搞定。

### ✨ 核心特性

#### 📄 多种文档类型
- **普通文档** - 类似 Notion 的连续流式布局，适合网站和笔记
- **分页文档** - LaTeX 级别的排版质量，适合书籍、论文和报告
- **幻灯片** - 基于 reveal.js 的交互式演示文稿
- **技术文档** - 适合 Wiki 和知识库的文档站点

#### 🎨 强大功能
- **函数系统** - 用 `.function {name}` 语法扩展 Markdown
- **图灵完备** - 内置变量、循环和条件渲染
- **专业排版** - LaTeX 质量的输出，但没有 LaTeX 的复杂性
- **实时预览** - 编辑时热重载，所见即所得
- **丰富内容** - 数学公式、图表、代码高亮
- **布局控制** - 容器、列、对齐、间距完全可控

#### 📦 输出格式
- ✅ HTML（支持所有文档类型）
- ✅ PDF（通过 Puppeteer）
- ✅ 纯文本

### 🚀 快速开始

#### 安装要求
- Java 17 或更高版本
- Node.js 和 npm（用于 PDF 导出）

#### macOS/Linux 安装

```bash
# 使用 Homebrew
brew install quarkdown-labs/quarkdown/quarkdown

# 或使用安装脚本
curl -fsSL https://raw.githubusercontent.com/quarkdown-labs/get-quarkdown/refs/heads/main/install.sh | sudo env "PATH=$PATH" bash
```

#### Windows 安装

```powershell
# 使用安装脚本
irm https://raw.githubusercontent.com/quarkdown-labs/get-quarkdown/refs/heads/main/install.ps1 | iex

# 或使用 Scoop
scoop bucket add java
scoop bucket add quarkdown https://github.com/quarkdown-labs/scoop-quarkdown
scoop install quarkdown
```

#### 从源码构建

```bash
git clone https://github.com/AIPMAndy/MDtoAll.git
cd MDtoAll
./gradlew installDist
```

### 📖 使用示例

#### 创建第一个文档

```bash
# 创建新项目
quarkdown create my-project

# 或手动创建 .qd 文件
cat > hello.qd << 'EOF'
.doctype {plain}

# 你好，世界

这是 **MDtoAll** 的演示！

.center
    居中的文本块

## 功能展示

.row alignment:{spacebetween}
    ![图片1](img1.png)
    ![图片2](img2.png)
    ![图片3](img3.png)
EOF
```

#### 编译文档

```bash
# 基础编译
quarkdown c hello.qd

# 实时预览（推荐）
quarkdown c hello.qd -p -w

# 导出 PDF
quarkdown c hello.qd --pdf
```

#### 高级语法示例

**自定义函数：**

```markdown
.function {问候}
    名字 来自:
    **你好，.名字！** 来自 .来自

.问候 {世界} 来自:{MDtoAll}
```

输出：**你好，世界！** 来自 MDtoAll

**文档类型设置：**

```markdown
.doctype {plain}   # 默认：连续流
.doctype {paged}   # 打印就绪的分页
.doctype {slides}  # 演示模式
.doctype {docs}    # 文档站点
```

### 📊 对比其他工具

|                  | MDtoAll | LaTeX | Typst | AsciiDoc | MDX |
|------------------|:-------:|:-----:|:-----:|:--------:|:---:|
| 语法简洁易读     | ✅ | ❌ | ✅ | ✅ | ✅ |
| 完整文档控制     | ✅ | ✅ | ✅ | ❌ | ❌ |
| 脚本支持         | ✅ | 部分 | ✅ | ❌ | ✅ |
| 多种输出格式     | ✅ | ❌ | 部分 | ✅ | ✅ |
| 学习曲线         | 低 | 高 | 中 | 低 | 低 |

### 🤝 贡献

欢迎贡献！请查看 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详情。

### 📜 许可证

- 核心模块：GNU GPLv3
- CLI 和 LSP：GNU AGPLv3

详见 [LICENSE](LICENSE)。

### 🙏 致谢

MDtoAll 是 [Quarkdown](https://github.com/iamgio/quarkdown) 的分支，由 [Giorgio Garofalo](https://github.com/iamgio) 创建。感谢原作者和所有贡献者。

---

## English

### 🎯 What is MDtoAll?

MDtoAll is a versatile Markdown-based document conversion system forked from [Quarkdown](https://github.com/iamgio/quarkdown). It transforms a single Markdown source into multiple professional output formats.

**Write once, publish everywhere** — from notes to papers, from presentations to technical documentation.

### ✨ Key Features

#### 📄 Multiple Document Types
- **Plain Documents** - Notion-like continuous flow for websites and notes
- **Paged Documents** - LaTeX-quality typography for books, papers, and reports
- **Slides** - Interactive presentations powered by reveal.js
- **Documentation** - Technical wikis and knowledge bases

#### 🎨 Powerful Capabilities
- **Function System** - Extend Markdown with `.function {name}` syntax
- **Turing-Complete** - Built-in variables, loops, and conditional rendering
- **Professional Typography** - LaTeX-quality output without LaTeX complexity
- **Live Preview** - Real-time hot reload during editing
- **Rich Content** - Math equations, diagrams, code highlighting
- **Layout Control** - Full control over containers, columns, alignment, spacing

#### 📦 Output Formats
- ✅ HTML (all document types)
- ✅ PDF (via Puppeteer)
- ✅ Plain Text

### 🚀 Quick Start

#### Prerequisites
- Java 17 or higher
- Node.js and npm (for PDF export)

#### Installation on macOS/Linux

```bash
# Using Homebrew
brew install quarkdown-labs/quarkdown/quarkdown

# Or using install script
curl -fsSL https://raw.githubusercontent.com/quarkdown-labs/get-quarkdown/refs/heads/main/install.sh | sudo env "PATH=$PATH" bash
```

#### Installation on Windows

```powershell
# Using install script
irm https://raw.githubusercontent.com/quarkdown-labs/get-quarkdown/refs/heads/main/install.ps1 | iex

# Or using Scoop
scoop bucket add java
scoop bucket add quarkdown https://github.com/quarkdown-labs/scoop-quarkdown
scoop install quarkdown
```

#### Build from Source

```bash
git clone https://github.com/AIPMAndy/MDtoAll.git
cd MDtoAll
./gradlew installDist
```

### 📖 Usage Examples

#### Create Your First Document

```bash
# Create a new project
quarkdown create my-project

# Or manually create a .qd file
cat > hello.qd << 'EOF'
.doctype {plain}

# Hello World

This is **MDtoAll** in action!

.center
    Centered text block

## Feature Showcase

.row alignment:{spacebetween}
    ![Image 1](img1.png)
    ![Image 2](img2.png)
    ![Image 3](img3.png)
EOF
```

#### Compile Documents

```bash
# Basic compilation
quarkdown c hello.qd

# Live preview (recommended)
quarkdown c hello.qd -p -w

# Export to PDF
quarkdown c hello.qd --pdf
```

#### Advanced Syntax Examples

**Custom Functions:**

```markdown
.function {greet}
    name from:
    **Hello, .name!** from .from

.greet {World} from:{MDtoAll}
```

Output: **Hello, World!** from MDtoAll

**Document Type Settings:**

```markdown
.doctype {plain}   # Default: continuous flow
.doctype {paged}   # Print-ready pages
.doctype {slides}  # Presentation mode
.doctype {docs}    # Documentation site
```

### 📊 Comparison with Other Tools

|                       | MDtoAll | LaTeX | Typst | AsciiDoc | MDX |
|-----------------------|:-------:|:-----:|:-----:|:--------:|:---:|
| Readable syntax       | ✅ | ❌ | ✅ | ✅ | ✅ |
| Full document control | ✅ | ✅ | ✅ | ❌ | ❌ |
| Scripting support     | ✅ | Partial | ✅ | ❌ | ✅ |
| Multiple output types | ✅ | ❌ | Partial | ✅ | ✅ |
| Learning curve        | Low | High | Medium | Low | Low |

### 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### 📜 License

- Core modules: GNU GPLv3
- CLI and LSP: GNU AGPLv3

See [LICENSE](LICENSE) for details.

### 🙏 Credits

MDtoAll is a fork of [Quarkdown](https://github.com/iamgio/quarkdown) by [Giorgio Garofalo](https://github.com/iamgio). We extend our gratitude to the original author and all contributors.

---

<div align="center">

**Made with ❤️ by [Andy](https://github.com/AIPMAndy)**

⭐ Star this repo if you find it useful!

</div>

---

<!-- andy-author-card:start -->
## 作者 / About the author

**AI 酋长 Andy（Andy Liu，GitHub/X @AIPMAndy）**：前腾讯/百度 AI 产品专家，大模型独角兽前 VP，现专注 AI + 产品方法论创业。

微信 `AIPMAndy`（备注「MDtoAll」） · [X @AIPMAndy](https://x.com/AIPMAndy) · [Telegram @AIPMAndy](https://t.me/AIPMAndy) · [个人官网 metaver.vip](https://metaver.vip/)

*AI Chief Andy (Andy Liu, @AIPMAndy on GitHub and X) is a former Tencent and Baidu AI product expert and former VP at an LLM unicorn, now a serial entrepreneur focused on AI and product methodology.*

### 作者的其他项目

- [AndySoul](https://github.com/AIPMAndy/AndySoul)：CLAUDE.md / AGENTS.md 规则模板，让 Claude Code、Codex、Cursor 少犯错
- [DNA Memory](https://github.com/AIPMAndy/dna-memory)：Claude Code、Codex 共用的本地 AI Agent 记忆 MCP
- [SafeSkill](https://github.com/AIPMAndy/safeskill)：装 AI Skill 之前，先扫危险命令、提示注入和密钥泄露
- [OpenClaw Skills 中文精选](https://github.com/AIPMAndy/awesome-openclaw-skills-CN)：OpenClaw Skills 分类整理，附国产模型接入指南
- [Grok Bot 中文攻略](https://aipmandy.github.io/grok-bot-handbook/)：AI Agent 中文教程

<!-- andy-author-card:end -->
