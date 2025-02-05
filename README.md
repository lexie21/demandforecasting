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
  
**<h4>Warehouse:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/by_warehouse.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/stacked_wh.png)
<h3>Recommendations & Next Steps</h3>

## Modeling
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/series_plot.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/diagnostics.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/outsample_forecast_SARIMAX.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/outsample_forecast_LSTM.png)
