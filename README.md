# Ai4Omics

This repository contains the datasets used in the AI4Omics course exercises.
The files are deliberately small and tabular so that they can be loaded with
standard Python tools while students learn to inspect, clean, and analyse
omics data.

## Data

All course data is in [`data/`](data/). The five CSV files are:

| File | Contents |
| --- | --- |
| [`expression.csv`](data/expression.csv) | Example gene-expression measurements |
| [`clinical.csv`](data/clinical.csv) | Sample-level clinical labels and covariates |
| [`methylation.csv`](data/methylation.csv) | Example DNA-methylation beta values |
| [`copy_number.csv`](data/copy_number.csv) | Example copy-number log2 ratios |
| [`mhc_gene_sets.csv`](data/mhc_gene_sets.csv) | The MHC class I and class II genes used in the analyses |

`mhc_gene_sets.csv` contains eight class I genes and thirteen class II genes.
Use the `mhc_class` column to select a gene set rather than maintaining a
second list in a notebook.

## Getting started

Create a Python environment with pandas installed, then load a dataset from
the repository root:

```python
import pandas as pd

expression = pd.read_csv("data/expression.csv")
mhc = pd.read_csv("data/mhc_gene_sets.csv")
class_i = mhc.loc[mhc["mhc_class"] == "I", "gene"]
```

Keep the original files unchanged and save derived tables outside `data/`
(or give them a new, descriptive filename) so that notebooks remain
reproducible for other students.