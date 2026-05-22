# Dataset

This folder is intended for the expression dataset used in the MATLAB analysis.

The MATLAB script can read CSV or Excel files using one of the following default names:

```text
GSE33075_expression.csv
GSE33075_expression.xlsx
gene_expression.csv
gene_expression.xlsx
expression_data.csv
expression_data.xlsx
```

If no dataset is available, the script automatically generates a small demo dataset so the workflow can still run without errors.

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
