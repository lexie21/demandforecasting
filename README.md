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

**<h4>Product Category & Code:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/treemap%20orders.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/stacked_area.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/max_product.png)

**<h4>Warehouse:</h4>**
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/by_warehouse.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/stacked_wh.png)
<h3>Recommendations & Next Steps</h3>

## Modeling
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/series_plot.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/diagnostics.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/outsample_forecast_SARIMAX.png)
![Alt Text](https://github.com/lexie21/demandforecasting/blob/main/images/outsample_forecast_LSTM.png)
