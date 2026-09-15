# Systemic Risk Spillovers Between European Banks and NBFIs

An empirical analysis of directional systemic-risk spillovers between listed European banks and non-bank financial intermediaries (NBFIs), using daily market data from 2015 to 2025.

This project was developed as part of my Master's studies in Economics at Lund University.

## Research question

Do listed European NBFIs transmit more tail risk to banks than banks transmit to NBFIs, and how do these spillovers vary with macro-financial conditions?

## Approach

The analysis combines a Python data pipeline with R-based multivariate volatility modelling:

- **Data preparation:** Python (`pandas`, `NumPy`) to clean, align and combine daily market data with macro-financial control variables.
- **Volatility modelling:** R (`rugarch`, `rmgarch`) called from Python through `rpy2` to estimate bivariate DCC-GJR-GARCH models with Student-t innovations.
- **Systemic-risk measure:** Directional Delta CoVaR measures constructed from conditional tail-risk estimates.
- **Empirical analysis:** Two-way clustered panel OLS and robustness checks using `linearmodels` and `statsmodels`.

## Main finding

The results indicate that tail-risk spillovers from NBFIs to banks are significantly stronger than spillovers in the opposite direction (p < 0.001), with the asymmetry particularly pronounced during periods of liquidity stress.

## Repository contents

```text
.
├── notebooks/
│   └── systemic_risk_spillovers.ipynb  # Fully rendered analysis notebook
├── requirements.txt                    # Python dependencies
└── README.md
```

## Data availability and reproducibility

The underlying Bloomberg data cannot be included because of licensing restrictions. The notebook is therefore provided as a fully rendered record of the data-processing, modelling and empirical-analysis workflow, including the reported outputs and figures.

To reproduce the analysis, a user with access to the underlying Bloomberg data would need to supply a local `Data.xlsx` file with the required sheets and install the R packages `rugarch` and `rmgarch` in addition to the Python dependencies.

## Technical stack

**Python:** pandas, NumPy, SciPy, statsmodels, arch, linearmodels, matplotlib, rpy2

**R:** rugarch, rmgarch

**Methods:** log returns, stationarity testing, GJR-GARCH, DCC-GARCH, Delta CoVaR, Newey-West inference, panel regression and robustness testing.

## Note

This repository is shared for portfolio and review purposes. It is not investment advice.
