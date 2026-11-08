# Cellxgene Census

"Query CZ CELLxGENE Census (61M+ cells). Filter by cell type/tissue/disease, retrieve expression data, integrate with scanpy/PyTorch, for population-scale single-cell analysis."

## Overview

This repository preserves the AITMPL skill instructions and the published reference resources at their original relative paths.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-cellxgene-census-skill.git ~/.claude/skills/cellxgene-census
```

On Windows, use `%USERPROFILE%\.claude\skills\cellxgene-census` as the destination.

## Usage

Claude Code can load the skill when a request matches its description. Invoke directly with `/cellxgene-census` when needed.

## Repository structure

```text
cellxgene-census/
├── SKILL.md
├── references/census_schema.md
├── references/common_patterns.md
├── README.md
└── LICENSE
```

## Runtime requirements

- The skill instructions require no build step.
- Install domain-specific libraries only when the skill's task requires them.
- Review scripts and their dependencies before execution.
