# MIST4610--GROUP-PROJECT-2-

Group 2
This project explores long-term trends and demographic influences on student physical fitness rates across California, utilizing advanced data manipulation and visualization techniques learned in MIST 4610.

# Team Members:

[Daniel Ferrer](https://github.com/djferrer25-maker)

[Ian Martin](https://github.com/icmj6789-commits)

[Noila Rahimjon](https://github.com/noilar)

[Oraa Raysoni](https://github.com/oraaraysoni-beep)

[Sisira Gudi](https://github.com/sisiragudi-web)

# Our datset: 
The core dataset provides a granular, 20-year time-series analysis of student physical fitness outcomes in California. This dataset was selected due to its high complexity, substantial observation count, and critical public health relevance.

Source: US Data.gov (California Department of Education)

Original URL: https://catalog.data.gov/dataset/percentage-of-physically-fit-students-lghc-indicator-9b191

Dimensions: 37,236 rows (observations) and 14 columns (dimensions).

Content: This data tracks the percentage of students in Grades 5, 7, and 9 who passed the state’s 6-part Physical Fitness Test. The data is stratified by Year, County, Grade Level, and Strata (including 'All Students' and specific demographic groups like 'Sex').

Key Columns & Data Types:

Year: Text (e.g., "1998-1999") - Manipulated to integer.

Geography: Text (California County Name)

Grade Lev: Text (5, 7, or 9)

Percent: Decimal (The core metric—the percentage of students scoring 6 of 6 on the test).

Numerator, Denominator: Integers (Raw counts used for calculation).

LCI, UCI, Stardard Error, RSE: Decimals (Statistical confidence and reliability measures).

# Key Analytical Questions

The two questions below are designed to move beyond simple descriptive statistics, focusing on complex relationships and long-term trends that possess significant social and economic importance, satisfying Evaluation Criterion (b).

Question 1: The Influence of County Size

Does the size of a county (Small, Medium, or Large) have a meaningful impact on the average physical fitness scores of its students over the 20-year period?

Importance: This question addresses resource allocation and health equity. If fitness outcomes are systematically tied to a measurable geographic characteristic like county size, the findings are critical for public health policy, enabling targeted intervention programs in high- or low-density areas.

Tie to Data: The analysis leverages the Geography column (County Name) to link the fitness data with an external classification of county size, transforming the data into a meaningful demographic dimension.

Question 2: Analyzing Long-Term Evolution and Divergence

How have student physical fitness rates in California evolved over the last 20 years, and how does this statewide trend compare to individual county trends?

Importance: This explores the effectiveness of long-term state-wide initiatives and identifies high-performing and underperforming regions. Understanding the "Risers vs. Fallers" provides essential insights for sharing best practices and addressing unexpected declines, offering a non-trivial view of the state-wide average.

Tie to Data: This question utilizes the full time-series nature of the 20 years of data, comparing individual county trends against the aggregate state-wide trend using the Year and Percent columns.

# Data Manipulations and Calculations

To address the complexity of the questions, two primary non-trivial manipulations were performed, demonstrating the team's ability to clean and enrich a raw dataset.

Manipulation 1: Year Standardization

Problem: The Year column was formatted as a text string representing a range (e.g., "1998-1999"), which is unsuitable for time-series analysis in Tableau.

Purpose: To convert the text year into a usable, sequential numeric field for trend analysis.

Method: A calculated field was created using Tableau's SPLIT() function to isolate the first four digits ("1998") and then casting the result as an integer type.

Manipulation 2: Calculating 20-Year Percentage Change

Problem: We needed to quantify the specific long-term change for every county to identify significant 'Risers' and 'Fallers' (Question 2). This required a complex, fixed calculation across the entire 20-year span.

Purpose: To establish a County-Level Performance Metric showing the percentage point change in fitness scores from the first year (1998) to the last year (2018).

Method: A Level of Detail (LOD) expression was used in Tableau. The calculation found the Percent value for the beginning year and subtracted it from the Percent value of the final year, fixed at the Geography (County) level. This calculated metric enabled the creation of the '20-Year Change' bar chart used in the analysis.

# Analysis and Results

Question 1: The Influence of County Size

Finding: No Correlation Between County Size and Fitness

Contrary to our initial hypothesis, our analysis revealed no statistically significant correlation between a county's size (Small, Medium, or Large) and its student fitness scores. High and low performing counties were distributed randomly across all size categories.

Visualization Used: Box Plot and Bar Chart (comparing mean Percent across the three County Size categories).

Implication: This "null result" is a critical finding for policymakers. It indicates that structural size is not a barrier to fitness. A large urban county has just as much potential for high fitness as a small rural one. Therefore, the disparity in fitness rates is likely driven by manageable variables such as access to recreation, income levels, food security, and school funding. Policy focus should shift away from geographic excuses and towards these actionable socioeconomic factors.

Question 2: Long-Term Evolution and Divergence

Finding: Divergence of "Risers" and "Fallers"

While the state-wide average fitness rate increased by 6.5% over the two decades (peaking in 2011), the aggregate data masks a massive divergence in local outcomes. The "20-Year Change" metric identified distinct groups of "Risers" and "Fallers."

Visualization Used: Dual-Axis Line Chart (State Average vs. County Trends) and a Calculated Bar Chart showing 20-Year Change (%).

Quantified Divergence:

Biggest Risers: Counties like Mono (+33.7%) and Amador (+27.5%) saw massive gains.

Biggest Fallers: Counties like Trinity (-15.3%) and Lake (-14.9%) experienced significant declines.

Implication: Because we proved in Question 1 that size doesn't matter, the success of the "Risers" is likely due to specific local interventions and policies. This implies that governments can actively encourage fitness through specific programs regardless of their county's size. The state should audit the "Riser" counties to identify what successful strategies (e.g., new PE curricula, park investments) can be replicated in the "Faller" counties.

# Tableau Packaged Workbook

The complete analysis, including all visualizations, calculated fields, and the externally joined data source, is contained within the following Tableau Packaged Workbook file:

Filename:

Location: Included in this repository for review.

