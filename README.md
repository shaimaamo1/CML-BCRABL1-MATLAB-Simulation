# MATLAB-Based Numerical Simulation of BCR-ABL1 Expression Dynamics and Targeted Therapy Response in CML

[![MATLAB](https://img.shields.io/badge/MATLAB-Numerical%20Modeling-orange?style=flat-square)](MATLAB_Code/CML_Numerical_Project.m)
[![Cancer Modeling](https://img.shields.io/badge/Cancer%20Modeling-CML-red?style=flat-square)](#)
[![Computational Biology](https://img.shields.io/badge/Computational%20Biology-Gene%20Expression-blue?style=flat-square)](#)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)](#)

## Project Overview

This project presents a MATLAB-based computational biology workflow for simulating **BCR-ABL1-related expression dynamics** and targeted therapy response in **Chronic Myeloid Leukemia (CML)**.

The project combines numerical modeling, ordinary differential equations, Euler’s Method, RK4 Method, MATLAB `ode45`, gene expression analysis, differential expression visualization, and treatment-response simulation.

The biological motivation is based on the role of **BCR-ABL1**, the oncogenic fusion driver of CML. BCR-ABL1 produces abnormal tyrosine kinase activity that supports leukemic cell survival and proliferation. In this simplified model, targeted therapy is represented as a treatment effect that reduces leukemic cell dynamics over time.

---

## Aim of the Project

The aim of this project was to develop a reproducible MATLAB workflow that can:

- simulate leukemic cell behavior under treatment,
- compare healthy and CML-related expression behavior,
- apply numerical methods to a biomedical ODE system,
- analyze gene expression differences between biological groups,
- generate clear scientific figures for interpretation.

---

## Biological Background

Chronic Myeloid Leukemia is strongly associated with the **Philadelphia chromosome**, which creates the **BCR-ABL1 fusion gene**. This fusion gene encodes an abnormal tyrosine kinase that activates pathways involved in uncontrolled cell growth and survival.

Targeted therapies such as imatinib are designed to inhibit BCR-ABL1 kinase activity. In this project, the treatment response is represented computationally by reducing leukemic cell survival and observing the downstream effect on a BCR-ABL1-related mRNA signal.

---

## Mathematical Model

The model uses three state variables:

| Variable | Meaning |
|---|---|
| `x(t)` | Leukemic cell population |
| `y(t)` | Healthy cell population |
| `m(t)` | BCR-ABL1-related mRNA expression signal |

The system models leukemic cell growth, leukemic cell death, healthy cell growth, competition between leukemic and healthy cells, mRNA production related to leukemic burden, mRNA degradation, and treatment-induced reduction in leukemic cell dynamics.

The treatment parameter is represented by `u`, where higher values indicate stronger treatment effect.

---

## Numerical Methods

| Method | Role in the Project |
|---|---|
| Euler’s Method | Basic step-by-step numerical approximation |
| RK4 Method | More accurate fixed-step ODE simulation |
| MATLAB `ode45` | Built-in adaptive solver used as a reference |

The project compares these methods to show how different numerical approaches approximate the same biological system.

---

## Gene Expression Analysis Component

The MATLAB script can load a gene expression matrix from CSV or Excel format. If no dataset is found, the script creates a small demo expression dataset automatically so that the complete workflow can still run.

The analysis includes data loading, metadata creation, missing value handling, optional log2 transformation, differential expression analysis, Benjamini-Hochberg adjusted p-values, volcano plot generation, top-gene bar plot, and heatmap visualization.

Default accepted dataset file names:

```text
GSE33075_expression.csv
GSE33075_expression.xlsx
gene_expression.csv
gene_expression.xlsx
expression_data.csv
expression_data.xlsx
```

---

## Repository Structure

```text
CML-BCRABL1-MATLAB-Simulation/
├── README.md
├── MATLAB_Code/
│   └── CML_Numerical_Project.m
├── Dataset/
│   └── README.md
├── Figures/
│   └── README.md
├── Results/
│   └── README.md
└── docs/
    └── project_summary.md
```

---

## How to Run

1. Open MATLAB.
2. Open the script:

```text
MATLAB_Code/CML_Numerical_Project.m
```

3. Optional: place the expression dataset file in the same folder as the MATLAB script.
4. Press **Run**.
5. The script will create an output folder called:

```text
Project_Output/
```

If no dataset is provided, the script will generate a demo dataset automatically.

---

## Generated Outputs

| Output File | Description |
|---|---|
| `Differential_Expression_Results.xlsx` | Gene-level differential expression results |
| `Treatment_Scenario_Summary.xlsx` | Final model values under different treatment strengths |
| `Project_Summary.txt` | Short numerical and biological summary |

---

## Generated Figures

| Figure | Description |
|---|---|
| `Figure_1_sample_expression_boxplot.png` | Expression distribution across samples |
| `Figure_2_sample_mean_expression.png` | Mean expression per sample |
| `Figure_3_volcano_plot.png` | Differential expression volcano plot |
| `Figure_4_top_DE_genes_barplot.png` | Top differentially expressed genes |
| `Figure_5_top_genes_heatmap.png` | Heatmap of top genes |
| `Figure_6_CML_dynamics_RK4.png` | CML dynamics using RK4 |
| `Figure_7_numerical_methods_comparison.png` | Euler, RK4, and ode45 comparison |
| `Figure_8_treatment_scenarios.png` | Treatment-strength comparison |

---

## Key Results

The simulation demonstrates that untreated CML-like conditions show higher leukemic activity, treatment reduces leukemic cell burden in the numerical model, stronger treatment values produce lower final leukemic cell levels, BCR-ABL1-related mRNA signal decreases indirectly as leukemic burden decreases, and differential expression analysis can identify genes altered between disease and reference conditions.

---

## Skills Demonstrated

- MATLAB programming
- Numerical analysis
- Euler’s Method
- RK4 Method
- MATLAB `ode45`
- ODE-based biomedical modeling
- Differential expression analysis
- Benjamini-Hochberg correction
- Scientific visualization
- Computational cancer biology
- Reproducible project documentation

---

## Professional Summary

This project demonstrates how numerical analysis and computational biology can be combined to model cancer-related molecular dynamics and targeted therapy response. By integrating ODE simulation, gene expression analysis, and MATLAB-based visualization, the project provides a reproducible example of biomedical modeling applied to BCR-ABL1-driven Chronic Myeloid Leukemia.

---

## Author

**Shaimaa Mohamed El Haddad**  
Biomedical Science Undergraduate  
Computational Biology & Genomics Concentration
