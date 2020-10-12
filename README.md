# Py-City Schools
![](/Images/education.png)

## PyCity Schools Analysis

- As a whole, schools with higher budgets, did not yield better test results. By contrast, schools with higher spending per student actually ($645- $675) underperformed compared to schools with smaller budgets ($585 per student).
- As a whole, smaller and medium sized schools dramatically out-performed large sized schools on passing math performances (89-91% passing vs 67%).
- As a whole, charter schools out-performed the public district schools across all metrics. However, more analysis will be required to glean if the effect is due to school practices or the fact that charter schools tend to serve smaller student populations per school.

### Dependencies and Starter Code

```
# Dependencies and Setup
import pandas as pd
import numpy as np

# File to Load (Remember to Change These)
school_data_to_load = "Resources/schools_complete.csv"
student_data_to_load = "Resources/students_complete.csv"

# Read School and Student Data File and store into Pandas DataFrames
school_data = pd.read_csv(school_data_to_load)
student_data = pd.read_csv(student_data_to_load)

# Combine the data into a single dataset.  
school_data_complete = pd.merge(student_data, school_data, how="left", on=["school_name", "school_name"])
```



### Check School Data types:

```
school_data_complete.info()
<class 'pandas.core.frame.DataFrame'>
Int64Index: 39170 entries, 0 to 39169
Data columns (total 11 columns):
 #   Column         Non-Null Count  Dtype 
---  ------         --------------  ----- 
 0   Student ID     39170 non-null  int64 
 1   student_name   39170 non-null  object
 2   gender         39170 non-null  object
 3   grade          39170 non-null  object
 4   school_name    39170 non-null  object
 5   reading_score  39170 non-null  int64 
 6   math_score     39170 non-null  int64 
 7   School ID      39170 non-null  int64 
 8   type           39170 non-null  object
 9   size           39170 non-null  int64 
 10  budget         39170 non-null  int64 
dtypes: int64(6), object(5)
memory usage: 3.6+ MB
```

### Displaying merged Data-Frame:

|      | Student ID |      student_name | gender | grade |       school_name | reading_score | math_score | School ID |     type | size |  budget |
| ---: | ---------: | ----------------: | -----: | ----: | ----------------: | ------------: | ---------: | --------: | -------: | ---: | ------: |
|    0 |          0 |      Paul Bradley |      M |   9th | Huang High School |            66 |         79 |         0 | District | 2917 | 1910635 |
|    1 |          1 |      Victor Smith |      M |  12th | Huang High School |            94 |         61 |         0 | District | 2917 | 1910635 |
|    2 |          2 |   Kevin Rodriguez |      M |  12th | Huang High School |            90 |         60 |         0 | District | 2917 | 1910635 |
|    3 |          3 | Dr. Richard Scott |      M |  12th | Huang High School |            67 |         58 |         0 | District | 2917 | 1910635 |
|    4 |          4 |        Bonnie Ray |      F |   9th | Huang High School |            97 |         84 |         0 | District | 2917 | 1910635 |



# District Summary

- Calculate the total number of schools
- Calculate the total number of students
- Calculate the total budget
- Calculate the average math score
- Calculate the average reading score
- Calculate the percentage of students with a passing math score (70 or greater)
- Calculate the percentage of students with a passing reading score (70 or greater)
- Calculate the percentage of students who passed math **and** reading (% Overall Passing)
- Create a dataframe to hold the above results
- Optional: give the displayed data cleaner formatting

### Calculation for District Summary (Totals, Averages, Percentages)

|      | Total Schools | Total Students | Total Budget | Average Math Score | Average Reading Score | Passing Math | Passing Reading | Overall Passing |
| ---: | ------------: | -------------: | -----------: | -----------------: | --------------------: | -----------: | --------------: | --------------: |
|    0 |            15 |         39,170 |  $24,649,428 |              78.99 |                 81.88 |      74.98 % |         85.81 % |         65.17 % |



# School Summary

- Create an overview table that summarizes key metrics about each school, including:
  - School Name
  - School Type
  - Total Students
  - Total School Budget
  - Per Student Budget
  - Average Math Score
  - Average Reading Score
  - % Passing Math
  - % Passing Reading
  - % Overall Passing (The percentage of students that passed math **and** reading.)
