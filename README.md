# Appendix A — Full R Code
### STAT 420 Final Project  
**Author:** Seokhyun (Jason) Lee  
**UIUC NetID:** sl251  
**Project:** Cryptocurrency Market Analysis (2010–2025)

---

## Overview
This repository contains the full, executable R code used to produce all results, figures, and models in my **STAT 420 Final Project**.  
The main PDF submission includes cleaned summaries of methods and results.  
This appendix provides the complete codebase for reproducibility.

The code performs the following tasks:

1. **Data import and cleaning**  
2. **Daily return computation**  
3. **Merging multi-asset time series**  
4. **Exploratory data analysis (EDA)**  
5. **Full regression model fitting**  
6. **Reduced / Interaction / Polynomial / Lagged models**  
7. **10-fold Cross-Validation (cv.glm)**  
8. **Diagnostic tests** (VIF, DW-test, ACF, residual plots)

---

## File Structure
├── cleaning.R
├── returns.R
├── modeling_full.R
├── modeling_reduced.R
├── modeling_interaction.R
├── modeling_polynomial.R
├── modeling_lagged.R
├── cross_validation.R
├── diagnostics.R
└── helper_functions.R


### **Descriptions**

| File | Purpose |
|------|---------|
| `cleaning.R` | Imports raw CSV files, standardizes column names, parses dates |
| `returns.R` | Computes daily returns for each asset and merges data frames |
| `modeling_full.R` | Fits the full return-based regression model |
| `modeling_reduced.R` | Fits the reduced model without SOL_ret or GOLD_ret |
| `modeling_interaction.R` | Adds ETH × SPX interaction term |
| `modeling_polynomial.R` | Fits quadratic SPX_ret model via poly() |
| `modeling_lagged.R` | Builds the lagged Bitcoin return model |
| `cross_validation.R` | Performs 10-fold CV using cv.glm |
| `diagnostics.R` | Residual plots, VIF, QQ plot, DW test, ACF plot |
| `helper_functions.R` | Shared helper functions used across scripts |

---

## How to Run

### **1. Clone this repository**
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### **2. Install required R packages**
```bash
install.packages(c("tidyverse", "lubridate", "corrplot", 
                   "car", "lmtest", "boot", "ggplot2"))
```

### **3. Run the scripts**
You may run each script individually, or source the full pipeline:
```bash
source("cleaning.R")
source("returns.R")
source("modeling_full.R")
source("modeling_reduced.R")
source("modeling_interaction.R")
source("modeling_polynomial.R")
source("modeling_lagged.R")
source("cross_validation.R")
source("diagnostics.R")
```

This will reproduce all:
Model outputs
Cross-validation results
Plots
Diagnostics
