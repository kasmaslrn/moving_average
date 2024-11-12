# Moving Average Strategy Analysis

## Overview

This project analyses a **moving average crossover strategy** applied to the S&P 500 index over a 24-year period (2000-2024). The analysis compares the effectiveness of a dual moving average crossover strategy (50-day vs 200-day) against a simple Buy-and-Hold approach, aiming to determine if it provides better risk-adjusted returns during major market events like the Dot-com Bubble, the 2008 Financial Crisis, and the COVID-19 Pandemic.

## Key Features

- **Dual Moving Average Crossover Strategy**: Uses a **50-day fast moving average (FAST_MA)** and a **200-day slow moving average (SLOW_MA)**. The system buys when the FAST_MA crosses above the SLOW_MA (bullish signal) and sells when it crosses below (bearish signal), aiming to capture short-term trends while filtering out noise.
- **Benchmark Comparison**: Compares the strategy's performance against a simple Buy-and-Hold portfolio to evaluate if the moving average crossover provides better risk-adjusted returns.

## Libraries Used

This project utilises the following Python libraries:

1. **yfinance**: To download historic price data for the S&P 500.
2. **numpy**: For numerical operations and generating metrics such as rolling averages.
3. **matplotlib**: To visualise price movements, moving averages, and strategy performance.
4. **seaborn**: For generating heatmaps used in sensitivity analysis to compare parameter settings.
5. **datetime**: For handling date operations.

## Technical Implementation Details

- **Data Preparation**: Data is downloaded from Yahoo Finance using `yfinance` and stored for analysis. A starting balance of $10,000 is used to compute the strategy's portfolio performance.

- **Moving Averages Calculation**: The 50-day (`FAST_MA`) and 200-day (`SLOW_MA`) moving averages are calculated to generate buy and sell signals based on crossover points.

- **Backtesting Logic**: The system enters a **long** position when the `FAST_MA` crosses above the `SLOW_MA` (buys) and exits when it falls below (sells). Portfolio value is updated based on returns during the period when a position is held.

- **Performance Metrics**: Key metrics include:
  - **Total Return**: Overall return over the entire period.
  - **CAGR (Compound Annual Growth Rate)**: Average annual growth rate.
  - **Maximum Drawdown**: Largest drop from peak to trough, indicating downside risk.
  - **Time in Market**: Percentage of time invested, providing insight into exposure compared to Buy-and-Hold.

- **Heatmap Sensitivity Analysis**: Generated using Seaborn to explore performance across different combinations of moving averages, providing insight into parameter sensitivity and potential optimal values.

## Areas for Improvement

To further enhance the analysis and the visualisation of results, the following additions can be made:

- **Event Annotations**: We could enhance the analysis by adding more event annotations such as the **Dot-com Bubble** (2000-2002), **Financial Crisis** (2007-2009), and **COVID-19 Crash** (2020). Highlighting these events on the charts would help visualise how the strategy performs during significant market turmoil, providing a clearer picture of its risk management capabilities.

- **Additional Metrics**:
  - **Sharpe Ratio**: Adding the Sharpe Ratio would allow for a more thorough risk-adjusted performance assessment by comparing excess returns to return volatility.
  - **Volatility**: Including volatility as a metric would give a clearer understanding of the risk inherent in the strategy by quantifying the variability of returns.
## Key Insights from the Analysis

- **Market Timing vs. Buy-and-Hold**: The moving average crossover strategy offers a method for mitigating losses during bear markets by generating sell signals when short-term trends weaken. During key downturns like the **2008 Financial Crisis**, the strategy experienced fewer drawdowns compared to the Buy-and-Hold approach.
- **Risk-Adjusted Returns**: While the Buy-and-Hold strategy tends to perform well during bull markets, the crossover strategy can help manage risk more effectively by reducing exposure during prolonged downtrends. This was particularly evident during the **Dot-com Bubble** and **COVID-19 Crash**.
- **Performance Across Timeframes**: Sensitivity analysis of different moving average combinations was conducted to determine optimal settings, providing valuable insights into which configurations maximise return while minimising risk.
- **Reduced Volatility**: The moving average strategy effectively reduced portfolio volatility during periods of market uncertainty, resulting in a smoother equity curve compared to a simple Buy-and-Hold approach.

## Summary

Overall, this analysis demonstrates that a moving average crossover strategy can be an effective tool for managing risk and optimising returns in volatile market environments. While it may not always outperform the Buy-and-Hold approach during long bull markets, it adds significant value during times of uncertainty by mitigating drawdowns and reducing overall portfolio volatility.

This project provides a comprehensive toolkit for analysing technical indicators using historic data, exploring both the benefits and limitations of moving average strategies in a practical, real-world context. Additionally, the sensitivity analysis offers insights into how robust the strategy is to parameter changes, allowing users to fine-tune the moving average periods to achieve the desired risk-return profile.