- Create a dataframe to hold the above results



### Creating an overview table that summarizes key metrics about Each School

|                       | School Type | Total Students | Total School Budget | Per Student Budget | Avg Math Score | Avg Reading Score | Passing Math % | Passing Reading % | Overall Passing % |
| --------------------: | ----------: | -------------: | ------------------: | -----------------: | -------------: | ----------------: | -------------: | ----------------: | ----------------: |
|    Bailey High School |    District |           4976 |          $3,124,928 |            $628.00 |          77.05 |             81.03 |        66.68 % |           81.93 % |           54.64 % |
|   Cabrera High School |     Charter |           1858 |          $1,081,356 |            $582.00 |          83.06 |             83.98 |        94.13 % |           97.04 % |           91.33 % |
|  Figueroa High School |    District |           2949 |          $1,884,411 |            $639.00 |          76.71 |             81.16 |        65.99 % |           80.74 % |           53.20 % |
|      Ford High School |    District |           2739 |          $1,763,916 |            $644.00 |          77.10 |             80.75 |        68.31 % |           79.30 % |           54.29 % |
|   Griffin High School |     Charter |           1468 |            $917,500 |            $625.00 |          83.35 |             83.82 |        93.39 % |           97.14 % |           90.60 % |
| Hernandez High School |    District |           4635 |          $3,022,020 |            $652.00 |          77.29 |             80.93 |        66.75 % |           80.86 % |           53.53 % |
|    Holden High School |     Charter |            427 |            $248,087 |            $581.00 |          83.80 |             83.81 |        92.51 % |           96.25 % |           89.23 % |
|     Huang High School |    District |           2917 |          $1,910,635 |            $655.00 |          76.63 |             81.18 |        65.68 % |           81.32 % |           53.51 % |
|   Johnson High School |    District |           4761 |          $3,094,650 |            $650.00 |          77.07 |             80.97 |        66.06 % |           81.22 % |           53.54 % |
|      Pena High School |     Charter |            962 |            $585,858 |            $609.00 |          83.84 |             84.04 |        94.59 % |           95.95 % |           90.54 % |
| Rodriguez High School |    District |           3999 |          $2,547,363 |            $637.00 |          76.84 |             80.74 |        66.37 % |           80.22 % |           52.99 % |
|   Shelton High School |     Charter |           1761 |          $1,056,600 |            $600.00 |          83.36 |             83.73 |        93.87 % |           95.85 % |           89.89 % |
|    Thomas High School |     Charter |           1635 |          $1,043,130 |            $638.00 |          83.42 |             83.85 |        93.27 % |           97.31 % |           90.95 % |
|    Wilson High School |     Charter |           2283 |          $1,319,574 |            $578.00 |          83.27 |             83.99 |        93.87 % |           96.54 % |           90.58 % |
|    Wright High School |     Charter |           1800 |          $1,049,400 |            $583.00 |          83.68 |             83.95 |        93.33 % |           96.61 % |           90.33 % |



## Top Performing Schools (By % Overall Passing)

- Sort and display the top five performing schools by % overall passing.

|                     | School Type | Total Students | Total School Budget | Per Student Budget | Avg Math Score | Avg Reading Score | Passing Math % | Passing Reading % | Overall Passing % |
| ------------------: | ----------: | -------------: | ------------------: | -----------------: | -------------: | ----------------: | -------------: | ----------------: | ----------------: |
| Cabrera High School |     Charter |           1858 |             1081356 |              582.0 |      83.061895 |         83.975780 |      94.133477 |         97.039828 |         91.334769 |
|  Thomas High School |     Charter |           1635 |             1043130 |              638.0 |      83.418349 |         83.848930 |      93.272171 |         97.308869 |         90.948012 |
| Griffin High School |     Charter |           1468 |              917500 |              625.0 |      83.351499 |         83.816757 |      93.392371 |         97.138965 |         90.599455 |
|  Wilson High School |     Charter |           2283 |             1319574 |              578.0 |      83.274201 |         83.989488 |      93.867718 |         96.539641 |         90.582567 |
|    Pena High School |     Charter |            962 |              585858 |              609.0 |      83.839917 |         84.044699 |      94.594595 |         95.945946 |         90.540541 |



