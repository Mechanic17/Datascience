# Data Science
# Sales Data Analysis for Online Retail

## Project Description

This project is an analysis of sales data from an online retail business. The data includes information about products, sales dates, customers, quantities, and product prices. The main goal of this analysis is to explore relationships between variables, identify potential anomalies, visualize the data, and provide business insights.

## Main Analysis Stages

### 1. Data Loading and Preprocessing
We loaded data from the original file and performed preprocessing steps:
- Removed duplicate records and handled missing values.
- Converted numerical data to appropriate types to avoid errors in further calculations.
- Added a new column, `TotalPrice`, to calculate the total value of each order based on the quantity (`Quantity`) and unit price (`UnitPrice`).

### 2. Data Analysis
#### Statistical Description
We generated key statistical metrics for the data, such as averages, minimum and maximum values, standard deviations, and quartiles for numeric columns (`Quantity`, `UnitPrice`, `TotalPrice`).

#### Checking for Missing Values and Anomalies
We analyzed the data for missing values and outliers (e.g., negative values in `Quantity` and `UnitPrice`), which could skew the results of the analysis.

### 3. Investigating Relationships Between Variables
#### Correlation Analysis
We created a correlation matrix for quantitative features, which revealed a strong positive correlation between `Quantity` and `TotalPrice`. This relationship makes sense, as the total order amount (`TotalPrice`) depends on the quantity of products sold. Meanwhile, the correlation between `UnitPrice` and other features is significantly weaker, suggesting a lack of association between product price and quantity.

#### Analysis of Unit Price Changes for Individual Products
For items with the same `StockCode`, we analyzed the time-based dynamics of price changes, which helped us identify price fluctuations. These may indicate seasonal discounts, price policy changes, or promotional activities.

### 4. Representative Sample for Visualization and KNIME Analysis
A representative subset of data was selected to facilitate simplified visualization and further analysis in the KNIME tool.

## Data Visualization

We created several key visualizations:
- **Correlation Matrix**: This visually highlighted relationships between quantitative features.
- **Price Change Plot for Individual Products**: This showed `UnitPrice` changes for specific items over time, allowing us to assess price stability and identify potential fluctuations.

## Insights and Hypotheses

- **Strong Correlation Between `Quantity` and `TotalPrice`**: Indicates a direct relationship between order total and quantity. These data could assist in optimizing inventory management and offering discounts for bulk purchases.
- **Price Analysis**: Variations in `UnitPrice` for the same item may relate to seasonality, promotions, or pricing policy changes, which are important for marketing strategies.
- **Data Anomalies**: The presence of negative values may indicate product returns or accounting errors, which should be considered when calculating profit and loss metrics.

## Possible Next Steps
# Logical Analysis and Hypothesis Formulation

## Insights and Hypotheses from Anomalies and Logical Analysis

### 1. Strong Correlation Between `Quantity` and `TotalPrice`
   - **Hypothesis 1**: Increasing the number of purchased items may decrease their price due to discounts. This can be tested by comparing the average product price across orders of varying volumes.
   - **Hypothesis 2**: If `TotalPrice` remains stable despite an increase in `Quantity`, the item might be sold at a fixed price regardless of quantity. This could indicate the use of constant pricing, which is important for pricing strategy decisions.

### 2. Analysis of `UnitPrice` Changes for Individual Products
   - **Hypothesis 3**: Temporal changes in `UnitPrice` may reflect seasonal promotions, cost adjustments, or new marketing strategies. If the price of the same product fluctuates by month, it may indicate seasonal sales or demand shifts.
   - **Hypothesis 4**: Sharp price changes might point to accounting errors or incorrect data. For instance, if `UnitPrice` is significantly higher or lower than the average price for similar products, it may indicate outliers or data entry errors.

### 3. Anomalies Such as Negative `Quantity` Values
   - **Hypothesis 5**: Negative values in `Quantity` may be associated with product returns. This information is crucial for understanding return reasons and building models to reduce future returns.
   - **Hypothesis 6**: If negative values appear more frequently for certain products, this may indicate poor quality or failure to meet customer expectations. We could explore connections between specific products and return frequency.

### 4. Missing `CustomerID` Data
   - **Hypothesis 7**: Missing `CustomerID` values may indicate one-time purchases where customer registration is not mandatory. This could mean a large portion of anonymous buyers, which is essential for customer segmentation.
   - **Hypothesis 8**: Recurring `CustomerID` gaps in specific periods may indicate promotions attracting new customers who are not yet registered in the system. We can analyze in which periods these purchases increase and whether they are tied to promotions or seasonal demand shifts.

## Next Steps for Hypothesis Testing

1. **Testing Discounts with Increasing Quantity**:
   - Compare average `UnitPrice` for different `Quantity` values and identify price dependencies on order volume.

2. **Seasonal Price Trend Analysis**:
   - Create a time series plot of `UnitPrice` changes by month or quarter to identify seasonal trends, if present.

3. **Identifying Return Reasons**:
   - Analyze products with negative `Quantity` values to determine reasons for returns by category or brand, aiding in quality improvement.

4. **Anonymous Purchase Analysis**:
   - Investigate `CustomerID` gaps and their time-based trends to understand which promotions or periods attract the highest number of new, unregistered customers.

## Conclusion

This project demonstrates the potential for in-depth sales data analysis to identify anomalies, form logical hypotheses, and generate business insights. Analyzing anomalies, such as negative values and missing data, enables us to formulate hypotheses about customer behavior, demand shifts, and product quality issues.
