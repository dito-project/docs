# 📚 Dito Documentation

<div align="center">
  <img src="src/dito.png" alt="Dito Logo" width="200">
  
  <p><strong>Comprehensive documentation for Dito - A high-performance, extensible reverse proxy server</strong></p>
  
  <p>
    <img src="https://img.shields.io/badge/mdBook-Documentation-orange.svg" alt="mdBook">
    <img src="https://img.shields.io/badge/status-active-green.svg" alt="Status">
    <img src="https://img.shields.io/badge/format-Markdown-blue.svg" alt="Format">
  </p>
</div>

---

## 🌟 Overview

This repository contains the complete documentation for **Dito**, a high-performance reverse proxy server written in Go. The documentation is built using [mdBook](https://rust-lang.github.io/mdBook/) and provides comprehensive guides, tutorials, and reference materials for users and developers.

## 📖 Documentation Structure

The documentation covers all aspects of Dito, from basic installation to advanced plugin development:

### 🚀 Getting Started
- **[Introduction](src/introduction.md)** - What is Dito and why use it
- **[Features](src/features.md)** - Complete overview of Dito's capabilities  
- **[Installation](src/installation.md)** - Step-by-step installation guide
- **[Usage](src/usage.md)** - Basic usage and configuration examples

### 🔧 Configuration & Setup
- **[Project Structure](src/project-structure.md)** - Understanding Dito's architecture
- **[Response Limits](src/response-limits.md)** - Configuring response size limits
- **[Custom Transport](src/custom-transport.md)** - Advanced transport configuration

### 🔌 Advanced Features
- **[Plugin System](src/plugins.md)** - Complete plugin development guide
- **[Metrics](src/metrics.md)** - Monitoring and observability setup
- **[Containerization & OpenShift](src/containerization.md)** - Container deployment guides

### 🤝 Community
- **[Contributing](src/contributing.md)** - How to contribute to Dito
- **[Reporting Issues](src/reporting-issues.md)** - Bug reporting guidelines
- **[License](src/license.md)** - Licensing information

## 🛠️ Building the Documentation

### Prerequisites

You need to have [mdBook](https://rust-lang.github.io/mdBook/) installed:

```bash
# Install mdBook via Cargo (requires Rust)
cargo install mdbook

# Or on macOS via Homebrew
brew install mdbook

# Or download from GitHub releases
# https://github.com/rust-lang/mdBook/releases
```

### Build Commands

```bash
# Build the documentation
mdbook build

# Serve locally with live reload (recommended for development)
mdbook serve

# Serve on a specific port
mdbook serve --port 3001

# Build and open in browser
mdbook serve --open
```

The built documentation will be available in the `book/` directory.

## 🚀 Deployment

The documentation is built locally and deployed to Cloudflare Pages:

1. **Build locally**: `mdbook build`
2. **Commit the book/ directory**: The built HTML files are committed to the repository
3. **Cloudflare Pages**: Automatically serves the `book/` directory as a static site

### Deployment Workflow

```bash
# Make your changes to src/ files
mdbook build
git add book/
git commit -m "Update documentation"
git push origin main
```

Cloudflare Pages is configured to serve the `book/` directory directly, making deployment simple and fast.

**Note**: The `book/` directory contains the built HTML files and is intentionally committed to the repository for Cloudflare Pages deployment.

## 🌐 Live Documentation

The documentation is automatically built and deployed. You can access it at:

- **Production**: [ditoproxy.com](https://ditoproxy.com)
- **Development**: Run `mdbook serve` locally on `http://localhost:3000`

## 📁 Repository Structure

```
docs/
├── README.md              # This file - Documentation overview
├── LICENSE                # Apache License 2.0
├── .gitignore            # Git ignore rules
├── book.toml             # mdBook configuration
├── src/                  # Markdown source files
│   ├── SUMMARY.md        # Table of contents
│   ├── *.md              # Documentation chapters
│   └── dito.png          # Assets and images
└── book/                 # Generated HTML output (after build)
    ├── index.html
    └── ...               # Static website files
```

## ✨ Key Features of This Documentation

- **📱 Responsive Design** - Works perfectly on desktop, tablet, and mobile
- **🔍 Full-text Search** - Quickly find any information
- **🎨 Syntax Highlighting** - Beautiful code examples with proper highlighting
- **📋 Copy-to-clipboard** - Easy copying of code snippets
- **🔗 Cross-references** - Seamless navigation between topics
- **📊 Print Support** - Generate PDF versions for offline reading
- **♿ Accessible** - Built with accessibility standards in mind

## 🤝 Contributing to Documentation

We welcome contributions to improve the documentation! Here's how you can help:

### Quick Edits

1. **Edit directly on GitHub** - Click the "Edit" button on any page
2. **Submit a Pull Request** - GitHub will guide you through the process

### Local Development

1. **Fork this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/docs.git
   cd docs
   ```

2. **Make your changes**
   ```bash
   # Edit files in src/
   vim src/your-file.md
   ```

3. **Test locally**
   ```bash
   mdbook serve
   # Open http://localhost:3000 to preview
   ```

4. **Submit Pull Request**
   ```bash
   git add .
   git commit -m "Improve documentation for X feature"
   git push origin your-branch-name
   ```

### Documentation Guidelines

- **Clear and Concise** - Write for users of all skill levels
- **Code Examples** - Include working examples for all features
- **Screenshots** - Add visuals when they help explain concepts
- **Cross-links** - Link to related sections when relevant
- **Test Examples** - Ensure all code examples work correctly

## 🐛 Reporting Documentation Issues

Found an issue with the documentation? Please help us improve:

1. **Check existing issues** - Search [GitHub Issues](https://github.com/dito-project/docs/issues)
2. **Create a new issue** - Use our issue template
3. **Provide details**:
   - Which page/section has the issue
   - What's wrong or missing
   - Suggested improvements
   - Screenshots if relevant

## 🔗 Related Resources

- **[Main Dito Repository](https://github.com/dito-project/dito)** - Source code and releases
- **[mdBook Guide](https://rust-lang.github.io/mdBook/)** - Learn more about mdBook
- **[Markdown Guide](https://www.markdownguide.org/)** - Markdown syntax reference

## 📄 License

This documentation is licensed under the same terms as the Dito project - Apache License 2.0. See [LICENSE](book/src/license.md) for details.

---


