# Data Analysis on GameZone Orders Data
This document provides an overview and description of the `gamezone-orders-data.xlsx` (20K-row e-commerce) dataset.

## Dataset Description

The `gamezone-orders-data.xlsx` file contains historical order data for a gaming company, GameZone. Each row in the dataset represents a single customer order and includes various attributes related to the purchase, shipping, customer, and product.
The dataset is assumed to be internal order data collected by the company named GameZone.

## Columns

The dataset contains the following columns:

-   **USER_ID**: A unique identifier for the user who placed the order.
-   **ORDER_ID**: A unique identifier for the specific order.
-   **PURCHASE_TS**: The timestamp when the order was placed.
-   **SHIP_TS**: The timestamp when the order was shipped.
-   **PRODUCT_NAME**: The name of the product purchased.
-   **PRODUCT_ID**: A unique identifier for the product purchased.
-   **USD_PRICE**: The price of the product in US Dollars.
-   **PURCHASE_PLATFORM**: The platform used for the purchase (e.g., website, mobile app).
-   **MARKETING_CHANNEL**: The marketing channel through which the customer was acquired for this order (e.g., organic, paid search, social media).
-   **ACCOUNT_CREATION_METHOD**: The method used to create the user's account (e.g., email, social login).
-   **COUNTRY_CODE**: The country from which the order was placed.

## Potential Use Cases

This dataset can be used for various analytical tasks, including:

-   Analyzing sales trends over time.
-   Identifying popular products.
-   Understanding customer purchase behavior based on platform, marketing channel, country, and account creation method.
-   Evaluating the efficiency of shipping processes.
-   Building predictive models for sales forecasting, price prediction, or customer segmentation.
-   Identifying operational bottlenecks or areas for improvement.


## ISSUE LOGS : Data Cleaning and Preparation

Based on analysis of this dataset, the following cleaning and preparation steps were performed:

-   Missing values in `MARKETING_CHANNEL`, `ACCOUNT_CREATION_METHOD`, and `COUNTRY_CODE` were filled with 'Unknown'.
-   Rows with missing `USD_PRICE` values were removed.
-   Duplicate rows were removed.
-   Categorical columns (`PURCHASE_PLATFORM`, `MARKETING_CHANNEL`, `ACCOUNT_CREATION_METHOD`, `COUNTRY_CODE`) were standardized to lowercase to handle potential inconsistencies.
-   The `USD_PRICE` column was converted to a numeric type.
-   Timestamp columns (`PURCHASE_TS`, `SHIP_TS`) were converted to datetime objects, and rows where conversion failed were removed.
-   New features were engineered from timestamps, including purchase/ship year, month, day of week, hour, and shipping duration in days.
-   Categorical features were one-hot encoded for machine learning modeling.
