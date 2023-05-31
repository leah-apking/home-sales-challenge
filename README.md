# PySpark SQL

### home-sales-challenge

This challenge utilizes SparkSQL within Google Colab to determine key metrics about home sales data. SparkSQL has many tools designed to optimize query execution times when working with large datasets; for this challenge I created temporary views, partitioned the data, and cached and uncached the temporary data.

The dataset used, home_sales_revised.csv, was read into a Spark dataframe from an AWS database and used to create a temporary table. I then used SparkSQL to write and execute queries answering a variety of questions about the dataset. The final query’s runtime was recorded to later compare against the same query when using cached and partitioned data.

I then cached my temporary table and ran the same timed query using the cached data. I found that cached data returned the query 3.6 times faster than the original uncached data. I then partitioned the dataset by the “date_built” field on the formatted parquet home sales data and created a temporary table for the parquet data. By running the same timed query, but this time on the parquet data I found that while the cached data still returned the query with the shortest runtime, the cache runtime was only 1.2 times, or 19 percent faster than the parquet data. 
