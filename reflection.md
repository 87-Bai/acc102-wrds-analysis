# Reflection – ACC102 Track 2 (WRDS Compustat Analysis)

## Analytical Problem and Intended User

The goal of this project is to compare the financial performance of two major US technology companies, Apple (AAPL) and Microsoft (MSFT), using WRDS Compustat annual data. The intended user is a finance student or junior analyst who has basic Python knowledge and access to WRDS, and who wants to quickly compute and visualise key profitability and leverage ratios. The project solves the problem of manually extracting data from Compustat and performing repetitive ratio calculations.

## Dataset and Justification

Data were obtained from the WRDS Compustat database (accessed 17 April 2026). Two tables were used: `comp.funda` for annual fundamentals and `comp.security` to map GVKEY to ticker symbols. The dataset includes fiscal years 2019–2024 for AAPL and MSFT. Key fields selected: current assets (`act`), total liabilities (`lt`), shareholders’ equity (`seq`), revenue (`sale`), net income (`ni`), and operating income (`oibdp`). This dataset is appropriate because Compustat is the industry standard for corporate financial analysis, and the time window captures recent post‑COVID performance.

## Methods and Python Workflow

The workflow consists of five main steps:

1. **Connection and SQL query**: Used the `wrds` library to establish a connection and executed a SQL query that joins `funda` and `security`, filtering by ticker (`tic`) and year.
2. **Ratio calculation**: Computed ROE (net income / equity), ROA (net income / total assets), debt‑to‑equity (total liabilities / equity), and operating margin (operating income / revenue).
3. **Data exploration**: Printed column names and inspected the resulting DataFrame.
4. **Visualisation**: Plotted ROE and debt‑to‑equity trends over time for both companies using `matplotlib`.
5. **Summary statistics**: Calculated mean and standard deviation of each ratio per company using `groupby().agg()`.

All code is contained in `financial_analysis_wrds.ipynb`. The notebook runs from top to bottom without errors and uses relative logic (no hard‑coded file paths).

## Key Findings and Interpretation

- **Profitability**: AAPL’s average ROE is substantially higher than MSFT’s (e.g., 150% vs 40% in recent years), but its ROE is also more volatile (standard deviation ~0.35 vs 0.10). This suggests AAPL generates higher returns for shareholders at the cost of greater earnings fluctuations.
- **Leverage**: AAPL’s debt‑to‑equity ratio is consistently above 3.5, while MSFT’s remains below 0.8. The high leverage explains part of AAPL’s ROE premium.
- **Core earnings**: Both companies show similar ROA (around 20‑25%), indicating that their underlying operational efficiency is comparable.

**Investment implication**: Risk‑tolerant investors may prefer AAPL for higher potential returns, whereas risk‑averse users might choose MSFT for stability.

## Limitations

- The analysis covers only two large‑cap US tech firms; results may not generalise to other sectors or smaller companies.
- Only annual data are used, which smooths out seasonal or quarterly shocks.
- The time window (2019–2024) includes the COVID‑19 distortion, which may bias ratios.
- WRDS access requires institutional subscription, limiting reproducibility for non‑academic users.

## Future Improvements

- Expand the analysis to 20‑30 companies across different industries to create a benchmark.
- Apply DuPont decomposition to separate ROE into profit margin, asset turnover, and leverage components.
- Incorporate quarterly data (`comp.fundq`) for more granular trend detection.
- Automate report generation as a PDF using `fpdf` or `reportlab`.

## AI Disclosure (in accordance with University Academic Integrity Policy)

**ChatGPT‑4o (OpenAI)** – accessed 17 April 2026  
- Used to: help debug the SQL column name error (`b.ticker` → `b.tic`), provide the initial structure for `matplotlib` plots, and suggest the `groupby().agg()` summary table.  
- All AI‑generated code was reviewed, understood, and modified by me. For instance, I corrected the ratio formulas to match Compustat field definitions and adjusted plot labels for clarity.

**GitHub Copilot** – accessed 17 April 2026  
- Used to: autocomplete repetitive pandas operations (e.g., `.head()`, `.dropna()`).  
- No core logic was written by Copilot; it only accelerated typing.

I confirm that I understand every line of code in my notebook and can explain the purpose of each step. The analytical conclusions and investment recommendations are entirely my own work.

---
**Student Name**: [Yanni.Qian24]  
**Date**: 17 April 2026
