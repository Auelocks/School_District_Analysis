# School_District_Analysis

## Overview

This study will aggregate data from local schools and students (including budgets and students’ standardized test scores) and provide insights about performance trends and patterns to influence school board goals and budgetary decisions.  Combined data is summarized using tables, also known as DataFrames in the script written for this project.  

## Resources
The software used to generate the scripts included Python 3.7.10 with Jupyter Notebook 6.3.0 and scripts are provided as *.ipynb files.  The district provided raw CSV files “schools_complete.csv” and “students_complete.csv” which are referenced in the Python script and stored in the provided Resources folder.

## Results

Early review of the student data revealed some erroneous titles for the high school students (pre-fix and suffixes such as “Mrs.” or “Dr.”) which were accounted for and removed in the script.  There was also some suspected academic dishonesty in ninth grade standardized test scores for Thomas High School (THS), so math and reading test scores for this group were replaced with null values “NaN” while keeping the rest of the data intact.  The total count of ninth grade students at THS was found to be 461 out of the total student count of 39,170 so it was expected that removing the test data in question would not have a significant impact on district wide summaries.  In the following sections, “original” data refers to the combined data including THS 9th grade test scores while the “adjusted” data refers to the combined data where the test scores in question were replaced with null values.

### District Summary

A District Summary was generated to condense school and student data into a district wide count of schools, students, and total budget as well as tabulate average student test score data. The following image includes the District Summary table for the original data as well as the adjusted data District Summary table.

![DistrictSum_combined](/Images/ DistrictSum_combined.png)

Comparing the original vs. adjusted values confirms that voiding the 9th grade data from THS had almost no impact on district wide test score averages and the average percentage of the student population passing.  For example, the largest impact was seen in the % Overall Passing which only increased by three tenths of a percent.

### School Summary

A complete school summary was generated as a high-level snapshot of each school based on the district's defined metrics.  The following table represents the district wide School Summary (including THS adjusted values), indexed by school name, detailing the total student count, budget, a calculated per student budget, testing score averages and percentages, as well as the calculated Spending Ranges per student.
 
![SchoolSum](/Images/SchoolSum.png)

Because the 9th grade test scores were removed from Thomas High School, the following side-by-side comparison is included for the THS School Summary Data, original values vs. adjusted values. 
![SchoolSum-THS Summary](/Images/SchoolSum-THS Summary.png)

From this comparison it is clear that removing the 9th grade data had little impact on the school’s averages. There were 461 student’s test scores identified and removed in a school of 1635 students, or a little more than 28% of the student body. This suggests there was not wide variability in the testing averages and percent passing among the 9th grade class vs. the 10th, 11th, and 12th grades at THS.

### High and Low Performing Schools

Budget allocation in a district is often determined by school performance.  The School Summary was filtered based on the calculated % Overall Passing where the district’s “high-performing” schools are selected as the top five schools with the highest overall percentage of passing students.  These are:

![SchoolSum_TopPerformers](/Images/SchoolSum_TopPerformers.png)

Low performing schools are selected as the five schools with the lowest overall percentage of passing students.  These are:

![SchoolSum_LowPerformers](/Images/SchoolSum_LowPerformers.png)


### Math and Reading Scores by Grade

Summary tables of math and reading scores by grade were also generated to visualize and determine areas for improvement by grade.



### Scores by School Spending

Testing averages and percentage of passing scores were grouped and collected into DataFrames by arbitrarily determining spending ranges so that an equal number of schools can be divided and spending ranges assigned to classify how spending per student could affect score averages and passing rates.

### Scores by School Size
Average math and reading scores, the average percentage of students who passed math and reading, and the average overall percentage were grouped and listed based on school size.  There were three main categories for size including “Small” being less than 1000 students, “Medium” included the 1000 to 2000 student range, and “Large” was defined as between 2000 and 5000 students.


###Scores by School Type

Testing averages and percentages of students passing were grouped by school types “Charter” vs. “District” to identify any trends between school type and student performance to show how school size affects score averages and passing rates.

### Summary

After adjusting the values in the District Summary Table removing the THS ninth grade test scores did not have much of an impact on the District Summary.
