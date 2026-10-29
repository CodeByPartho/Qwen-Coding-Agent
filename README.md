<div align="center">

  <h1>Qwen Code Interface</h1>

  <p><b>A lightweight desktop interface for local text generation and codebase refactoring</b></p>

  <p>
    A Python-based developer tool designed for local text generation, AST-aware refactoring, syntax checking, and automated test execution.
  </p>

  <p>
    <a href="https://www.python.org"><img src="https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.11" /></a>
    <a href="https://ollama.com"><img src="https://img.shields.io/badge/Runtime-Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama" /></a>
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License" /></a>
  </p>

</div>

---

## Overview

**Qwen Code Interface** provides a developer interface for running local text generation models and automating multi-file editing and verification workflows.

Built with Python, it provides tools for directory navigation, regex editing, terminal execution, and test-driven validation.

---

## Key Features

- **Offline Local Execution** — Connects directly to local model runtimes via Ollama for on-device generation without external network dependencies.
- **AST Refactoring & Regex Editing** — Targeted file modification using contiguous multi-line regex match and syntax tree verification.
- **Automated Test Validation** — Automatically executes test commands against modified files and reports runtime traces.
- **Workspace Sandboxing** — Non-destructive directory isolation to protect untracked files during automated operations.

---

## Workflow

```mermaid
graph TD
    User([Task / Prompt]) --> Core[Execution Engine]
    
    Core --> Router{Tool Dispatch}
    Router --> ReadFile[File Search & Reader]
    Router --> EditFile[Contiguous Multi-Line Editor]
    Router --> RunTerminal[Test & Compiler Execution]
    
    ReadFile --> Context[Context Accumulator]
    EditFile --> TestRunner[Test Verification]
    RunTerminal --> TestRunner
    
    TestRunner --> ErrorCheck{Tests Pass?}
    ErrorCheck -->|No| FixLoop[Error Trace Analysis]
    FixLoop --> Core
    ErrorCheck -->|Yes| Complete([Complete & Save])
```

---

## Getting Started

### Prerequisites
- **Python**: `>= 3.10`
- **Ollama**: (For offline local execution) installed from [ollama.com](https://ollama.com)

### Quick Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/CodeByPartho/Qwen-Coding-Agent.git
   cd Qwen-Coding-Agent
   ```

2. **Pull model weights**:
   ```bash
   ollama pull qwen2.5-coder:7b
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

---

## License

This project is licensed under the **[MIT License](LICENSE)**.

---

<p align="center">Built by Partho</p>
