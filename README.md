# MDtoAll

<p align="center">
  <strong>A powerful Markdown conversion toolkit based on Quarkdown</strong>
  <br><br>
  <a href="#features">Features</a> •
  <a href="#installation">Installation</a> •
  <a href="#quick-start">Quick Start</a> •
  <a href="#usage">Usage</a> •
  <a href="#license">License</a>
</p>

---

## About

MDtoAll is a versatile Markdown-based document conversion system forked from [Quarkdown](https://github.com/iamgio/quarkdown). It extends CommonMark and GFM with powerful scripting capabilities, allowing you to transform a single Markdown source into multiple professional output formats.

### Why MDtoAll?

- **One Source, Multiple Outputs**: Write once in Markdown, export to HTML, PDF, slides, or documentation sites
- **Turing-Complete**: Built-in scripting with functions, variables, and control flow
- **Professional Typography**: LaTeX-quality output without LaTeX complexity
- **Live Preview**: Real-time preview with hot reload during editing
- **Extensible**: Rich standard library with layout builders, math support, and more

## Features

### Document Types

- **Plain Documents** - Notion-like continuous flow for websites and notes
- **Paged Documents** - LaTeX-quality books, papers, and reports
- **Slides** - Interactive presentations powered by reveal.js
- **Documentation** - Technical wikis and knowledge bases

### Output Formats

- ✅ HTML (all document types)
- ✅ PDF (via Puppeteer)
- ✅ Plain Text

### Key Capabilities

- 📝 **Function System**: Extend Markdown with `.function {name}` syntax
- 🎨 **Layout Control**: Containers, columns, alignment, and spacing
- 📊 **Rich Content**: Math equations, diagrams, code highlighting
- 🔄 **Dynamic Content**: Variables, loops, and conditional rendering
- 🎯 **Type Safety**: Strongly-typed function parameters
- 🚀 **Fast Compilation**: Optimized Kotlin-based compiler

## Installation

### Prerequisites

- Java 17 or higher
- Node.js and npm (for PDF export)

### macOS/Linux

```bash
# Using Homebrew
brew install quarkdown-labs/quarkdown/quarkdown

# Or using install script
curl -fsSL https://raw.githubusercontent.com/quarkdown-labs/get-quarkdown/refs/heads/main/install.sh | sudo env "PATH=$PATH" bash
```

### Windows

```powershell
# Using install script
irm https://raw.githubusercontent.com/quarkdown-labs/get-quarkdown/refs/heads/main/install.ps1 | iex

# Or using Scoop
scoop bucket add java
scoop bucket add quarkdown https://github.com/quarkdown-labs/scoop-quarkdown
scoop install quarkdown
```

### Manual Installation

1. Download `quarkdown.zip` from [releases](https://github.com/AIPMAndy/MDtoAll/releases)
2. Unzip and add `bin/` to your PATH
3. Verify: `quarkdown --version`

Or build from source:

```bash
./gradlew installDist
```

## Quick Start

### Create Your First Document

```bash
# Create a new project
quarkdown create my-project

# Or manually create a .qd file
echo ".doctype {plain}

# Hello World

This is **MDtoAll** in action!" > hello.qd
```

### Compile

```bash
# Basic compilation
quarkdown c hello.qd

# With live preview
quarkdown c hello.qd -p -w

# Export to PDF
quarkdown c hello.qd --pdf
```

## Usage

### Basic Syntax

MDtoAll extends standard Markdown with functions:

```markdown
.doctype {paged}

# My Document

.tableofcontents

## Introduction

This is a **bold** statement with _emphasis_.

.center
    Centered text block

.row alignment:{spacebetween}
    ![Image 1](img1.png)
    ![Image 2](img2.png)
    ![Image 3](img3.png)
```

### Custom Functions

Define reusable functions:

```markdown
.function {greet}
    name from:
    **Hello, .name!** from .from

.greet {World} from:{MDtoAll}
```

Output: **Hello, World!** from MDtoAll

### Document Types

Set the document type at the beginning:

```markdown
.doctype {plain}   # Default: continuous flow
.doctype {paged}   # Print-ready pages
.doctype {slides}  # Presentation mode
.doctype {docs}    # Documentation site
```

### CLI Options

```bash
quarkdown c <file.qd> [options]

Options:
  -p, --preview     Enable live preview
  -w, --watch       Auto-recompile on file changes
  --pdf             Export to PDF
  --clean           Clean output directory before compiling
  --strict          Strict mode (fail on warnings)
```

## Project Structure

```
MDtoAll/
├── quarkdown-core/          # Core compiler
├── quarkdown-stdlib/        # Standard library
├── quarkdown-html/          # HTML renderer
├── quarkdown-cli/           # Command-line interface
├── quarkdown-lsp/           # Language server
├── docs/                    # Documentation
└── mock/                    # Example documents
```

## Comparison

|                       | MDtoAll/Quarkdown | LaTeX | Typst | AsciiDoc | MDX |
|-----------------------|:-----------------:|:-----:|:-----:|:--------:|:---:|
| Readable syntax       | ✅ | ❌ | ✅ | ✅ | ✅ |
| Full document control | ✅ | ✅ | ✅ | ❌ | ❌ |
| Scripting support     | ✅ | Partial | ✅ | ❌ | ✅ |
| Multiple output types | ✅ | ❌ | Partial | ✅ | ✅ |
| Learning curve        | Low | High | Medium | Low | Low |

## Examples

Check out the [`mock`](mock) directory for comprehensive examples, or view pre-generated PDFs in the [generated repo](https://github.com/quarkdown-labs/generated).

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Credits

MDtoAll is a fork of [Quarkdown](https://github.com/iamgio/quarkdown) by [Giorgio Garofalo](https://github.com/iamgio). We extend our gratitude to the original author and all contributors.

## License

- Core modules: GNU GPLv3
- CLI and LSP: GNU AGPLv3

See [LICENSE](LICENSE) for full details.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/AIPMAndy">Andy</a>
</p>
