# Dataset

This folder documents the expression input format; no expression dataset is committed here. The current script searches the MATLAB **current folder**, not this `Dataset/` folder. Place input beside the script and set that folder as current before running.

The MATLAB script can read CSV or Excel files using one of the following default names:

```text
GSE33075_expression.csv
GSE33075_expression.xlsx
gene_expression.csv
gene_expression.xlsx
expression_data.csv
expression_data.xlsx
```

If no dataset is available, the script automatically generates a small demo dataset for a synthetic demonstration. This fallback does not establish that a run will succeed in every MATLAB environment.

## Expected Format

The expression matrix should contain:

- one column for gene names or probe IDs,
- multiple sample columns containing expression values.

Example:

```text
Gene,Normal_1,Normal_2,CML_1,CML_2
ABL1,7.8,7.5,9.2,9.5
BCR,6.1,6.3,8.4,8.6
```

The default analysis compares `CML` with `Normal`. Review inferred sample groups before interpreting results; the script can assign groups by column position if labels are unclear. Example values above are illustrative.

[Full setup, model scope, and limitations](../README.md)
