# Title: Data Engineering of Timeseries IoT Data for Visualizing Taktzeit in Power BI Dashboard

## Description:
This project focuses on engineering timeseries IoT data for the visualization of Taktzeit (cycle time) in a Power BI Dashboard. The project utilizes PySpark for data processing, transformation, and aggregation to derive meaningful insights from the IoT data.

## Objective:
The main objective of this project is to preprocess and aggregate IoT data to calculate Taktzeit and visualize it in a Power BI Dashboard. Taktzeit refers to the cycle time or pace of production in manufacturing processes.

## Key Components:

### Spark Environment Setup:

* The project initializes a Spark session with configurations optimized for processing large datasets.
* PySpark libraries are imported along with necessary dependencies for working with AWS S3 and SageMaker.
### Data Ingestion:

* The project reads IoT data from a CSV file ("contour-export-22-02-2022.csv") into a Spark DataFrame using Spark's CSV reader.
### Data Transformation:

Several functions are defined for transforming the raw data:
* prozent_taktzeit: Calculates the percentage of Taktzeit for each record based on specified conditions.
* median_taktzeit: Computes the median Taktzeit for each group of records.
* half_hour_cycle_time: Segments the data into half-hour intervals and computes cycle time within each interval.
* daily_cycle_time: Segments the data into daily intervals and computes cycle time for each day.
* part_cycle_time: Calculates cycle time for each part based on process step.
### Data Aggregation:

* The transformed data is aggregated using PySpark's DataFrame operations such as groupBy, agg, and orderBy.
### Data Integration:

* The processed data from different time intervals and calculations are combined using the unionAll function and joined using the join_col function.
### Output:

The final processed data is stored in Spark DataFrames ready for further analysis or visualization in Power BI.
## GitHub Repository Structure:

* Data-Engineering-of-Timeseries-IoT-data-for-Visualising-Taktzeit-in-Power-BI-Dashboard/
* README.md: This document providing an overview of the project and instructions for usage.
* src/
** data_engineering.py: Python script containing the Spark data processing and transformation functions.
* data/
** contour-export-22-02-2022.csv: Sample input data file.
* requirements.txt: File listing all Python dependencies required to run the project.
## Usage:

* Clone the repository.
* Install the required dependencies using pip install -r requirements.txt.
* Run the data_engineering.py script to process the IoT data and generate the output.
* 
## License:

This project is licensed under the MIT License - see the LICENSE file for details.
