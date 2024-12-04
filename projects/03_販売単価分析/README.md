# AVILEN Sales Price Analysis Project

## Project Overview

At AVILEN, I was tasked with developing a data processing pipeline to analyze factors affecting sales prices. This project showcases my ability to handle complex data integration challenges in a Japanese business context, working with multiple economic indicators and Japanese-language datasets.

## Challenge

The business needed to analyze the relationship between sales prices (販売単価) and various economic indicators. This required:

1. Processing multiple data sources in different formats (CSV, Excel)
2. Handling Japanese-language datasets with varied encodings
3. Standardizing time series data from different reporting frequencies
4. Creating a clean, analysis-ready unified dataset

## Input Data Sources

Integrated six key economic indicators:

1. **Corporate Price Index** (企業物価指数)
   - Import Price Index focusing on food/agricultural products
   - Monthly time series data from CSV

2. **Wage Data** (賃金データ)
   - Nominal and real wage indices
   - Monthly observations

3. **Consumer Price Index** (消費者物価指数)
   - Multiple category breakdowns of consumer prices
   - Data from Excel with complex sheet structure

4. **Interest Rates** (金利)
   - Japanese interest rate data
   - Monthly observations

5. **GDP Data**
   - Real GDP expenditure approach data
   - Quarterly observations requiring conversion

6. **GDP Growth Rate** (GDP成長率)
   - Quarterly growth rate data
   - Required interpolation for monthly analysis

## Technical Implementation

### Data Processing Pipeline

The notebook demonstrates my implementation of:

1. **Automated File Processing**
```python
# Example: Intelligent encoding detection for Japanese text
with open(file_path, 'rb') as file:
    encoding = chardet.detect(file.read())['encoding']
df = pd.read_csv(file_path, encoding=encoding)
```

2. **Date Standardization**
```python
# Converting various date formats to YYYYMM
df['date'] = pd.to_datetime(df['date_column'], 
                           format='%Y/%m').dt.strftime('%Y%m')
```

3. **Time Series Integration**
```python
# Creating consistent monthly date range
date_range = pd.date_range(start='1994-01-01',
                          end='2023-12-31', 
                          freq='MS')
```

### Key Technical Features

1. **Robust Japanese Text Handling**
   - Automatic encoding detection
   - Proper processing of Japanese date formats
   - Handling of multi-byte characters

2. **Data Quality Management**
   - Automated type conversion with error catching
   - Consistent handling of missing values
   - Data validation checks

3. **Time Series Alignment**
   - Conversion of quarterly to monthly data
   - Proper handling of different date formats
   - Consistent datetime indexing

## Results

Successfully delivered:
- Unified dataset combining all economic indicators
- Clean, analysis-ready data structure
- Standardized monthly time series (1994-2023)
- Documentation of data processing methodology

## Technology Stack

- **Python**: Primary development language
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical operations
- **chardet**: Character encoding detection
- **Jupyter**: Development environment

## Repository Contents

- `notebooks/販売単価_data_collection_cleaning.ipynb`: Data processing pipeline
- `images/task_overview.png`: Original task requirements
- `README.md`: Project documentation

Note: The actual data files are not included as they contain proprietary information, but the notebook demonstrates the complete data processing methodology.

## Skills Demonstrated

- Data cleaning and integration
- Japanese language data processing
- Time series data handling
- Business requirements analysis
- Documentation and code organization
