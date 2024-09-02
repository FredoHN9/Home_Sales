# Big Data Processing with SparkSQL

## Overview

This project demonstrates how to set up and use Apache Spark for analyzing big data, specifically focusing on a housing sales dataset. The code performs several data processing steps and Spark SQL queries to analyze and derive insights from the data.

## Features

1. **Environment Setup**: Install and configure Apache Spark and Java.
2. **Data Loading**: Read data from a CSV file into a Spark DataFrame.
3. **Data Analysis using Spark SQL**:
   - Average home price for four-bedroom houses sold per year.
   - Average home price for houses built in different years with specific attributes.
   - Average home price per "view" rating with filtering and ordering.
4. **Performance Comparison**: Compare query runtimes with and without caching and using Parquet format.
5. **Data Persistence**: Save data in Parquet format partitioned by a specific field.

## How It Works

### Environment Setup

1. **Install Spark and Java**: The code uses system commands to install OpenJDK and Spark.
2. **Set Environment Variables**: Environment variables are set to point to the installations of Java and Spark.

### Data Loading

1. **Read Data**: The housing sales data is read from a CSV file stored in an AWS S3 bucket into a Spark DataFrame.
2. **Display Data**: The first few rows of the DataFrame are displayed to verify the data loading.

### Data Analysis

Using Spark SQL, the following analyses are performed:

1. **Average Price for Four-Bedroom Houses**:
    - Calculate the average price for houses with four bedrooms sold per year.

2. **Average Price for Houses with Specific Attributes**:
    - Calculate the average price for houses with three bedrooms and three bathrooms built in different years.
    - Further filter these houses to include only those with two floors and living space greater than or equal to 2,000 square feet.

3. **Average Price by View Rating**:
    - Calculate the average price of a home per "view" rating for homes with an average price greater than or equal to $350,000, ordered by view rating.
    - Measure and compare the runtime of this query before and after caching the data, and using Parquet formatted data.

### Performance Comparison

1. **Caching**: Cache the DataFrame and compare query runtime before and after caching.
2. **Parquet Format**: Save the DataFrame in Parquet format, partitioned by the `date_built` field, and compare the runtime of queries on the Parquet data against the uncached and cached data.

### Data Persistence

1. **Save as Parquet**: Save the data with partitioning field to improve query performance.
2. **Read and Query Parquet Data**: Load the Parquet data and run queries to measure performance improvements.

## Usage

To use this code:
1. Ensure you have the necessary access to Google Colab or any environment where you can run shell commands for installing Java and Spark.
2. Copy the code into a Python environment that supports Spark.
3. Execute the code, ensuring you have an active internet connection to download Java, Spark, and the data file.

## Notes

- The provided data is fetched from a publicly accessible AWS S3 bucket.
- The script demonstrates the efficient use of Spark for big data processing, showcasing important practices like caching, partitioning, and using optimized data formats like Parquet.

## Results

- Comparing query runtimes reveals significant reductions in execution time when using cached data and Parquet files, demonstrating the efficacy of these optimization techniques.

## Future Enhancements

- Extend the analysis to include more complex queries and additional datasets.
- Integrate with more advanced data visualization tools to create detailed reports.
- Add more robust error handling and logging mechanisms.
