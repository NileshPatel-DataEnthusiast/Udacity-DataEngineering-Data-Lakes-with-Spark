# Project: Data Lake
 
A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake.  
The analytics team are interested in finding insights in what songs their users are listening to.
Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.
 
## Introduction

To assist the analytics team, an ETL pipline will need to be built that extracts their data from S3, processes them using Spark, 
and loads the data back into S3 as a set of dimensional tables for the analytics team to easily query.  

## Project Files

The project workspace includes three files:

1. dl.cfg  - config file that stores AWS credentials and filepaths for data on S3.
2. etl.py  - reads data from S3, processes that data using Spark, and writes them back to S3. 
3. README.md - This file provides discussion on the project.

## Data Sets

There are 2 datasets that need to be loaded and processed to be used for analysis:

1. Song Dataset
   The first dataset is a subset of real data from the Million Song Dataset. 
   Each file is in JSON format and contains metadata about a song and the artist of that song. 
2. Log Dataset
   The second dataset consists of log files in JSON format generated by the event simulator based on the 
   songs in the dataset above. These simulate activity logs from a music streaming app based on specified 
   configurations.

## Usage

These are the instructions to load the data from S3, process it using Spark and write the data back to S3:
 
1. Create an AWS S3 bucket and create a folder called "output_data" in the bucket.

2. Launch an AWS EMR cluster.

3. Update dwh.cfg file with AWS Access Key and Secret Access Key as well as the name of the S3 bucket created in Step 2. 

4. Run etl.py in a Python Terminal to load data from S3 into the AWS EMR cluster for Spark to process the data and write the data back to S3. 

```bash
python3 etl.py
```
