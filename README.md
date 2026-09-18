GROUP PROJECT PLANNING SHEET

Class: XI RPL 3
Friday, September 18, 2026

Group Members’ Names:
Noach Zefanya Rifian/23
Mevlana Ravi Atmajati/13

Selected Dataset: Student Academic Grade Data 

Initial Analysis Questions:
What is the average student grade per subject?
How do student grades compare across classes?
What percentage of students meet the minimum passing grade?

Suspected Data Quality Issues 
Missing values in columns: 8 (grade and teacher columns)
Duplicate data: 4
Inconsistent data type in column: Grade (string type)
Other: inconsistent capitalization in the exam type column; date column does not follow the correct date format

Data Cleaning Plan: 
Duplicates: Remove exact duplicates using `df.drop_duplicates()`.
String Standardization & Outliers: Remove the text ‘ points’, change the decimal comma ‘,’ to ‘.’. The value 999 (input typo) is changed to NaN so it does not skew statistical calculations.
Data Type Conversion: Convert the “nilai” column to numeric (float).
Missing Values: Fill in missing values with the median or mean score per subject, or remove rows without exam scores if deemed invalid (dropna). Empty entries in the “guru_pengampu” column are filled with “Not Recorded.”
Category Standardization: Standardize the `jenis_ujian` column to uppercase (str.upper()).

Data Manipulation Plan
Filter: Filter students whose scores are below the passing score (75) for the remedial program
Sort: Sort scores from highest to lowest
Derived column: Create a graduation status column; “Pass” if >75, “Remedial” for the rest
Group by/Aggregation: Group data by subject and class to calculate the average, lowest score, and highest score.

Work Schedule
P3 (Loading & Inspection): Load CSV into a DataFrame; check .info(), .head(), .describe(), and identify data anomalies
P4 (Cleaning): Handle duplicates, clean numeric strings, impute missing values, and correct data types.
P5 (Manipulation): Create a derived column for KKM status, filter out students in remedial classes, and aggregate class/subject performance.
P6 (Testing & Presentation): Export dataset_bersih.csv, interpret findings narratively, and prepare presentation slides.

Role Assignment:
Member 1: Responsible for Data Manipulation (filtering, sorting, creating a graduation status column, groupby) and compiling the Data Profiling Summary.
Member 2: Responsible for Data Loading, Data Inspection, and Data Cleaning (handling missing values, duplicates, and data types).
