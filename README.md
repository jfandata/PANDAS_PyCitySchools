# PyCitySchools
This project is part of the Data Analytics and Visualization Certification at Washington University in St. Louis.  Other projects can be found at the [main GitHub repo](https://github.com/jfandata).

#### -- Project Status: [Completed]

## Project Intro/Objective
The purpose of this project is to analyze district-wide standardized test results. Data is aggregated to show trends in school performance. The school board will be using these results to make strategic decisions regarding future school budgets and priorities. 

### Methods Used
* Data manipulation with data frames
* Array calculations

### Technologies
* Python
* Pandas
* NumPy
* Jupyter Notebook 

## Project Description
This project uses the Pandas library to manipulate data into tables that allow for aggregating and summarizing of district and school data. Array calculations are performed to create a snapshot of school district's key metrics. Analysis done to show trends such as top peforming schools, bottom performing schools, math and reading scores by grade, and scores by school spending, size, and school type. 

## Needs of this Project

- data exploration/descriptive statistics
- data processing/cleaning
- statistical modeling

## Contents of Project Repository

1. School and student raw data is being kept [here](https://github.com/jfandata/PANDAS_PyCitySchools/tree/master/Resources) within this repo.

2. Data processing/transformation scripts and results done in jupyter notebook are being kept [here](https://github.com/jfandata/PANDAS_PyCitySchools/blob/master/PyCitySchools_starter.ipynb)

## Key Takeaways

1. Import dependencies.

```python
import pandas as pd
import numpy as np
```

2. Load and read data from csv.

```python
# Load data
school_data_to_load = "Resources/schools_complete.csv"
student_data_to_load = "Resources/students_complete.csv"
# Read data
school_data = pd.read_csv(school_data_to_load)
student_data = pd.read_csv(student_data_to_load)
```