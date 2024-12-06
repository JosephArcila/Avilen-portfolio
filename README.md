# AVILEN 日本ハム project AI Development Portfolio
*February 2024 - September 2024*

## Overview
This repository documents my work as an AI Developer at AVILEN on the 日本ハム project, where I focused on data analysis and predictive modeling for market trends and pricing.

## Project Structure
```
Avilen-portfolio
├── 01_data_cleaning                # Data preprocessing pipelines
├── 02_cross_market_export_analysis # Export market visualization 
├── 03_販売単価分析                 # Sales price analysis
├── 04_販売単価_vs_○○○_analysis     # Price correlation studies
├── 05_predicting_large_changes_in_外貨  # Currency change prediction
├── 06_predicting_出回り数量_LightGBM    # Distribution volume forecasting
├── 07_predicting_フード販売単価         # Food price prediction
└── 08_research_task                # Industry AI implementation research
```

## Key Projects

### 1. Data Cleaning Projects
*Tools: Python, pandas*

Processed three types of data sources:
1. Container Freight Charges
   - Converted PDF format into structured CSV data
   - Standardized date formats to yyyymm
   - Created consistent numeric columns

2. Market Conditions Data
   - Consolidated data from Brazil, Thailand, USA, and China
   - Standardized currency representations
   - Unified missing value handling

3. Brazil Export Analysis
   - Transformed export data into analyzable time series
   - Processed nested year data structures
   - Implemented country name translations

### 2. Cross-Market Export Analysis
*Tools: Python, matplotlib*

Created visualizations comparing:
- US exports (shifted 1 month forward)
- Brazilian exports (scaled and shifted 1 month forward)
- US inventory levels
- Foreign currency rates

Generated analysis for key markets:
- Philippines
- China
- Angola
- Iraq
- South Africa

![Philippines Export Analysis](02_cross_market_export_analysis/philippines_analysis.png)

### 3. Sales Price Analysis 
Integrated six economic indicators:
1. Corporate Price Index (企業物価指数)
2. Wage Data (賃金データ)
3. Consumer Price Index (消費者物価指数)
4. Interest Rates (金利)
5. GDP Data
6. GDP Growth Rate (GDP成長率)

### 4. Price Correlation Analysis
Analyzed relationships between:
- Sales unit prices and consumer prices
- Shipping volumes and inventory metrics
- Market indicators with lag effects

Key findings from detrended analysis:
- Earlier years (2012-2017): Predominantly negative detrended values
- Recent years (2022-2024): Higher volatility with both positive and negative deviations

### 5. Currency Change Prediction
Analyzed different thresholds for predicting significant currency price changes:

| Threshold | Precision | Recall | F1 Score | Accuracy |
|-----------|-----------|---------|-----------|-----------|
| 0.5       | 0.6667    | 0.3784  | 0.4828    | 0.7000    |
| 1.0       | 0.7778    | 0.1892  | 0.3043    | 0.6800    |
| 1.5       | 0.6667    | 0.1081  | 0.1860    | 0.6500    |
| 2.0       | 1.0000    | 0.0541  | 0.1026    | 0.6500    |
| 2.5       | 1.0000    | 0.0270  | 0.0526    | 0.6400    |
| 3.0       | 1.0000    | 0.0270  | 0.0526    | 0.6400    |

### 6. Distribution Volume Prediction
*Tools: LightGBM*

Implemented various feature combinations with results:
1. Basic Inventory Lags: MAPE 2.15%
2. Rolling Statistics: MAPE 2.13%
3. Inventory Differences: MAPE 2.13%
4. Currency Lags: MAPE 2.14%
5. Currency Differences: MAPE 2.11%
6. Currency-Inventory Interactions: MAPE 2.40%
7. Categorical Features: MAPE 2.13%
8. Derived Inventory Metrics: MAPE 2.15%
9. Conditional Features: MAPE 2.06%
10. Final Combined Model: MAPE 2.04%

### 7. Food Price Prediction
Developed LightGBM model with feature engineering:
- Lag features for key metrics (2-6 months)
- Rolling statistics
- Interaction features between currency rates and inventory levels

Final model achieved MAPE of 2.04% on test data starting from January 2021.

### 8. Industry Research
Researched AI implementation in major food companies:

**Tyson Foods Implementation:**
- AWS machine learning for chicken tray detection
- Quantified Result: 15,000 hours of skilled labor saved annually in one facility
- Automation Program: $1.3 billion investment over three years
- Results: 48% EPS growth to $2.87 in Q1 2022, 24% sales increase

**JBS Implementation:**
- AI-driven carcass sorting system
- AI cameras for tender steak processing quality assessment in Canada

**Sysco Implementation:**
- Partnership with iFoodDS for traceability solutions
- Focus on FSMA 204 compliance

## Recognition
Project feedback from Kota Kobayashi, Data Scientist at AVILEN:
> "時系列データを用いたコード実装のアウトプットはいつも期待値を超えていました。抽象的な業務も自身でタスクに分解して期待以上のアウトプットを出せます。"
