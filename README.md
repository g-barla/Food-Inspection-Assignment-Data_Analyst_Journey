# 🍽️ Restaurant and Food Establishment Inspections – End-to-End Data Engineering Project

## 📝 Project Summary

This end-to-end data engineering project compares and integrates restaurant inspection data from Chicago and Dallas, focusing on creating a clean, consistent, and analytics-ready dataset. The project leveraged modern data tools like Azure Data Factory, SQL, and Alteryx to build a robust ETL workflow and prepare the data for advanced reporting.

## 🎯 Objective

The goal of this project was to:
✅ Clean raw inspection data for both cities
✅ Handle missing and duplicate values 
✅ Apply data standardization and transformation logic
✅ Generate a dimensional DimLocation table with surrogate keys
✅ Enable insights with the help of Power BI dashboards

## 🧰  Tools & Technologies Used

| Tool               | Purpose                                   | 
|--------------------|-------------------------------------------|
| Azure Data Factory | Applied data cleaning and logic           |
| Snowflake          | Data source and sink management           |
| Power BI           | Dashboard creation and data visualization |
| YData Profiler     | Profiling theh dataset                    |


## 📂 Dataset Summary

|Dataset          | Records      | Format | 
|-----------------|--------------|--------|
|Chicago Dataset  | ~130,000     | .csv   |
|Dallas Dataset   | ~70,000      | .csv   |

Variables included:
- Establishment Name
- Inspection Type and Result
- Address, Zip Code
- Latitude & Longitudes
- 	License ID , Risk Level

## 🧼 Data Cleaning – Alteryx Logic
	-	Filtered out records missing restaurant names
	-	Applied REGEX_Replace to remove non-alphabetic characters
	-	Removed rows with numerical-only names (invalid)
	-	Generated RowID for tracking and unique reference
	-	Ensured consistent formatting for zip codes and geolocation

## 🔄 Data Pipeline Architecture

🔷 Azure Data Factory – ETL Flow
	-	Read: Ingested Chicago and Dallas datasets from staging.
	- Transform: Used Select and DerivedColumn to unify formats.
	-	Union: Merged both city datasets for modeling.
	-	Join: Connected with DimLocationMaxId for surrogate key logic.
	-	Aggregate: Removed redundancy using address-level grouping.
	-	Sink: Loaded clean data into ds_DimLocation SQL table.

 ## 🧪 Data Profiling Report – YData Summary

|Metric        | Value              |
|--------------|--------------------|
|Total Records |130,462             |
|Duplicate Rows| 57,297 (43.9%)     |
|Missing Cells | 42,742 (1.9%)      |
|Variable Count| 17                 |

The profiling report allowed us to prioritize cleaning steps and remove low-quality records, especially from the Chicago dataset.

## 📈 Visualizations

Using Power BI, we developed a dashboard to analyze key metrics from the cleaned dataset.

|Dashboard             | Insight                                               |
|----------------------|-------------------------------------------------------|
| Inspection Heatmap   |High-risk areas by latitude and longitude              |
| Outcome Pie Chart    | Distribution of pass vs fail by city                  |
| Inspection Timeline  | Monthly and yearly inspection trends                  |
|Violation Type Summary| Frequent infractions grouped by violation categories  |


## ✅ Key Takeaways
	-	Learned to implement scalable pipelines in Azure Data Factory
	-	Practiced real-world data cleaning with Alteryx & Regex
	-	Applied data profiling for smart decision-making
	-	Built an end-to-end ETL system feeding a robust Dimensional Model
	-	Visualized geographic and temporal trends using Power BI

 
## 👥 Team Members
	-👤 Je Sai Kailash Pulipati
	-👤 Deepthi Ramesh
	-👤 Geetika Barla


