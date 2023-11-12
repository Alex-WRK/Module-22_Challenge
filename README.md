# Home_Sales

## Project Overview

In this project, I utilized Spark, within a Databricks environment to perform a comprehensive analysis of a real estate dataset. The dataset, named `home_sales_revised.csv`, was sourced from an AWS S3 bucket and contains various attributes of home sales.

## Key Steps and Findings

### 1. Data Loading and DataFrame Creation
- The data was successfully loaded into a Spark DataFrame from the provided CSV file. This process involved setting up the Databricks environment to read the CSV and ensure proper schema inference and header recognition.

### 2. Temporary Table Creation
- A temporary view, `home_sales_view`, was created from the DataFrame. This allowed me to use Spark SQL for subsequent data querying, providing both flexibility and efficiency in handling SQL-like queries.

### 3. Data Analysis Queries
- I conducted several analyses to extract insights from the data. These included:
  - Calculating the average price of four-bedroom houses sold each year.
  - Determining the average price of homes with three bedrooms and three bathrooms for each construction year.
  - Analyzing the average price of homes with specific features (three bedrooms, three bathrooms, two floors, and a minimum of 2,000 square feet) for each year built.
  - Evaluating the "view" rating for the average price of homes priced at or above $350,000.

### 4. Performance Optimization Using Caching
- The `home_sales_view` was cached to optimize the performance of the queries. Caching proved to be effective in reducing the runtime of data processing, particularly for the complex aggregations and filters applied in the analysis queries.

### 5. Data Partitioning and Parquet Formatting
- I partitioned the data by the "date_built" field and saved it in Parquet format. This step was crucial for optimizing query performance, especially for larger datasets, as Parquet is efficient for columnar storage and works well with partitioning.

### 6. Runtime Analysis
- The runtime for queries on the cached data versus the Parquet formatted data was recorded and compared. This comparison provided valuable insights into the performance benefits of caching and Parquet formatting in Spark.

### 7. Resource Management
- Post-analysis, I made sure to uncache the `home_sales_view` to free up memory resources. This practice is essential in resource management, especially in a shared Spark environment.

## Conclusion and Insights

This project highlighted the power of Apache Spark in handling and analyzing big data. Through caching and partitioning, significant improvements in query performance were observed. The analysis provided deep insights into the housing market trends, particularly in relation to property features and pricing. Leveraging Spark SQL for these analyses proved to be both efficient and effective, demonstrating Spark's capability in processing large-scale data with complex queries.


###### Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