## Bottom Performing Schools (By % Overall Passing)

- Sort and display the five worst-performing schools by % overall passing.

|                       | School Type | Total Students | Total School Budget | Per Student Budget | Avg Math Score | Avg Reading Score | Passing Math % | Passing Reading % | Overall Passing % |
| --------------------: | ----------: | -------------: | ------------------: | -----------------: | -------------: | ----------------: | -------------: | ----------------: | ----------------: |
| Rodriguez High School |    District |           3999 |             2547363 |              637.0 |      76.842711 |         80.744686 |      66.366592 |         80.220055 |         52.988247 |
|  Figueroa High School |    District |           2949 |             1884411 |              639.0 |      76.711767 |         81.158020 |      65.988471 |         80.739234 |         53.204476 |
|     Huang High School |    District |           2917 |             1910635 |              655.0 |      76.629414 |         81.182722 |      65.683922 |         81.316421 |         53.513884 |
| Hernandez High School |    District |           4635 |             3022020 |              652.0 |      77.289752 |         80.934412 |      66.752967 |         80.862999 |         53.527508 |
|   Johnson High School |    District |           4761 |             3094650 |              650.0 |      77.072464 |         80.966394 |      66.057551 |         81.222432 |         53.539172 |



## Math Scores by Grade

- Create a table that lists the average Math Score for students of each grade level (9th, 10th, 11th, 12th) at each school.
- Create a pandas series for each grade. Hint: use a conditional statement.
- Group each series by school
- Combine the series into a dataframe
- Optional: give the displayed data cleaner formatting

|                       | 9th Grade Avg Math Scores | 10th Grade Avg Math Scores | 11th Grade Avg Math Scores | 12th Grade Avg Math Scores |
| --------------------: | ------------------------: | -------------------------: | -------------------------: | -------------------------: |
|    Bailey High School |                 77.083676 |                  76.996772 |                  77.515588 |                  76.492218 |
|   Cabrera High School |                 83.094697 |                  83.154506 |                  82.765560 |                  83.277487 |
|  Figueroa High School |                 76.403037 |                  76.539974 |                  76.884344 |                  77.151369 |
|      Ford High School |                 77.361345 |                  77.672316 |                  76.918058 |                  76.179963 |
|   Griffin High School |                 82.044010 |                  84.229064 |                  83.842105 |                  83.356164 |
| Hernandez High School |                 77.438495 |                  77.337408 |                  77.136029 |                  77.186567 |
|    Holden High School |                 83.787402 |                  83.429825 |                  85.000000 |                  82.855422 |
|     Huang High School |                 77.027251 |                  75.908735 |                  76.446602 |                  77.225641 |
|   Johnson High School |                 77.187857 |                  76.691117 |                  77.491653 |                  76.863248 |
|      Pena High School |                 83.625455 |                  83.372000 |                  84.328125 |                  84.121547 |
| Rodriguez High School |                 76.859966 |                  76.612500 |                  76.395626 |                  77.690748 |
|   Shelton High School |                 83.420755 |                  82.917411 |                  83.383495 |                  83.778976 |
|    Thomas High School |                 83.590022 |                  83.087886 |                  83.498795 |                  83.497041 |
|    Wilson High School |                 83.085578 |                  83.724422 |                  83.195326 |                  83.035794 |
|    Wright High School |                 83.264706 |                  84.010288 |                  83.836782 |                  83.644986 |



## Reading Score by Grade

- Create a table that lists the average Reading Score for students of each grade level (9th, 10th, 11th, 12th) at each school.
- Create a pandas series for each grade.
- Group each series by school
- Combine the series into a dataframe
- Optional: give the displayed data cleaner formatting

