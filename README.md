# CML Dynamics and Treatment Scenarios in MATLAB

![MATLAB](https://img.shields.io/badge/MATLAB-Numerical%20Modeling-orange?style=flat-square)
![Methods](https://img.shields.io/badge/Methods-Euler%20%7C%20RK4%20%7C%20ode45-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Academic%20project-blue?style=flat-square)

A team computational biology project combining **simplified CML population dynamics**, numerical solver comparisons, and an exploratory gene-expression analysis workflow.

**Start here:** [MATLAB script](MATLAB_Code/CML_Numerical_Project.m) · [Project summary](docs/project_summary.md) · [Dataset notes](Dataset/README.md) · [Run instructions](#how-to-run)

> **Implementation status:** The repository contains a MATLAB script with synthetic expression-data fallback. The script was reviewed for documentation accuracy but was not executed in this review. Generated figures and result tables are not included. Model scenarios are educational, not validated clinical predictions.

## Purpose and Portfolio Value

The project connects biological questions with numerical programming: importing tabular data, preprocessing expression values, comparing groups, solving differential equations, and exporting figures and tables.

The original project framing focused on BCR-ABL1 and treatment response in chronic myeloid leukemia. The **current code models leukemic cells, healthy cells, and an mRNA signal**; it does not explicitly model a BCR-ABL1 protein variable.

## Team

- **Shaimaa Mohamed El Haddad**
- **Menatalla Essam**

This is a team project; individual component ownership is not separately documented.

## Implemented Workflow

| Component | Current implementation |
| --- | --- |
| Expression input | Reads a supported CSV/XLSX filename from the MATLAB current folder |
| Synthetic fallback | Generates 120 fictional genes across four Normal and four CML samples with random seed 7 |
| Preprocessing | Fills missing values by gene mean, conditionally log-transforms values, removes zero-variance genes |
| Group comparison | Defaults to CML vs Normal; Welch's t-tests and Benjamini–Hochberg adjustment |
| Visualization | Expression distributions, volcano plot, top-gene bar plot, heatmap |
| ODE simulation | Leukemic population, healthy population, and mRNA signal |
| Solver comparison | Explicit Euler, fourth-order Runge–Kutta, and MATLAB `ode45` |
| Treatment scenarios | Compares `u = 0, 0.15, 0.35, 0.55` |
| Export | PNG figures, XLSX result tables, and a text summary under `Project_Output/` |

## Mathematical Model

The three state variables are:

| Code variable | Meaning |
| --- | --- |
| `x` | Leukemic cell population |
| `y` | Healthy cell population |
| `m` | mRNA signal linked to leukemic cells |

The implemented equations are:

```text
dx/dt = rL*x*(1 - x/KL) - dL*x - u*x
dy/dt = rH*y*(1 - y/KH) - alpha*x*y
dm/dt = beta*x - gamma*m
```

The treatment parameter `u` adds a loss term to the leukemic population. Initial conditions are `[15; 85; 8]`, the simulation interval is 0–60, and Euler/RK4 use a step size of 0.5. The fixed-step solvers clamp negative state values to zero; `ode45` is called without that explicit clamp.

Parameters are illustrative. The code does not fit them to patient data or infer a clinical dose.

## How to Run

1. Use MATLAB with the **Statistics and Machine Learning Toolbox** for functions including `ttest2` and `boxplot`.
2. Open [CML_Numerical_Project.m](MATLAB_Code/CML_Numerical_Project.m).
3. Set MATLAB's current folder to `MATLAB_Code/`.
4. For a synthetic demonstration, leave the input files absent and run:

```matlab
CML_Numerical_Project
```

5. Inspect the console to confirm whether synthetic data or a real file was used. Outputs are written to `Project_Output/` under the current folder.

No external expression dataset is required for the synthetic fallback. Runtime compatibility and numerical results have not been independently verified here.

### Using a Real Expression Table

The script searches for:

```text
GSE33075_expression.csv
GSE33075_expression.xlsx
gene_expression.csv
gene_expression.xlsx
expression_data.csv
expression_data.xlsx
```

Provide a gene identifier column and numeric sample columns. Recognized gene-column names include `Gene`, `GeneSymbol`, `Symbol`, `ID`, and `ProbeID`; otherwise, the first column is used.

Review `groupA`, `groupB`, and sample-name parsing before interpreting results. **The code can split samples automatically when group labels are unclear**, so check the displayed metadata against the true experimental design.

GSE33075 is referenced in the original project context. This repository does not contain its expression matrix, a verified sample mapping, or reproduced dataset-specific findings. The default comparison is **CML vs Normal**, not a before/after-treatment comparison.

## Expected Outputs and Results Status

The script is configured to export:

- Eight PNG figures covering expression QC, differential expression, solver comparison, and treatment scenarios.
- `Differential_Expression_Results.xlsx`.
- `Treatment_Scenario_Summary.xlsx`.
- `Project_Summary.txt`.

These are **expected output files**, not artifacts verified in the repository. Synthetic expression differences are constructed for demonstration and do not establish findings about GSE33075.

The treatment scenarios illustrate the consequences of changing the model's assumed treatment term. A validated treatment-response claim would require suitable data, parameter estimation, and independent checks.

## Repository Navigation

| Path | Purpose |
| --- | --- |
| [MATLAB_Code/](MATLAB_Code/) | Main executable script and local helper functions |
| [Dataset/README.md](Dataset/README.md) | Dataset context |
| [Figures/README.md](Figures/README.md) | Figure documentation |
| [Results/README.md](Results/README.md) | Results documentation |
| [docs/project_summary.md](docs/project_summary.md) | Short project overview |

## Next Steps

- [ ] Record MATLAB and toolbox versions from a successful run.
- [ ] Add small, reviewed output figures with explicit synthetic/real-data labels.
- [ ] Replace automatic group inference with validated metadata in a separately reviewed code change.
- [ ] Add numerical convergence checks and automated tests.
- [ ] Document real-data provenance and reproduce any dataset-specific findings.

## Skills Demonstrated in the Code

MATLAB · data preprocessing · numerical methods · ODE modeling · statistical comparisons · scientific visualization · computational biology

[Portfolio](https://github.com/shaimaamo1) · [LinkedIn](https://www.linkedin.com/in/shaimaa-muhammad-9a7a6a2b0/)
