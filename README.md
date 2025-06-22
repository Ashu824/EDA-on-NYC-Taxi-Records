# 🗽 EDA on NYC Taxi Records (2023)

This repository contains a Jupyter Notebook that performs **Exploratory Data Analysis (EDA)** on the 2023 Yellow Taxi Trip Data from New York City. The goal is to explore data patterns, clean inconsistencies, and derive business insights to optimize taxi operations in NYC.

---

## 📌 Problem Statement

As a data analyst at a new taxi startup in NYC, your objective is to analyze public taxi data and uncover patterns that can:

- Improve dispatch efficiency
- Maximize revenue
- Enhance rider experience

---

## 📂 Dataset Overview

The dataset includes yellow taxi trip records for each month in 2023, published by the **NYC Taxi & Limousine Commission (TLC)**. Each file is in `.parquet` format, with 12 files (one per month).

### 🔑 Key Columns

| Feature              | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `VendorID`           | Code for TPEP provider (1 = CMT, 2 = VeriFone)                              |
| `tpep_pickup_datetime` | Timestamp when meter was turned on                                         |
| `tpep_dropoff_datetime` | Timestamp when meter was turned off                                       |
| `passenger_count`    | Number of passengers (entered by driver)                                   |
| `trip_distance`      | Distance in miles                                                           |
| `PULocationID`       | TLC Taxi Zone ID for pickup                                                 |
| `DOLocationID`       | TLC Taxi Zone ID for dropoff                                                |
| `RatecodeID`         | Rate code used (e.g., JFK, Newark, etc.)                                   |
| `store_and_fwd_flag` | Whether trip was stored then forwarded (Y/N)                               |
| `payment_type`       | Payment mode (1 = Card, 2 = Cash, etc.)                                     |
| `fare_amount`        | Fare based on distance and time                                            |
| `tip_amount`         | Tip given (for card payments)                                              |
| `tolls_amount`       | Tolls charged                                                               |
| `total_amount`       | Final total amount including all surcharges                                |
| `congestion_surcharge` | Congestion fee for trips in congested areas                               |
| `airport_fee`        | Applicable for JFK/LaGuardia pickups                                       |

> Full documentation: [TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

---

## 🧪 Analysis Workflow

### 1. 📥 Data Loading

- Efficiently reads `.parquet` files using `pyarrow`
- Samples 5% of hourly data per day to maintain computational feasibility
- Merges all months into a single DataFrame

### 2. 🧹 Data Cleaning

- ✅ Fixes column naming issues (e.g., `Airport_fee`)
- 🚫 Handles negative values in key columns like `fare_amount`, `trip_distance`, etc.
- ❓ Addresses missing values (e.g., imputes or removes where necessary)
- ⚠️ Identifies and removes extreme outliers using thresholds

### 3. 📊 Exploratory Data Analysis (EDA)

- Categorizes columns into numerical, categorical, and temporal
- Performs time-based trend analysis (hourly, daily, monthly)
- Analyzes relationships between:
  - Fare and distance
  - Tip and payment type
  - Total fare and pickup time
- Generates insightful visualizations:
  - Histograms, bar charts, heatmaps, scatter plots

---

## 📈 Visual Examples

| Visualization | Description |
|---------------|-------------|
| 🕐 Histogram | Distribution of pickup hours |
| 🗓️ Bar Plot | Trip count by day of week/month |
| 📈 Scatter Plot | Fare vs. Distance |
| 🧭 Heatmap | Correlation between numerical features |

---

## 💡 Key Insights _(To Be Filled Post-Execution)_

- 📌 Total trips processed: _[x million]_
- 🚦 Peak hours: _[e.g., 6 PM – 8 PM on weekdays]_
- 💳 Most common payment: _[Credit Card with x% of trips]_
- 💰 Tip patterns: _[Higher tips on longer night trips paid via card]_
- 🗺️ Most popular zones: _[Zone A → Zone B, etc.]_

---

## 💼 Business Recommendations

1. Optimize driver deployment during peak evening hours and weekend nights.
2. Promote card payments via offers—card trips yield higher tips.
3. Improve availability in popular pickup zones based on weekday patterns.
4. Flag suspicious trips with distance < 0.5 miles and high fares.

---



