# LIC Investment Analysis (1994–2024)

A multi-sheet Excel-based quantitative analysis of Life Insurance Corporation of India's investment portfolio across 30 years — combining descriptive statistics, log-linear regression modelling, exponential forecasting, and sector composition analysis.

---

## Project Overview

LIC is India's largest institutional investor, managing a corpus that grew from ₹44,162 Crore in 1994 to ₹42.81 Lakh Crore in 2024 — nearly 96x growth. This project goes beyond basic data summarisation: it applies a log-linear regression model to the 30-year time series to capture the exponential growth trajectory, quantify model fit (R²), identify structural growth shifts, and forecast future portfolio values.

---

## Key Findings

| Metric | Value |

| Total Portfolio Size (2024) | ₹42.81 Lakh Crore |
| Overall Growth (1994–2024) | ~9,593.8% (~96x) |
| CAGR (1994–2024) | 16.47% p.a. |
| Avg. Annual YoY Growth | 16.61% |
| Peak Growth Year | 2004 — 29.8% |
| Regression Model R² | 0.9816 |
| Public Sector Share (2024) | 81.1% |
| Private Sector Share (2024) | 18.9% |
| Loans Portfolio Change | −22.7% (as % of total) |

**Structural shift identified:** Early-period growth rates of ~16–21% p.a. have moderated to ~9–11% in recent years, indicating LIC is transitioning from a high-growth phase to a more mature, stable expansion phase — a finding the regression residuals make visible.

---

### Data Source
- **Primary:** Life Insurance Corporation of India Annual Reports
- **Secondary:** RBI Handbook of Statistics on Indian Economy (HSIE) — Table 70

---


### Log-Linear Regression Model

To model LIC's exponential growth pattern, a log-linear regression was applied:

ln(Investment) = a + b × (Year Index)
→ Investment = EXP(a + b × Year Index)

- **Year Index** runs from 1 (1994) to 31 (2024)
- **Slope (b)** and **Intercept (a)** computed using Excel's `SLOPE()` and `INTERCEPT()` functions
- **Model fit: R² = 0.9816** — the model explains ~98.2% of variance in log-investment, confirming a strong exponential growth pattern
- **% Error** column in Cleaned Data tracks residuals to surface deviations from the model trend

### Forecasting
The Analysis sheet includes a dynamic forecast tool: enter any future year, and the model returns an estimated portfolio size using the fitted regression equation — `=EXP(a + b × (input_year − 1993))`.

### Statistical Analysis
Computed across Total Investments, Public Sector, Private Sector, Stock Exchange, and Loans:
- Mean, Median, Standard Deviation, Minimum, Maximum
- Range and Coefficient of Variation (%) for dispersion analysis

---

## Skills Demonstrated

- Time-series financial analysis over a 30-year horizon
- Applied mathematics: log-linear regression, exponential modelling, R² interpretation
- Excel modelling: structured Tables, cross-sheet formula references, `SLOPE()`, `INTERCEPT()`, `RSQ()`, `LN()`, `EXP()`
- Descriptive statistics: mean, median, std dev, coefficient of variation
- Residual analysis and structural break identification
- Dynamic forecasting tool built entirely within Excel
- Data storytelling through a structured Insights layer

---

## Insights

- LIC's portfolio follows a near-perfect exponential growth curve (R² = 0.9816), making it well-suited to log-linear regression
- A structural growth deceleration is observable post-2011, with YoY rates dropping from ~20% to ~9–11% — the model's residuals make this shift explicit
- The public sector continues to dominate (~81%) but private sector allocation has nearly tripled since 1994, signalling gradual diversification
- The loans portfolio has systematically declined as a share of total investments, consistent with LIC's shift toward market-linked instruments
- The regression-based forecast should be treated as a long-run trend estimate; near-term forecasts may deviate due to the moderating growth rate observed in recent years

---

## Potential Extensions

- Fit a piecewise regression to model the pre-2011 (high growth) and post-2011 (moderate growth) phases separately
- Overlay Sensex / Nifty performance to test correlation between equity market returns and LIC's private sector allocation growth
- Add inflation-adjusted (real terms) portfolio values using CPI deflator data from RBI
- Build a Monte Carlo simulation to generate forecast confidence intervals around the regression estimate
