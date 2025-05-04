# Macroeconomic and Business Analysis of Ireland Project Datasets

## Overview
This repository contains datasets for the Macroeconomic Vulnerability Index project at the Centre for Development Studies, Jawaharlal Nehru University. The datasets include:

1. **Annual Macroeconomic Variables of Ireland (1990–2024)**  
2. **Quarterly Inflation & Unemployment Rates (2010–2024)**  
3. **Quarterly Monetary Aggregates (2010–2024)**  
4. **Quarterly Potential GDP & Output Gap (2010–2024)**  
5. **All Countries Important Indicators for MVI (2010–2024)**  

Each dataset includes detailed column definitions, sources, time spans, and notes on data processing (imputation, seasonal adjustment, filters).

---

## 1. Annual Macroeconomic Variables of Ireland (1990–2024)

**Filename:**  
`Annual Macroeconomic Variable of Ireland (1990-2024).csv`

**Source & Imputation:**  
- Base data from World Bank’s World Development Indicators (WDI).  
- Latest-year GDP (constant prices), inflation, unemployment from Ireland’s CSO and Central Bank (adjusted base years).  
- For any pair of variables with Pearson correlation > 0.9, missing values are imputed via linear regression on the correlated series.

**Frequency & Coverage:**  
Annual, calendar years 1990 through 2024.

**Columns:**  
| Column                                                     | Description                                                                                       |
|------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| `Year`                                                     | Calendar year (1990–2024)                                                                         |
| `Central government debt, total (% of GDP)`                | Total central government debt as a share of GDP                                                   |
| `Consumer price index (2010 = 100)`                        | Annual CPI index, base year 2010                                                                  |
| `Current account balance (% of GDP)`                       | CA balance as % of GDP (WDI)                                                                      |
| `Current account balance (BoP, current US$)`               | CA balance in current U.S. dollars                                                                |
| `Domestic credit to private sector (% of GDP)`             | Domestic private credit (% of GDP)                                                                |
| `Exports of goods and services (constant LCU)`             | Exports in real local currency units                                                              |
| `Exports of goods and services (% of GDP)`                 | Exports as % of GDP                                                                               |
| `Final consumption expenditure (% of GDP)`                 | Final household + government consumption as % of GDP                                              |
| `Foreign direct investment, net inflows (% of GDP)`        | FDI net inflows as % of GDP                                                                       |
| `Foreign direct investment, net inflows (BoP, current US$)`| FDI net inflows in current U.S. dollars                                                           |
| `GDP (current LCU)`                                        | Nominal GDP in local currency units                                                               |
| `GDP (constant LCU)`                                       | Real GDP in local currency units (constant prices)                                                |
| `GDP (current US$)`                                        | Nominal GDP in U.S. dollars                                                                       |
| `Inflation rate (WDI)`                                     | Year-over-year % change in CPI                                                                    |
| `Unemployment rate (% of labor force)`                     | % of total labor force unemployed                                                                 |
| `Trade (% of GDP)`                                         | (Exports + Imports) as % of GDP                                                                   |
| `Merchandise trade (% of GDP)`                             | Exports + Imports of goods only, as % of GDP                                                      |
| `Net lending (+) / net borrowing (–) (% of GDP)`           | Government net lending/borrowing as % of GDP                                                      |
| `Tax revenue (% of GDP)`                                   | Total government tax revenue as % of GDP                                                          |
| `Military expenditure (% of GDP)`                          | Military spending as % of GDP                                                                     |
| `Research and development expenditure (% of GDP)`          | R&D spending as % of GDP                                                                          |
| `Market capitalization of listed domestic companies (% of GDP)` | Equity market cap as % of GDP                                                                |
| `Natural resources rents (% of GDP)`                       | Total resource rents (oil, gas, minerals) as % of GDP                                             |
| _...plus 86 other WDI series (see CSV for full list)_      |                                                                                                   |

---

## 2. Quarterly Inflation & Unemployment Rates (2010–2024)

**Filename:**  
`Quarterly Inflation and Unemployment Rates (2010-2024).csv`

**Source:**  
OECD Main Economic Indicators

**Seasonal Adjustment:**  
- **Inflation Rate (HICP)**: Not seasonally adjusted  
- **Unemployment Rate**: Seasonally adjusted  

**Frequency & Coverage:**  
Quarterly, Q1 2010 through Q4 2024

**Columns:**
| Column             | Description                                                   |
|--------------------|---------------------------------------------------------------|
| `Date`             | Quarter end date (YYYY-MM-DD)                                 |
| `Inflation Rate`   | Harmonized CPI (HICP) total for Ireland                       |
| `Unemployment Rate`| Unemployment rate for ages 15-64                              |

---

## 3. Quarterly Monetary Aggregates (2010–2024)

**Filename:**  
`Quarterly Monetary_Aggregates_Ireland (2010-2024).csv`

**Source:**  
Eurostat

**Frequency & Coverage:**  
Quarterly, Q1 2010 through Q4 2024

