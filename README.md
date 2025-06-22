# EDA-on-NYC-Taxi-Records

Overview
This repository contains a Jupyter Notebook that performs an Exploratory Data Analysis (EDA) on the 2023 Yellow Taxi Trip Data from New York City. The primary objective of this case study is to understand why EDA is a crucial step in the data science and machine learning pipeline by uncovering insights that can help optimize taxi operations.

Problem Statement
As an analyst at an upcoming taxi operation in NYC, the task is to leverage the 2023 taxi trip data to identify patterns and trends. These insights will then inform strategic decisions aimed at improving service efficiency, maximizing revenue, and enhancing passenger experience.

Dataset
The dataset consists of yellow taxi trip records for the year 2023, collected and provided by technology providers to the NYC Taxi and Limousine Commission (TLC). The data is stored in Parquet format, with each month's data residing in a separate file.

Key features in the dataset include:

VendorID: TPEP provider code (1=Creative Mobile Technologies, LLC; 2=VeriFone Inc.).

tpep_pickup_datetime: Date and time when the meter was engaged.

tpep_dropoff_datetime: Date and time when the meter was disengaged.

passenger_count: Number of passengers (driver-entered value).

trip_distance: Elapsed trip distance in miles.

PULocationID: TLC Taxi Zone ID for pickup.

DOLocationID: TLC Taxi Zone ID for dropoff.

RatecodeID: Final rate code in effect (e.g., Standard, JFK, Newark).

store_and_fwd_flag: Indicates if the trip record was "store and forward" (Y/N).

payment_type: Numeric code for payment method (1=Credit card, 2=Cash, etc.).

fare_amount: Time-and-distance fare.

extra: Miscellaneous extras and surcharges.

mta_tax: MTA tax.

tip_amount: Tip amount (automatically populated for credit card tips).

tolls_amount: Total amount of all tolls.

improvement_surcharge: Improvement surcharge.

total_amount: Total amount charged to passengers.

congestion_surcharge: NYS congestion surcharge.

airport_fee: Airport fee (for LaGuardia and JFK pickups).

A detailed data dictionary can be found here.

Analysis Tasks
The notebook covers the following main tasks:

Data Loading:

Loading large Parquet files efficiently.

Implementing a sampling strategy (5% of hourly data per day) to handle the large dataset size and computational feasibility.

Combining sampled monthly data into a single DataFrame.

Data Cleaning:

Fixing Columns: Identifying and addressing issues like duplicate columns or incorrectly named columns (e.g., Airport_fee).

Handling Negative Values: Identifying and correcting negative values in monetary and distance-related columns.

Handling Missing Values: Analyzing the proportion of missing values in each column and imputing or dropping them as appropriate (e.g., passenger_count, RatecodeID, congestion_surcharge).

Handling Outliers: Identifying and addressing outliers in key numerical features such as trip_distance, fare_amount, and passenger_count based on predefined criteria (e.g., trip_distance near 0 with high fare_amount, payment_type 0, very high trip_distance).

Exploratory Data Analysis (EDA):

General EDA:

Categorizing variables into numerical, categorical, and temporal types.

Performing temporal analysis to understand the distribution of taxi pickups by hours of the day, days of the week, and months of the year, supported by visualizations.

Bivariate and Multivariate Analysis:

Analyzing relationships between different variables (e.g., trip distance vs. fare amount, payment type vs. tip amount).

Exploring how multiple variables interact to influence key metrics like total revenue or trip duration.

Creating Visualizations: Generating various plots (histograms, bar plots, scatter plots, heatmaps) to support the analysis and highlight key insights.

Deriving Insights and Stating Conclusions: Summarizing findings from the EDA to inform strategic recommendations for optimizing taxi operations, maximizing revenue, and enhancing passenger experience.

How to Run the Notebook
Clone the repository:

git clone <repository-url>
cd <repository-directory>

Download the data:
Obtain the 2023 NYC Yellow Taxi trip records (Parquet files) from the TLC Trip Record Data website. Place the 2023-*.parquet files in a directory named Datasets/trip_records within your project folder, or update the data_folder variable in the notebook to your data's location.

your_project_folder/
├── EDA_Assg_NYC_Taxi_Starter.ipynb
└── Datasets/
    └── trip_records/
        ├── 2023-1.parquet
        ├── 2023-2.parquet
        └── ... (all 12 monthly files)

Set up the environment:
It is recommended to use a virtual environment.

python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
pip install pandas numpy matplotlib seaborn pyarrow

(Note: pyarrow is needed to read Parquet files.)

Open and run the notebook:

jupyter notebook EDA_Assg_NYC_Taxi_Starter.ipynb

Follow the instructions in the notebook to execute the cells sequentially.

Key Insights (To be filled after running the analysis)
[Insert key findings from data loading and cleaning, e.g., total rows processed, data quality issues addressed.]

[Insert insights from temporal analysis, e.g., peak hours, busiest days/months.]

[Insert insights from bivariate/multivariate analysis, e.g., factors influencing tip amounts, relationship between trip distance and fare, patterns in payment types.]

[Summarize actionable recommendations for taxi operations.]

Visualizations
The notebook includes various plots to illustrate the data distributions and relationships. Examples include:

Histograms of pickup_hour, trip_distance, fare_amount.

Bar plots of passenger_count, RatecodeID, payment_type distributions.

Plots showing taxi activity by day of the week and month.

Scatter plots to visualize relationships between numerical variables.

Conclusion
This EDA provides a foundational understanding of the NYC Yellow Taxi trip data, highlights data quality considerations, and uncovers significant operational patterns. The insights derived can be used to inform strategic decisions for optimizing taxi services in New York City.