|                       | 9th Grade Avg Reading Scores | 10th Grade Avg Reading Scores | 11th Grade Avg Reading Scores | 12th Grade Avg Reading Scores |
| --------------------: | ---------------------------: | ----------------------------: | ----------------------------: | ----------------------------: |
|    Bailey High School |                    81.303155 |                     80.907183 |                     80.945643 |                     80.912451 |
|   Cabrera High School |                    83.676136 |                     84.253219 |                     83.788382 |                     84.287958 |
|  Figueroa High School |                    81.198598 |                     81.408912 |                     80.640339 |                     81.384863 |
|      Ford High School |                    80.632653 |                     81.262712 |                     80.403642 |                     80.662338 |
|   Griffin High School |                    83.369193 |                     83.706897 |                     84.288089 |                     84.013699 |
| Hernandez High School |                    80.866860 |                     80.660147 |                     81.396140 |                     80.857143 |
|    Holden High School |                    83.677165 |                     83.324561 |                     83.815534 |                     84.698795 |
|     Huang High School |                    81.290284 |                     81.512386 |                     81.417476 |                     80.305983 |
|   Johnson High School |                    81.260714 |                     80.773431 |                     80.616027 |                     81.227564 |
|      Pena High School |                    83.807273 |                     83.612000 |                     84.335938 |                     84.591160 |
| Rodriguez High School |                    80.993127 |                     80.629808 |                     80.864811 |                     80.376426 |
|   Shelton High School |                    84.122642 |                     83.441964 |                     84.373786 |                     82.781671 |
|    Thomas High School |                    83.728850 |                     84.254157 |                     83.585542 |                     83.831361 |
|    Wilson High School |                    83.939778 |                     84.021452 |                     83.764608 |                     84.317673 |
|    Wright High School |                    83.833333 |                     83.812757 |                     84.156322 |                     84.073171 |

## Scores by School Spending

- Create a table that breaks down school performances based on average Spending Ranges (Per Student). Use 4 reasonable bins to group school spending. Include in the table each of the following:
  - Average Math Score
  - Average Reading Score
  - % Passing Math
  - % Passing Reading
  - Overall Passing Rate (Average of the above two)



### Figure out the Min and Max budget

```
578.0
655.0
```

|                               | Avg Math Score | Avg Reading Score | Passing Math % | Passing Reading % | Overall Passing % |
| ----------------------------: | -------------: | ----------------: | -------------: | ----------------: | ----------------: |
| Spending Ranges (Per Student) |                |                   |                |                   |                   |
|                         <$585 |      83.455399 |         83.933814 |        93.46 % |           96.61 % |           90.37 % |
|                      $585-615 |      83.599686 |         83.885211 |        94.23 % |           95.90 % |           90.22 % |
|                      $615-645 |      79.079225 |         81.891436 |        75.67 % |           86.11 % |           66.11 % |
|                      $645-675 |      76.997210 |         81.027843 |        66.16 % |           81.13 % |           53.53 % |



## Scores by School Size

- Create a table that breaks down school performances based on School Size. Use 4 reasonable bins to group school size.
- Include in the table each of the following:
  - Average Math Score
  - Average Reading Score
  - % Passing Math
  - % Passing Reading
  - Overall Passing Rate (Average of the above two)

|                    | Avg Math Score | Avg Reading Score | Passing Math % | Passing Reading % | Overall Passing % |
| -----------------: | -------------: | ----------------: | -------------: | ----------------: | ----------------: |
|        School Size |                |                   |                |                   |                   |
|      Small (<1000) |      83.821598 |         83.929843 |        93.55 % |           96.10 % |           89.88 % |
| Medium (1000-2000) |      83.374684 |         83.864438 |        93.60 % |           96.79 % |           90.62 % |
|  Large (2000-5000) |      77.746417 |         81.344493 |        69.96 % |           82.77 % |           58.29 % |

## Scores by School Type

- Create a table that breaks down school performances based on School Type
- Include in the table each of the following:
  - Average Math Score
  - Average Reading Score
  - % Passing Math
  - % Passing Reading
  - Overall Passing Rate (Average of the above two)

|             | Avg Math Score | Avg Reading Score | Passing Math % | Passing Reading % | Overall Passing % |
| ----------: | -------------: | ----------------: | -------------: | ----------------: | ----------------: |
| School Type |                |                   |                |                   |                   |
|     Charter |      83.473852 |         83.896421 |        93.62 % |           96.59 % |           90.43 % |
|    District |      76.956733 |         80.966636 |        66.55 % |           80.80 % |           53.67 % |
