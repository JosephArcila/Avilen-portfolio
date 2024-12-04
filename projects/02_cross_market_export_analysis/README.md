# Cross-Market Export Analysis

## Overview
This project analyzes the relationship between US poultry export volumes, Brazil export volumes, US inventory levels, and foreign currency dynamics. The analysis focuses on key importing countries to understand market dynamics and trade patterns.

## Objectives
- Visualize export volumes from both US and Brazil to major importing countries
- Compare export patterns with US inventory levels and foreign currency fluctuations
- Identify potential correlations between market variables

## Methodology

### Data Sources
- US Poultry Export Quantity (by country)
- Brazil Export Volume Data (by destination)
- US Inventory Levels (monthly)
- Foreign Currency Exchange Rates

### Data Processing
1. Converted US export data to metric tons (multiplied by 2240)
2. Applied -1 month shift to align export volumes with future market conditions
3. Merged datasets using left join to maintain main dataset integrity
4. Scaled Brazil export quantities by 1000x for visualization clarity

### Analysis Focus
Key importing countries analyzed:
- Philippines
- China
- Angola
- Iraq
- South Africa

## Visualizations

### Country-Specific Analysis
For each target country, created multi-axis visualizations showing:
- US exports (1 month forward)
- Brazil exports (1 month forward)
- US inventory levels
- Foreign currency rates

![Example Country Analysis](images/country_analysis.png)

### Global Market Overview
Created comprehensive visualization comparing:
- Total US exports worldwide
- Total Brazil exports
- US inventory levels
- Foreign currency rates

![Global Market Analysis](images/global_analysis.png)

## Technical Implementation

### Key Features
- Multi-axis plotting using matplotlib
- Time series alignment with data shifting
- Customized axis scaling for visualization clarity
- Grid implementation for year-based analysis
- Japanese-English mapping for country names

### Code Structure
```python
# Country mapping dictionary
country_name_mapping = {
    'フィリピン': 'Philippines',
    '中国': 'China',
    'アンゴラ': 'Angola',
    'イラク': 'Iraq',
    '南アフリカ': 'South Africa'
}

# Visualization implementation for each country
for country in countries:
    # Create multi-axis plot
    fig, (ax1, ax2, ax3) = plt.subplots(...)
    
    # Plot export data with time shift
    ax1.plot(data.shift(-1))
    
    # Add inventory and currency axes
    ax2.plot(inventory_data)
    ax3.plot(currency_data)
```

## Insights
- Export patterns show distinct seasonality across markets
- US inventory levels demonstrate inverse relationship with export volumes
- Currency fluctuations appear to influence export timing decisions
- Brazil and US exports often show complementary patterns in shared markets