**Columns:**
| Column                    | Description                                      |
|---------------------------|--------------------------------------------------|
| `Date`                    | Quarter end date                                 |
| `Year`                    | Calendar year of quarter                         |
| `Quarter`                 | Quarter number (1–4)                             |
| `Corporate_Credit`        | Credit to non-financial corporations             |
| `Household_Deposits`      | Deposits held by households                      |
| `Corporate_Deposits`      | Deposits held by non-financial corporations      |
| `Private_Sector_Deposits` | Deposits by private sector entities              |
| `Household_Loans`         | Loans extended to households                     |
| `M1`                      | Monetary aggregate M1                            |
| `M2`                      | Monetary aggregate M2                            |
| `M3`                      | Monetary aggregate M3                            |

---

## 4. Quarterly Potential GDP, Actual GDP & Output Gap (2010–2024)

**Filename:**  
`Quarterly Potential GDP Actual GDP and Output Gap (2010-2024).csv`

**Source & Methodology:**  
- **Actual GDP** from Ireland’s CSO.  
- **Potential GDP** estimated by:  
  1. 21-quarter moving average (MA)  
  2. Hodrick–Prescott (HP) filter  
- **Output Gap** = Actual GDP − Potential GDP

**Frequency & Coverage:**  
Quarterly, Q1 2010 through Q4 2024

**Columns:**
| Column             | Description                                        |
|--------------------|----------------------------------------------------|
| `TIME_PERIOD`      | Quarter (YYYY-MM format)                           |
| `Actual_GDP`       | Observed GDP                                       |
| `Potential_GDP_MA` | Potential GDP via 21-quarter moving average        |
| `Potential_GDP_HP` | Potential GDP via HP filter                        |
| `Potential_GDP`    | Final chosen potential GDP series (MA or HP based) |
| `Output_Gap`       | Actual minus potential GDP                         |

---

## 5. All Countries Important Indicators for MVI (2010–2024)

**Filename:**  
`All countries Important Indicators for MVI.csv`

**Source:**  
- World Bank DataBank (WGI, CPIA, macro variables)  
- World Economic Forum (WEF) Global Competitiveness Index (GCI)  
- World Intellectual Property Organization (WIPO) Global Innovation Index (GII)  
- World Bank Doing Business archives  
- Economist Intelligence Unit (EIU) Country Risk and Democracy Index  
- INFORM and ND-GAIN databases  

**Purpose:**  
Used to construct a Multidimensional Vulnerability Index ranking for 199 countries, based on 21 key indicators.  

**Methodology:**  
- Simple averages for all indicators.  
- Weighted averages for annual data (2010–2024).  

**Columns (Key Indicators):**  
| Column                                             | Description                                                                 |
|----------------------------------------------------|-----------------------------------------------------------------------------|
| `Country Name`                                     | Name of the country                                                         |
| `Country Code`                                     | ISO 3-letter country code                                                   |
| `Series Name`                                      | Indicator name (e.g., GDP growth, inflation, governance scores)             |
| `2010`–`2024`                                     | Annual values for each indicator                                            |
| **Example Indicators:**                            |                                                                             |
| `Central government debt, total (% of GDP)`        | Total central government debt as % of GDP                                   |
| `Control of Corruption: Estimate`                  | World Governance Indicator (WGI) score                                      |
| `Current account balance (% of GDP)`               | Current account balance as % of GDP                                         |
| `GDP growth (annual %)`                            | Annual GDP growth rate                                                      |
| `Inflation, consumer prices (annual %)`            | Annual inflation rate                                                       |
| `Unemployment, total (% of labor force)`           | Unemployment rate                                                           |
| `Government Effectiveness: Estimate`               | WGI score for government effectiveness                                      |
| `Political Stability and Absence of Violence/Terrorism: Estimate` | WGI score for political stability                               |
| `Regulatory Quality: Estimate`                     | WGI score for regulatory quality                                            |
| `Voice and Accountability: Estimate`               | WGI score for voice and accountability                                      |
| `Foreign direct investment, net inflows (% of GDP)`| FDI inflows as % of GDP                                                     |
| `Research and development expenditure (% of GDP)`  | R&D spending as % of GDP                                                    |
| `Human capital index (HCI) (scale 0-1)`            | World Bank Human Capital Index                                              |
| `Total reserves (% of total external debt)`        | Reserves as % of external debt                                              |

---

## Notes on Usage

- **Imputation:** Missing annual data for the latest years was sourced directly from national statistical offices and central banks; variables with correlation > 0.9 used regression-based imputation.  
- **Seasonality:** Only unemployment is seasonally adjusted in the quarterly rates file.  
- **Potential GDP:** Both MA and HP series are provided—users should state which they employ.  
- **MVI Construction:** For the multidimensional index, ensure consistency in weighting and normalization of indicators.  
- **Data Licensing:** Please cite the original data providers (WDI, OECD, Eurostat, CSO, WEF, WIPO, EIU, INFORM, ND-GAIN) when publishing results.

---

*End of README*  
