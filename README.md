# Value-at-Risk (VaR) Modelling and Backtesting

## Project Overview
This project evaluates market risk for a hypothetical ₹10,000,000 equity portfolio comprising seven Indian paint-sector stocks. It compares three Value-at-Risk (VaR) methodologies—Parametric VaR, Historical Simulation, and Monte Carlo Simulation—and evaluates their performance through backtesting and the Basel traffic-light framework.

## Objectives
- Estimate one-day VaR at 95% and 99% confidence levels.
- Compare risk estimates across three VaR methodologies.
- Evaluate model performance using actual versus expected VaR breaches.
- Apply the Basel traffic-light test to assess market-risk outcomes.
- Identify model limitations and opportunities for improvement.

## Portfolio and Data
- **Sector:** Indian paint industry
- **Assets:** Asian Paints, Berger Paints, Indigo Paints, Kansai Nerolac, Shalimar Paints, Akzo Nobel India, and Sirca Paints
- **Sample period:** 1 April 2021 – 1 April 2026
- **Observations:** 1,240 daily closing prices and 1,239 daily returns
- **Hypothetical portfolio value:** ₹10,000,000
- **Weighting approach:** Market-capitalisation weights

## Methodology
1. **Parametric VaR:** Estimates portfolio risk using the mean and standard deviation of returns under a normality assumption.
2. **Historical Simulation:** Estimates VaR using empirical return percentiles.
3. **Monte Carlo Simulation:** Generates simulated returns using estimated portfolio mean and volatility.
4. **Backtesting:** Compares observed VaR breaches against expected breach counts at both confidence levels.
5. **Basel Traffic-Light Test:** Classifies the number of breaches over the most recent 252 observations at the 99% confidence level.

## Key Findings
The initial workbook reported the following one-day VaR estimates:

| Method | 95% VaR | 99% VaR |
|---|---:|---:|
| Parametric | ₹202,307 | ₹286,822 |
| Historical Simulation | ₹198,397 | ₹314,289 |
| Monte Carlo | ₹215,593 | ₹291,931 |

The initial backtesting results showed 20 breaches for both Parametric and Monte Carlo VaR at the 99% confidence level, compared with approximately 12 expected breaches.

The report's independent review identified a sign error in the daily return calculation. After correcting the return series, Historical Simulation's 99% VaR increased to approximately ₹356,631. These corrected figures indicate that return construction and tail-risk estimation materially affect market-risk measurement.

## Limitations
- The initial workbook contains a return-sign and date-alignment error.
- Backtesting uses the same observations used to estimate VaR, creating in-sample bias.
- The Monte Carlo implementation uses normally distributed portfolio returns rather than a correlated simulation of individual assets.
- The simulation uses only 1,000 draws and is sensitive to random recalculation.
- The portfolio has substantial concentration in Asian Paints and Berger Paints.
- Corporate actions and potentially unadjusted price observations require further verification.

## Recommended Improvements
- Correct the return calculation and regenerate all results.
- Implement rolling-window, out-of-sample backtesting.
- Increase Monte Carlo simulations to at least 10,000 and incorporate cross-asset correlations.
- Add Expected Shortfall (ES) and formal backtesting tests.
- Evaluate fat-tailed distributions and volatility models such as GARCH.
- Validate price data and corporate-action adjustments.

## Repository Contents
- `VAR.xlsx` — Excel workbook containing the VaR analysis and dashboard.
- `VaR_Analysis_Report.pdf` — Detailed report covering methodology, findings, limitations, and recommendations.

## Tools and Concepts
**Tools:** Microsoft Excel

**Concepts:** Value-at-Risk, Market Risk, Portfolio Risk Measurement, Historical Simulation, Monte Carlo Simulation, Backtesting, Basel Traffic-Light Framework, Expected Shortfall, Financial Risk Management.

## Disclaimer
This project is for educational and analytical purposes only. The portfolio is hypothetical, and the estimates should not be interpreted as investment advice or regulatory risk estimates.
