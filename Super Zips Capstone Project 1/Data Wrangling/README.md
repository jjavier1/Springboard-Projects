------------------------------
Super Zips Data Wrangling
------------------------------

------------------------------
Steps Taken for Data Wrangling
------------------------------

1) Determine and download main source data files needed from irs.gov and data.census.gov

2) Determine which columns to be used using documentation files provided with main source data files

3) Create subset data files from main source date files due to big source file sizes

4) Determine how to address missing data:
-For the IRS AGI (Adjusted Gross Income) data, the missing data was filled in thanks to cross-referencing smaller data subset files divided from the main aggregate source file and grouped by state.
-For the Census data, all rows containing missing data were removed from the dataset since certain estimates could not be calculated due to either no or too few observations as explained in the Symbols Dictionary

5) Re-define appropriate data types for all columns in data

6) Regroup/Tidy Data into a format appropriate for analysis using the .melt() and .pivot() dataframe methods

7) Calculate scores from raw data as described below. **EDA was not performed on the raw data due to file size**

8) Perform EDA by the following steps and repeat for every year available (i.e. 2011-2018 for Census data and 2006-2017 for IRS AGI data)
a) Using .info() dataframe method to confirm numeric data uniformity and no missing data as well as data types
b) Use .describe() dataframe method to generate descriptive statistics and confirm data integrity
c) Plot a histogram to visualize distribution of all zip code scores from all 51 states
d) Use FacetGrid function from Seaborn to plot multiple swarmplots visualizing the score distributions by state

9) Create data analysis files for visualizations


------------------------------
Calculating Education and Income Scores per Zip Code:
------------------------------
This score is calculated using a weighted average formula based on population and scoring scales below. Refer to the Jupyter notebooks in both IRS and Census folder for more details.

Education Scoring Scale - Categories obtained from column names in source data.
1 = Less than 9th grade
2 = 9th to 12th grade, no diploma
3 = High school graduate (includes equivalency)
4 = Some college, no degree
5 = Associate's degree
6 = Bachelor's degree
7 = Graduate or professional degree

IRS AGI Scoring Scale - Determined by Adjusted Gross Income submitted by IRS Forms 1040, 1040A, 1040EZ (column named as “AGI_STUB” or “AGI_CLASS” depending on which year)
1 = $1 under $25,000
2 = $25,000 under $50,000
3 = $50,000 under $75,000
4 = $75,000 under $100,000
5 = $100,000 under $200,000
6 = $200,000 or more
