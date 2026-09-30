# Event-Driven Portfolio Stress Testing

A Python framework for evaluating portfolio behaviour during historical market shocks and testing whether downside-risk measures remain informative under stress.

## Purpose

This project studies how portfolios respond to event-driven dislocations. It combines historical stress windows with rolling Value at Risk (VaR), Conditional Value at Risk (CVaR) and breach analysis to identify periods in which realized losses exceed model expectations.

Portfolio composition, event windows and reporting dates remain configurable while the broader portfolio-reporting framework is being standardized.

## Analytical Scope

- Event-window selection for historical stress episodes
- Portfolio construction across thematic or regional asset groups
- Rolling historical VaR estimation
- CVaR / Expected Shortfall measurement
- Identification and visualization of VaR breaches
- Comparative assessment of drawdown and diversification behaviour
- Automated risk-report generation

## Workflow

1. Retrieve market-price histories.
2. Construct portfolio return series from configurable allocations.
3. Calibrate risk thresholds using a pre-event lookback sample.
4. Evaluate returns during the selected stress window.
5. Compare realized losses, VaR and CVaR across portfolios.
6. Present model breaches and cross-portfolio risk differences.

## Repository Contents

| File | Description |
|---|---|
| [event_driven_risk_backtester_I.py](./event_driven_risk_backtester_I.py) | Primary historical stress-testing workflow |
| [event_driven_risk_backtester_II.py](./event_driven_risk_backtester_II.py) | Complementary event and portfolio comparison workflow |
| [Systemic_Stress_Test_Mining_Report.pdf](./Systemic_Stress_Test_Mining_Report.pdf) | Example report generated from the framework |

## Methods and Tools

- Historical simulation
- Rolling VaR and CVaR
- Event-driven backtesting
- Portfolio comparison and diversification analysis
- Python: Pandas, NumPy, Matplotlib and yfinance

## Limitations

Historical stress testing is conditional on the selected assets, weights, lookback period and event definition. It does not estimate every possible future shock, and VaR does not measure the magnitude of losses beyond its threshold. CVaR is included to provide additional information about tail severity.

## Development Context

This repository remains a standalone stress-testing module. Its validated components may later be integrated into the broader [Risk & Portfolio Engine](https://github.com/caballerohh/Risk-and-Portfolio-Engine) after portfolio and reporting conventions are fully aligned.

---

This project is provided for research, education and professional portfolio purposes. It does not constitute investment advice.
