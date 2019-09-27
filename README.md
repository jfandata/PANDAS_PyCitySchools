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

3. Combine the data into a single dataset.

```python
school_data_complete = pd.merge(student_data, school_data, how="left", on=["school_name", "school_name"])
```

4. Ways of summarizing the data.

```python
# counting the number of schools, with .unique() because names of schools occurs more than once.
school_names = school_data_complete["school_name"].unique()
total_schools =len(school_names)
# counting the number of students, with .count() because each student should be unique
total_students = school_data_complete["student_name"].count()
# filtering data: calculate the percentage of students with a passing math score (70 or greater)
passing_math=school_data_complete.loc[school_data_complete["math_score"] >= 70]["math_score"].count()
# group by schools
school_names = school_data_complete.set_index("school_name").groupby(["school_name"])
# sort and display top 5
top_5 = summary_by_school.sort_values("Overall Passing Rate", ascending = False)
```

5. Create a table that lists the average Reading Score for each grade at each school.

```python
#Create a table that lists the average Reading Score for students of each grade level (9th, 10th, 11th, 12th) at each school.
#Create a pandas series for each grade, using a conditional statement.
#Group each series by school
ninth = student_data.loc[student_data["grade"] == "9th"].groupby("school_name")["math_score"].mean()
tenth = student_data.loc[student_data["grade"] == "10th"].groupby("school_name")["math_score"].mean()
eleventh = student_data.loc[student_data["grade"] == "11th"].groupby("school_name")["math_score"].mean()
twelfth = student_data.loc[student_data["grade"] == "12th"].groupby("school_name")["math_score"].mean()
#Combine the series into a dataframe
math_scores = pd.DataFrame({
        "9th": ninth,
        "10th": tenth,
        "11th": eleventh,
        "12th": twelfth
})
```