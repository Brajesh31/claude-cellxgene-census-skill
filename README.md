# claude-cellxgene-census-skill

A Claude Code skill for querying and analyzing large-scale single-cell genomics data with CELLxGENE Census.

## Overview

CELLxGENE Census provides access to standardized single-cell datasets with rich metadata. This skill helps formulate Census queries, filter cells and genes, retrieve expression data, and connect the results to scientific Python and machine-learning workflows.

It is designed for population-scale exploration where datasets may contain millions of cells and require careful filtering and memory management.

## Main Capabilities

- Explore available Census datasets and metadata.
- Filter observations by cell type, tissue, disease, donor, and other supported fields.
- Select genes and retrieve expression values.
- Work with sparse expression matrices.
- Retrieve embeddings and dataset-level information where available.
- Integrate retrieved data with Scanpy and related tools.
- Prepare data for PyTorch-based machine-learning workflows.
- Aggregate and compare results across datasets.

## Installation

Install the Census package in the analysis environment:

```bash
python -m pip install cellxgene-census
```

Install the skill:

```bash
git clone https://github.com/Brajesh31/claude-cellxgene-census-skill.git ~/.claude/skills/cellxgene-census
```

## Usage

Invoke the skill for Census data tasks:

```text
/cellxgene-census
```

State the biological question, species, tissue, cell type, disease context, genes of interest, and expected output. Include the required Census version or snapshot when reproducibility matters.

## Typical Workflow

1. Define the scientific question and relevant population.
2. Inspect available dataset and observation metadata.
3. Build filters using valid Census fields.
4. Retrieve only the required observations and variables.
5. Preserve sparse representations where practical.
6. Convert to AnnData or another analysis format when appropriate.
7. Perform downstream analysis with clear filtering and normalization choices.
8. Record the Census version, query filters, and analysis parameters.

## Example Analysis Outline

```python
import cellxgene_census

with cellxgene_census.open_soma() as census:
    datasets = census["census_info"]["datasets"]
    print(datasets)

    # Build a query using metadata fields available
    # in the selected Census release.
```

Query APIs and metadata schemas can vary by release. Use the schema reference included in this repository before writing a complete query.

## Reference Guide

| File | Focus |
|---|---|
| `references/census_schema.md` | Census data organization and schema |
| `references/common_patterns.md` | Reusable query and analysis patterns |

## Data Quality and Reproducibility

- Record the Census release or snapshot.
- Validate metadata field names before filtering.
- Check the number of cells returned by each filter.
- Avoid loading more expression data than the analysis requires.
- Preserve observation and gene identifiers.
- Document normalization and transformation steps.
- Distinguish missing measurements from zero expression.
- Validate batch and donor composition before comparing groups.

## Repository Contents

- `SKILL.md`: Main skill instructions.
- `references/census_schema.md`: Schema and metadata guidance.
- `references/common_patterns.md`: Query and analysis examples.
- `README.md`: Installation and workflow overview.

## Responsible Interpretation

Large-scale cell counts do not remove sampling bias or dataset heterogeneity. Interpret comparisons in light of donor composition, study design, tissue handling, and metadata quality. Treat associations as evidence for further investigation, not proof of causality.
