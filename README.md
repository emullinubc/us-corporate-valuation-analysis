
# Firm-Level Determinants of Corporate Valuations Across U.S. Industries

### An Empirical Analysis of Growth, Profitability, and Financial Leverage

Eli Mullin  
University of British Columbia | Vancouver School of Economics  
ECON 326: Econometrics II  
November 2026 | Research in Progress

---

## 1. Research Question

How are revenue growth, profitability, and financial leverage associated with corporate valuation, and how do these relationships vary across U.S. industries?

Corporate valuation can be influenced by firm-specific fundamentals, particularly revenue growth, profitability, and financial leverage. This research examines the nature and strength of these relationships while controlling for relevant firm characteristics.

The analysis further investigates whether these relationships differ across industries, particularly between fast-growing technology firms and more established, capital-intensive sectors.

## 2. Data and Sample

Firm-level financial data were obtained from LSEG Workspace Screener.

The sample consists of publicly traded companies headquartered in the United States and listed on the following exchanges:

- New York Stock Exchange (NYSE)
- Nasdaq Global Select Market
- Nasdaq Global Market
- Nasdaq Capital Market
- NYSE American

Financials, Real Estate, Government Activity, and Institutions and Organizations are excluded from the sample because their valuation characteristics, financial structures, and accounting practices differ from those of the firms examined in this research.

The preliminary analytical sample contains 1,660 U.S. publicly traded companies. The final sample will be confirmed following validation of the exported financial data.

### Variables

The dependent variable is the natural logarithm of the enterprise value to EBITDA multiple:

$$\ln\left(\frac{EV_i}{EBITDA_i}\right)$$

The independent variables are defined as follows.

Revenue growth:

$$Growth_i = \frac{Revenue_{i,FY0}}{Revenue_{i,FY-1}} - 1$$

Operating profit margin:

$$Margin_i = \frac{\text{Operating Profit}_{i,FY0}}{\text{Revenue}_{i,FY0}}$$

Financial leverage:

$$Leverage_i = \frac{\text{Total Debt}_{i,FY0}}{\text{Total Assets}_{i,FY0}}$$

Firm size:

$$Size_i = \ln(\text{Total Assets}_{i,FY0})$$

Industry indicators are binary variables representing each firm's industry classification. These control for systematic differences in valuation across sectors.

## 3. Preliminary Summary Statistics

The preliminary analytical sample contains 1,660 observations for each variable.

| Variable | N | Mean | Median | SD | Min | Max |
|---|---:|---:|---:|---:|---:|---:|
| Log EV/EBITDA | 1660 | 2.578 | 2.480 | 0.850 | -0.640 | 8.264 |
| Revenue growth | 1660 | 0.348 | 0.056 | 6.472 | -0.399 | 232.582 |
| Operating margin | 1660 | 0.121 | 0.099 | 0.165 | -3.983 | 0.764 |
| Leverage | 1660 | 0.305 | 0.274 | 0.248 | 0.000 | 2.806 |
| Log total assets | 1660 | 21.911 | 21.910 | 1.861 | 16.190 | 27.832 |

Some variables exhibit substantial skewness, particularly revenue growth. The median is included to provide a measure of central tendency that is less sensitive to extreme observations.

These observations will be investigated before regression estimation.

## 4. Empirical Methodology

The research employs ordinary least squares (OLS) to estimate the relationships between corporate valuation and firm-level financial characteristics.

The proposed baseline regression specification is:

$$\ln\left(\frac{EV_i}{EBITDA_i}\right) = \beta_0 + \beta_1 Growth_i + \beta_2 Margin_i + \beta_3 Leverage_i + \beta_4 \ln(Assets_i) + \gamma_{s(i)} + \varepsilon_i$$

Where:

- $\beta_0$: intercept.
- $\beta_1$: association between revenue growth and valuation.
- $\beta_2$: association between operating profitability and valuation.
- $\beta_3$: association between financial leverage and valuation.
- $\beta_4$: association between firm size and valuation.
- $\gamma_{s(i)}$: industry fixed effects.
- $\varepsilon_i$: error term.

Industry fixed effects control for systematic differences in valuation levels across industries.

Subsequent specifications will introduce interaction terms between industry indicators and firm-level financial characteristics to investigate whether the relationships between growth, profitability, leverage, and valuation differ across sectors.

The estimated coefficients represent conditional associations rather than causal effects, as unobserved factors may influence both firm fundamentals and corporate valuation.

## 5. Tools and Data Availability

Tools: Python, Microsoft Excel, LSEG Workspace.

The underlying firm-level financial data were obtained through LSEG Workspace and are not publicly redistributed in this repository.

## Reference

London Stock Exchange Group (2026). *LSEG Workspace Screener*. Financial data retrieved November 12, 2026.
