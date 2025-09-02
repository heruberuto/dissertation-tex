# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a PhD dissertation repository focused on "NLP Methods for Automated Fact-Checking" written in LaTeX using the CTU thesis template. The dissertation covers automated fact-checking through Natural Language Processing methods, specifically for West Slavic languages (Czech, Slovak, Polish) and English.

## Building and Compilation

### Main Document
- **Primary file**: `dissertation.tex` (main LaTeX document)
- **Build command**: Use `arara` build system with the following commands embedded in the document:
  ```bash
  arara dissertation.tex
  ```
  This will automatically run:
  - `pdflatex` with synctex enabled
  - `makeindex` with ctuthesis style
  - `bibtex` for bibliography

### Alternative Manual Build
If arara is not available, use standard LaTeX compilation:
```bash
pdflatex dissertation.tex
makeindex -s ctuthesis.ist dissertation.idx
bibtex dissertation
pdflatex dissertation.tex
pdflatex dissertation.tex
```

### Output
- Main output: `dissertation.pdf`
- Auxiliary files are stored in `aux/` directory

## Document Structure

### Main Components
- **Main document**: `dissertation.tex` - Contains document setup, packages, and includes all chapters
- **Chapters**: Located in `chapters/` directory:
  - `1_introduction.tex` - Introduction and motivation
  - `2_sota.tex` - State of the art review
  - `3_current_contributions.tex` - Current research contributions
  - `4_dissertation_plan.tex` - Future dissertation plan
  - `9_conclusion.tex` - Conclusions
- **Bibliography**: `dissertation.bib` - BibTeX references
- **Figures**: `fig/` directory contains all dissertation figures (PDF, PNG formats)

### CTU Thesis Template
- **Class file**: `ctuthesis.cls` - Custom CTU thesis document class
- **Core components**:
  - `ctuth-core.tex` - Core functionality
  - `ctuth-pkg.tex` - Package definitions
  - `ctuth-templates.tex` - Template definitions
  - `ctuth-names.tex` - Name definitions
- **Style file**: `ctuthesis.ist` - Index style for makeindex

### Document Configuration
The document is configured in `dissertation.tex` with:
- Language: English (with Czech as secondary)
- Department: Department of Computer Science, Faculty of Electrical Engineering, CTU
- Author: Ing. Herbert Ullrich
- Supervisor: Ing. Jan Drchal, Ph.D.
- Field: Informatics - Natural Language Processing
- Keywords: Fact-checking, Natural Language Inference, Claim Generation, Transformers, LLMs

### Custom Macros and Commands
The document defines numerous custom commands for:
- Dataset names (e.g., `\FEVER`, `\FCZ`, `\CTK`)
- Model names (e.g., `\BERT`, `\RoBERTa`, `\MBERT`)
- Fact-checking labels (`\SUP`, `\REF`, `\NEI`)
- Custom formatting and cross-references

## Research Focus

The dissertation focuses on:
1. **Automated fact-checking** using NLP methods
2. **Dataset collection** for West Slavic languages
3. **Claim generation** as a summarization task
4. **Transformer models** and **Large Language Models (LLMs)**
5. **Natural Language Inference (NLI)** for fact verification
6. **Information Retrieval** for evidence gathering

## File Management

- **Main working files**: Keep in root directory
- **Auxiliary files**: LaTeX compilation artifacts go to `aux/`
- **Figures**: Store in `fig/` with appropriate subdirectories
- **Inspirations**: `inspirations/` contains reference materials and previous work samples

## Important Notes

- The document uses `oneside` layout for printing
- Bibliography style: `apalike`
- Index style: Custom CTU thesis style (`ctuthesis.ist`)
- The document includes line numbering for review purposes (`lineno` package)
- Uses `algorithm2e` package for algorithm formatting
- Extensive use of custom LaTeX macros for consistency