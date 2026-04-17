# Financial Analysis with WRDS Compustat – ACC102 Track 2

## 1. Problem & User
**Problem**: Retail investors need to compare financial health and profitability across companies, but manually extracting WRDS data is challenging.  
**User**: Finance students or analysts with basic programming skills who want to use SQL to pull data from WRDS and automatically compute key financial ratios.

## 2. Data Source
- **Database**: WRDS Compustat (annual fundamentals)
- **Access Date**: 17 April 2026
- **Key Tables**: `comp.funda` (financial data), `comp.security` (ticker mapping)
- **Companies**: AAPL (Apple), MSFT (Microsoft)
- **Years**: 2019–2024

## 3. Methods & Steps
1. Establish connection using the `wrds` library
2. Write SQL queries to retrieve current assets, liabilities, equity, revenue, net income, etc.
3. Compute ratios: ROE, ROA, debt-to-equity, operating margin
4. Plot trend comparison charts
5. Generate summary statistics and investment insights

## 4. Key Findings
- AAPL has a higher average ROE than MSFT, but with greater volatility.
- AAPL's debt-to-equity ratio is significantly higher, indicating financial leverage.
- Both companies have similar ROA levels, suggesting comparable core profitability.

## 5. Demo Video

📹 Click to watch demo video: https://b23.tv/7Hpcatk

## 6. Limitations & Next Steps

· Only two large US tech companies were analysed
· Quarterly data and industry adjustments not considered
· Future work: expand to more companies, add DuPont analysis

## 7. How to Run
```bash
pip install wrds pandas matplotlib seaborn
jupyter notebook financial_analysis_wrds.ipynb
