# School_District_Analysis

## Overview

This study will aggregate data from local schools and students (including budgets and students’ standardized test scores) and provide insights about performance trends and patterns to influence school board goals and budgetary decisions.  Combined data is summarized using tables, also known as DataFrames in the script written for this project.  

## Resources

The software used to generate the scripts included Python 3.7.10 with Jupyter Notebook 6.3.0 and scripts are provided as .ipynb files.  The district provided raw CSV files “schools_complete.csv” and “students_complete.csv” which are referenced in the Python script and stored in the provided Resources folder.

## Results

Early review of the student data revealed some erroneous titles for the high school students (pre-fix and suffixes such as “Mrs.” or “Dr.”) which were accounted for and removed in the script.  There was also some suspected academic dishonesty in ninth grade standardized test scores for Thomas High School (THS), so math and reading test scores for this group were replaced with null values “NaN” while keeping the rest of the data intact.  The total count of ninth grade students at THS was found to be 461 out of the total student count of 39,170 so it was expected that removing the test data in question would not have a significant impact on district wide summaries.  In the following sections, “original” data refers to the combined data including THS 9th grade test scores while the “adjusted” data refers to the combined data where the test scores in question were replaced with null values.

### District Summary

A District Summary was generated to condense school and student data into a district wide count of schools, students, and total budget as well as tabulate average student test score data. The following image includes the District Summary table for the original data as well as the adjusted data District Summary table.

![DistrictSum_combined](/Images/DistrictSum_combined.PNG)

Comparing the original vs. adjusted values confirms that voiding the 9th grade data from THS had almost no impact on district wide test score averages and the average percentage of the student population passing.  For example, the largest impact was seen in the % Overall Passing which only increased by three tenths of a percent in the adjusted District Summary.

### School Summary

A complete school summary was generated as a high-level snapshot of each school based on the district's defined metrics.  The following table represents the district wide School Summary (including THS adjusted values), indexed by school name, detailing the total student count, budget, a calculated per student budget, testing score averages and percentages, as well as the calculated Spending Ranges per student.
 
![SchoolSum](School_District_Analysis/Images/SchoolSum.png)

Because the 9th grade test scores were removed from Thomas High School, the following side-by-side comparison is included for the THS School Summary Data, original values vs. adjusted values. 

![SchoolSum-THS Summary](School_District_Analysis/Images/SchoolSum-THS Summary.png)

From this comparison it is clear that removing the 9th grade data had little impact on the school’s averages and overall percentages. There were 461 student’s test scores identified and removed in a school of 1635 students, a little more than 28% of the student body.  The most significant impact is seen in the “% Overall Passing” category which decreased by 0.3% in the adjusted table.  This suggests there was not wide variability in the testing score average and percent of students passing among the 9th grade class vs. the 10th, 11th, and 12th grades at THS.

### High and Low Performing Schools

Budget allocation in a district is often determined by school performance.  The School Summary was filtered based on the calculated % Overall Passing where the district’s “high-performing” schools are selected as the top five schools with the highest overall percentage of passing students.  These are:

![SchoolSum_TopPerformers](School_District_Analysis/Images/SchoolSum_TopPerformers.png)

In both the original school summary and after accounting for the adjusted values, Thomas High School remained the second highest performing school in the district.  The difference in % Overall Passing score was only three tenths of a percent decrease after adjustment.  This adjustment brings THS closer to the third highest performing school, Griffin High School.  When the Overall Percentages are rounded so that values are limited to three significant figures, Griffin High School is tied with Thomas High School at 90.6% Overall Passing.

Low performing schools are selected as the five schools with the lowest overall percentage of passing students.  These are:

![SchoolSum_LowPerformers](School_District_Analysis/Images/SchoolSum_LowPerformers.png)


### Math and Reading Scores by Grade

Summary tables of math and reading scores by grade were generated to visualize and determine areas for improvement by grade.  The averages for Thomas High School’s 9th grade are shown as “NaN.”

![AvgByGrade](School_District_Analysis/Images/AvgByGrade.png)


### Scores by School Spending

Testing averages and percentage of passing scores were grouped and collected into DataFrames by arbitrarily determining spending ranges so that an equal number of schools can be divided and spending ranges assigned to classify how spending per student could affect score averages and passing rates. As demonstrated with the district wide summary, the removal of THS 9th grade scores did not have an impact on this district wide spending summary.

![ScoresbySpending](School_District_Analysis/Images/ScoresbySpending.png)

### Scores by School Size

Average math and reading scores, the average percentage of students who passed math and reading, and the average overall percentage were grouped and listed based on school size.  There were three main categories for size including “Small” being less than 1000 students, “Medium” included the 1000 to 2000 student range, and “Large” was defined as between 2000 and 5000 students.  As with the other district wide summaries, the adjusted values had no impact on this summary table.

![ScoresbySize](School_District_Analysis/Images/ScoresbySize.png)

### Scores by School Type

Testing averages and percentages of students passing were grouped by school types “Charter” vs. “District” to identify any trends between school type and student performance to show how school size affects score averages and passing rates.  Again, it is noted that this district-wide summary is not impacted by the adjusted values.

![ScoresbyType](School_District_Analysis/Images/ScoresbyType.png)


## Summary

Based on the Results above, it is clear that removing the THS ninth grade test scores did not have a significant impact on the district wide summaries or even the overall school averages and percent passing for Thomas High School.  This indicates that the questionable test scores did not skew the overall picture district wide nor even for Thomas High School based on 10th through 12th grade performance.  The most notable impacts were the following:

* In the District Summary, the adjusted values increased the % Overall Passing by three tenths (0.3) of a percent.

* In the School Summary, looking at the original vs. adjusted data for THS specifically, there were four small corrections:
  - “Average Reading Score” increased by less than 0.1%
  - “% Passing Math” decreased by about 0.1%
  - “% Passing Reading” decreased by about 0.3%
  - “% Overall Passing” decreased by 0.3%

* The adjusted Top Performing Schools summary now shows a tie (when limiting % Overall Passing to 3 significant figures) between the second and would-be third ranked schools.  In order to determine whether Thomas High School should remain as the second ranked top performer, the calculated percentage would be determined from the hundredths of a percent values.

* The Math and Reading Scores by Grade summary will not consider the 9th grade averages for Thomas High School and the tables show a null value “NaN” for the 9th grade averages.

