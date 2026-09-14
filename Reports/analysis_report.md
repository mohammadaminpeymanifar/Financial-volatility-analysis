# Bitcoin Volatility Analysis Report
This project investigates Bitcoin return dynamics and volatility using a combined ARIMA-GARCH framework.
The primary objective was to determine whether Bitcoin returns are predictable and whether market volatility exhibits persistent behavior.
The results indicate limited predictability in returns but strong persistence in volatility, which is consistent with findings commonly reported in financial econometrics literature.

==============================
# Stationarity Analysis

## ADF Test Results
 | Series              | Result         |
 | ------------------- | -------------- |
 | Bitcoin Price       | Non-Stationary |
 | Bitcoin Log Returns | Stationary     |

### Interpretation
Bitcoin prices were found to be non-stationary, indicating the presence of trends and unit-root behavior.
After transforming prices into logarithmic returns, the series became stationary.
This result is consistent with the behavior of most financial assets, where returns are generally stationary while prices are not.

==============================
# ARIMA Analysis
An ARIMA(1,0,1) model was fitted to Bitcoin log returns.

### Findings
AR coefficient was not statistically significant.
MA coefficient was not statistically significant.
Residual diagnostics showed no meaningful autocorrelation.

### Interpretation
The results suggest that historical returns provide limited information for predicting future Bitcoin returns.
This finding is consistent with the Efficient Market Hypothesis, which states that publicly available information is rapidly incorporated into  market prices.

==============================
# GARCH Analysis
A GARCH(1,1) model was estimated using ARIMA residuals.

## Estimated Parameters
 | Parameter | Value |
 | --------- | ----- |
 | Alpha (α) | 0.078 |
 | Beta (β)  | 0.895 |
 | α + β     | 0.973 |

### Interpretation
The GARCH model successfully captured time-varying volatility.
The value of α + β = 0.973 indicates extremely high volatility persistence.
Market shocks tend to influence future volatility for an extended period rather than disappearing quickly.

==============================
# Volatility Clustering
One of the most important findings is the presence of Volatility Clustering.
Periods of high volatility are followed by high volatility, while calm periods tend to be followed by calm periods.
This behavior is a well-known characteristic of financial markets and was clearly observed in Bitcoin returns.

==============================
# Descriptive Statistics
 | Metric           | Value   |
 | ---------------- | ------- |
 | Mean Return      | 0.048%  |
 | Volatility (Std) | 2.99%   |
 | Minimum Return   | -17.41% |
 | Maximum Return   | 17.18%  |
 | Skewness         | -0.136  |
 | Kurtosis         | 4.123   |

### Interpretation
The return distribution exhibits:
 Slight negative skewness
 Excess kurtosis
 Fat-tailed behavior
These characteristics indicate that extreme market movements occur more frequently than predicted by a normal distribution.

==============================
# Forecast Results
Next-Day Forecast
 | Metric              | Forecast |
 | ------------------- | -------- |
 | Expected Return     | -0.025%  |
 | Expected Volatility | 2.55%    |

### Interpretation
The forecasted return is close to zero, reinforcing the conclusion that Bitcoin returns are difficult to predict.
However, the volatility forecast remains meaningful and provides useful information regarding market risk.

==============================
# Final Conclusion
The analysis demonstrates that Bitcoin returns exhibit limited predictability, while volatility can be modeled effectively using GARCH techniques.
The findings provide evidence of:
 Non-stationary prices
 Stationary returns
 Volatility clustering
 Strong volatility persistence
 Fat-tailed return distributions

Overall, the project highlights the importance of volatility modeling in financial analytics and risk management.

==============================================================================================================================================
نتایج این پروژه نشان داد که قیمت بیت‌کوین غیرمانا و بازدهی‌های آن مانا هستند. 
ARIMA ---------(توان محدودی در پیش‌بینی بازدهی آینده داشت)
GARCH ---------(توانست رفتار نوسانات بازار را به خوبی مدل‌سازی کند)
α + β= 0.973 ---------(بیانگر پایداری بسیار بالای نوسانات و وجود پدیده خوشه‌بندی نوسانات است) 
 توزیع بازدهی‌ها دارای دنباله‌های چاق (Fat Tails)--------- وقوع حرکات شدید قیمتی بیشتر از آن چیزی است که توزیع نرمال پیش‌بینی می‌کند
به طور کلی، نتایج نشان می‌دهند که اگرچه پیش‌بینی جهت حرکت قیمت بیت‌کوین دشوار است، اما ریسک و نوسانات آن قابلیت مدل‌سازی و پیش‌بینی دارند و می‌توان از این روش‌ها در تحلیل مالی و مدیریت ریسک استفاده کرد.
