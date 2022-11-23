# Sagemaker Exploration
## Exploring PySpark and PyDeequ with Amazon SageMaker 

[Amazon SageMaker](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html) is a fully managed machine learning service. With SageMaker, data scientists and developers can quickly and easily build and train machine learning models, and then directly deploy them into a production-ready hosted environment.

We are using SageMaker compute instances running [Jupyter Notebooks](https://jupyter.org) not only for analytical coding, but also for building services with AWS resources using the AWS Python SDK (boto3).

PyDeequ is a Python API for Deequ, a library built on top of Apache Spark for defining "unit tests for data", which measure data quality in large datasets. PyDeequ is written to support usage of Deequ in Python.   We are looking to leverage PyDeequ for analyzing and improving Data Quality.

## Contents
[**PySparkShakeout.DAAB-LAB.ipynb**](PySparkShakeout.DAAB-LAB.ipynb) -- All Jupyter Notebook operations behave as expected.<br/>
[**PySparkShakeout.WC2H-DDMAP.ipynb**](PySparkShakeout.WC2H-DDMAP.ipynb) -- Jupyter Notebook operations work for local files, AWS CLI, and AWS SDK.  But PySpark is unable to read S3 objects <br/>
[**data**](data) -- CSV and Parquet sample data files (from FiscalData) <br/>

## Summary of Results
|Para|Operation|DAAB-LAB|WC2H-DDMAP|				
|:-:|---|:-:|:-:|				
|[4]|# Read a CSV file from local instance directory into a Spark dataframe|Works|Works|				
|[5]|# Write a copy of the Spark dataframe to a Parquet output file|Works|Works|				
|[5]|# Read a Parquet file from local instance directory|Works|Works|				
|[6]|# copy local CSV file to S3 using AWS CLI|Works|Works|				
|[7]|# Read the CSV file from S3 using Python AWS SDK|Works|Works|				
|[8]|# Read the CSV file from S3 into a Spark data frame|Works|Fails|				
|[9]|# Use AWS CLI to list objects in publicly-accessible S3 parquet data set (AWS US East Region)|Works|Fails|				
|[10]|# Read a publicly-accessible S3 parquet data set into a Spark dataframe (AWS US East Region)|Works|Fails|				


## References

[Test data quality at scale with Deequ](https://aws.amazon.com/blogs/big-data/test-data-quality-at-scale-with-deequ/)

[Test data quality at scale with PyDeequ](https://aws.amazon.com/blogs/big-data/testing-data-quality-at-scale-with-pydeequ/) 

[https://github.com/awslabs/python-deequ](https://github.com/awslabs/python-deequ)

