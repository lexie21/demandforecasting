# Order Demand Forecasting Analysis

<details>
<summary><b>Check out my other projects!</b></summary>
  
[Movie Recommender](https://github.com/lexie21/movierecommender)

[Loan Defaulter](https://github.com/lexie21/loandefaulter)

</details>

## Table of Contents
- [Introduction](#introduction)
- [EDA](#exploratory-data-analysis)
- [Modeling](#modeling)

## Introduction

<b>What this project is about?</b>

- Project Scope

  Accurate demand forecasting is crucial for optimizing operations in global manufacturing. This project focuses on developing a data-driven approach to predict demand, helping a multinational manufacturing company enhance its production planning and inventory management. Our initial objective is to improve the accuracy of quantity forecasts. By leveraging historical sales data, market trends, and statistical modeling techniques, we aim to minimize discrepancies between predicted and actual demand.

  Through this project, we aim to deliver actionable insights that drive cost efficiency and operational resilience in manufacturing.

- Next Steps

  Once we refine overall demand estimation, we will extend our model to generate product-specific forecasts across multiple warehouses. This will enable more precise inventory allocation, reducing both stockouts and excess inventory while improving supply chain efficiency.

<b>What I did?</b>

- EDA
  
  Conducted in-depth EDA to understand demand patterns at both the overall metric level and across different dimensions (e.g., time, product categories, warehouses).
  Identified trends, seasonality, and anomalies in historical demand data.

- Forecasting
  
  Implemented various models from traditional econometrics and deep learning including SARIMAX to establish baseline forecasts and LSTM to capture complex temporal dependencies.
  Compared model performance using key evaluation metrics (e.g., RMSE, MAE) to select the best forecasting approach.
  
## Exploratory Data Analysis
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/daily_orders.png)

<h3>Metrics and Dimensions</h3>

- **Order**: Average quantity per order from all products
- **Product category and code**: 2160 codes spread over more than 30 categories
- **Central warehouse**: Warehouse A, C, J, S

<h3>Summary of Insights</h3>

**<h4>Order:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/avg_order_series.png)

- Average daily orders tended to experience spikes of extremely large quantities at 100K to over 200K during the end of each year from 2013 to 2016, which likely shows that the types of products manufactured by the company are usually consumed during holiday seasons. These spikes became much more regular from 2016 - investigate whether this is due to the introduction of new products or other logistical changes.
- Average order quantities per month exhibited a modestly increasing trend amidst frequent fluctutations. The last two years of 2015 and 2016 observed the highest records among the entire period. Seasonality-wise, orders consistently dropped in February as well as between September/October. 

**<h4>Product Category & Code:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/treemap%20orders.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/stacked_product.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/max_product.png)

- Category 019 remains the best-seller in terms of total sales and typically made up about 80% of orders, although this number has been decreasing mildly over the years. Within this category, a few products stood out with orders ranging from 80K to almost 200K. Specifically, product 1245 reported a total sales of 180K orders. 
- The other best-selling categories were 006, which had the highest orders for product 1152, followed by 005 and 007, with all products in both categories having orders below 40K.
- With respect to monthly top-selling products, product 1432 and 1248 dominated both in terms of frequency and actual order quantity. Among these, product 1432 always received huge one-time orders with quantities exceeding 2M on average. A significant observation is that product 1245 started to emerge as a strong top-selling candidate on a monthly basis starting in 2015, potentially due to shifting customer preferences or its recent introduction to the market.

**<h4>Warehouse:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/by_warehouse.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/stacked_wh.png)

- The orders for warehouse J and A were always consistently lower relatively in comparison to the remaining warehouses at 5K for the former and 1K for the latter. Meanwhile, while warehouses C and S had similar average order quantities from 2012 to 2015, warehouse S took a clear lead in 2016, reporting a significantly higher number of orders at over 200K. Interestingly, it experienced a gradual downward trend to meet warehouse C again during the final months of 2016 - examine if this unusual surge was due to marketing/promotion effect or reallocation of manufacturing locations for different products.
- However, when we look at total orders by location, warehouse J became the top-performing warehouse accounting for approximately 70% of all orders. It is followed by warehouse S and C at about 20% and 10% respectively, with the latter's contribution consistently increasing from 2014.
- This indicates that orders from warehouse J are typically placed at a high frequency, in contrast to those from warehouse C and S.
  
<h3>Recommendations & Next Steps</h3>

- Investigate the reasons behind the regular year-end order surges, determining whether this is primarily a seasonal effect or related to specific product issues, and explore strategies to replicate such increases during other time periods.
- Orders from Categories 019 and 006 have a disproportionate impact on sales due to a limited number of specific best-selling products; therefore, identify complementary products that could attract the same customer base and ensure consistent stock availability to prevent shortages or disruptions.
- Warehouse S’s surge in 2016 followed by a decline warrants investigation to determine whether it was driven by marketing campaigns or a reallocation of manufacturing locations, which could guide future strategies. Warehouse J, which accounts for 70% of total orders, should focus on enhancing fulfillment efficiency and leveraging demand forecasting to improve operational performance. Meanwhile, warehouses A and C, with their relatively lower order frequencies, should consider inventory redistribution and product diversification to balance performance across locations and support sustained growth.

## Modeling

| Model | MSE | MAE | 
|------------|----------|--------|
| SARIMAX       | 0.821 | 0.651  |
| LSTM       | 0.651    | 0.547   | 

**<h4>Log Differenced Series:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/series_plot.png)

**<h4>Diagnostics for SARIMAX:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/diagnostics.png)

**<h4>Forecasts from SARIMAX:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/outsample_forecast_SARIMAX.png)

**<h4>Forecasts from LSTM:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/outsample_forecast_LSTM.png)
