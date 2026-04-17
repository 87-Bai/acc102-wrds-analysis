# Reflection – ACC102 Track 2 (WRDS Compustat Analysis)

## My Intellectual Contribution

I independently completed this project from start to finish. My specific contributions include:

- Designing the SQL query to extract annual financial data from WRDS Compustat, including correctly joining `comp.funda` and `comp.security` tables and handling the column name issue (`tic` instead of `ticker`).
- Calculating all financial ratios (ROE, ROA, debt-to-equity, operating margin) based on formulas learned in class.
- Selecting Apple and Microsoft as comparison cases to illustrate the trade-off between profitability and leverage.
- Creating the trend plots and summary statistics to support my investment conclusions.
- Writing the complete README and this reflection, including honest AI disclosure.
- Debugging the notebook and ensuring it runs without errors.

## AI Use Disclosure (in accordance with university academic integrity policy)

**ChatGPT-4o (OpenAI)** – Accessed 17 April 2026  
- Role: Helped debug the SQL error where `b.ticker` should be `b.tic`; provided the initial structure for matplotlib plots; suggested the `groupby().agg()` summary table.  
- All AI-generated code was reviewed, understood, and modified by me. For example, I adjusted the ratio calculations to match Compustat field definitions.

**GitHub Copilot** – Accessed 17 April 2026  
- Role: Autocompleted repetitive pandas operations such as `.head()` and column selection.

No AI tool was used to write the analytical conclusions or the investment recommendations – those are entirely my own.

## Code I Can Explain

I fully understand every line of code in my notebook, including:

- `wrds.Connection()`: Establishes an SSH tunnel to the WRDS server using my `.pgpass` credentials.
- `db.raw_sql(query, date_cols=['datadate'])`: Executes the SQL query and automatically parses the `datadate` column as datetime.
- `df['roe'] = df['ni'] / df['seq']`: Calculates return on equity (net income / shareholders' equity).
- `df.groupby('ticker').agg(...)`: Computes mean and standard deviation for each company.

## Limitations of the Project

- The analysis is limited to only two US large-cap technology companies. Results may not generalise to other sectors or smaller firms.
- WRDS Compustat annual data is backward-looking; no forward-looking estimates are included.
- The time window (2019–2024) is relatively short and may be influenced by the COVID-19 pandemic distortion.
- No adjustments were made for stock buybacks or special dividends, which can affect ROE.

## Future Improvements

- Expand the analysis to include 10–20 companies across different industries for benchmarking.
- Add DuPont decomposition to understand the drivers of ROE (profit margin, asset turnover, leverage).
- Incorporate quarterly data from `comp.fundq` for higher-frequency trend detection.
- Automate the generation of a PDF report using Python.

## Professional Practice

I have followed the course guidelines on ethical AI use by providing full disclosure of tools and their specific roles. My GitHub repository is public and well-organised, and the notebook is reproducible by anyone with WRDS access. This project will be added to my professional portfolio, and I am prepared to explain any part of the code in an interview.

---
**Student Name**: [Yanni.Qian24]  
**Date**: 17 April 2026
