# MATLAB-Based Numerical Simulation of BCR-ABL1 Expression Dynamics and Targeted Therapy Response in Chronic Myeloid Leukemia

[![MATLAB](https://img.shields.io/badge/MATLAB-Numerical%20Modeling-orange?style=flat-square)](MATLAB_Code/CML_Numerical_Project.m)
[![Cancer Modeling](https://img.shields.io/badge/Cancer%20Modeling-CML-red?style=flat-square)](#)
[![Computational Biology](https://img.shields.io/badge/Computational%20Biology-Gene%20Expression-blue?style=flat-square)](#)
[![GEO](https://img.shields.io/badge/GEO-GSE33075-green?style=flat-square)](#)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)](#)

## Project Overview

This project presents a MATLAB-based computational and numerical simulation of **BCR-ABL1 expression dynamics** in **Chronic Myeloid Leukemia (CML)**. The project models the behavior of BCR-ABL1 mRNA and protein/activity levels under three biological conditions: normal cells, untreated CML cells, and treated CML cells.

The biological focus of the project is based on the role of the **BCR-ABL1 gene** in CML, where its abnormal tyrosine kinase activity promotes excessive survival and growth of myeloid cells. The project also incorporates a treatment-response scenario using **tyrosine kinase inhibitor-like inhibition**, inspired by imatinib treatment data from the public GEO dataset **GSE33075**.

## Team Members

- **Shaimaa Mohamed El Haddad**
- **Menatalla Essam**

## Project Aim

The main aim of this project was to model **BCR-ABL1 mRNA and protein/activity dynamics** in:

- Normal cells
- Untreated CML cells
- Treated CML cells

The expected biological behavior was that normal cells would show the lowest BCR-ABL1 activity, untreated CML cells would show the highest activity, and treated CML cells would show reduced activity after therapy.

## Biological Background

Chronic Myeloid Leukemia is strongly associated with the **Philadelphia chromosome**, which creates the **BCR-ABL1 fusion gene**. This fusion gene encodes an abnormal tyrosine kinase that activates pathways involved in uncontrolled cell growth and survival.

Targeted therapies such as imatinib are designed to inhibit BCR-ABL1 kinase activity. In this project, the treatment response is represented computationally by reducing BCR-ABL1-related activity over time.

## Mathematical Model

The model uses two main biological variables:

| Variable | Meaning |
|---|---|
| `M(t)` | BCR-ABL1 mRNA level |
| `P(t)` | BCR-ABL1 protein/activity level |

The model assumes that mRNA dynamics depend on synthesis and decay, while protein/activity dynamics depend on synthesis, decay, and treatment inhibition. The treatment effect was represented using an inhibition term affecting the protein/activity level.

## Numerical Methods

The project applied MATLAB-based numerical simulation approaches:

| Method | Role in the Project |
|---|---|
| Euler’s Method | Step-by-step numerical approximation of the model behavior |
| MATLAB `ode45` | Adaptive ODE solver used to simulate the system over time |

The simulation was performed over time to compare BCR-ABL1 mRNA and protein/activity levels across normal, untreated CML, and treated CML scenarios.

## Transcriptomic Data Analysis

The project also included analysis of the public GEO transcriptomic dataset **GSE33075**. The dataset contains samples from healthy controls, CML patients before treatment, and CML patients after one month of imatinib treatment.

Expression values were imported into MATLAB, grouped by condition, and compared to identify genes that decreased after treatment. This supported the treatment-response scenario represented in the numerical model.

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

## How to Run

1. Open MATLAB.
2. Open the main script:

```text
MATLAB_Code/CML_Numerical_Project.m
```

3. Optional: place the processed gene expression dataset file in the same folder as the MATLAB script.
4. Press **Run**.
5. The script will generate simulation outputs and figures.

If no dataset is provided, the script can still run using a small demo expression dataset.

## Expected Outputs

| Output type | Examples |
|---|---|
| Numerical simulation | BCR-ABL1 mRNA and protein/activity curves |
| Treatment comparison | Normal vs untreated CML vs treated CML dynamics |
| Solver comparison | Euler’s Method and ode45 simulation behavior |
| Gene expression analysis | Downregulated genes after treatment |
| Scientific visualization | Line plots, treatment-response plots, expression plots |

## Key Results

The simulation showed that:

- Normal cells had low BCR-ABL1 mRNA and protein/activity levels.
- Untreated CML cells showed the highest BCR-ABL1 protein/activity levels.
- Treated CML cells showed reduced protein/activity due to the treatment inhibition term.
- Increasing treatment strength led to progressively lower BCR-ABL1 activity.
- GEO transcriptomic analysis identified downregulated genes after treatment, supporting the treatment-response scenario.

## Tools and Skills Used

- MATLAB
- Numerical Analysis
- Euler’s Method
- `ode45` ODE Solver
- Gene Expression Analysis
- GEO Dataset Analysis
- Mathematical Modeling
- Biomedical Simulation
- Chronic Myeloid Leukemia Biology
- BCR-ABL1 Expression Dynamics
- Treatment Response Modeling
- Scientific Data Visualization

## Conclusion

This project demonstrated how numerical methods and computational biology can be integrated to study cancer-related gene expression behavior. By combining mathematical modeling, MATLAB simulation, and transcriptomic data analysis, the project provided a simplified computational representation of BCR-ABL1 dynamics in CML and showed how targeted therapy may reduce leukemic activity over time.

## Short Repository Description

MATLAB-based numerical simulation of BCR-ABL1 mRNA and protein/activity dynamics in Chronic Myeloid Leukemia, integrating Euler’s Method, ode45, and GEO gene expression analysis.

## Project Contributors

- **Shaimaa Mohamed El Haddad** — Biomedical Science Undergraduate, Computational Biology & Genomics Concentration
- **Menatalla Essam** — Project team member
