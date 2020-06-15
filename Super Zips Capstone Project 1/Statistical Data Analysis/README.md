Super Zips Capstone Project: Statistical Data Analysis

------------------
Overview:
------------------
This document summarizes the steps and corresponding results of performing Statistical Data Analysis on Education (obtained from the US Census) and Income (obtained from the IRS) data. For this analysis, these two variables are defined to be the primary factors of an area’s overall standard of living.  Also, they’re shown to be linearly related and vary together. **Only use 2011 and 2017 data due to intersection of annual releases of datasets**

------------------
Steps and Findings
------------------
1) Conduct EDA: Plot ECDFs for all years available for Education and Income Scores with color variation to show change over time.

Results and Findings: The ECDF plots for Education and Income Scores show gradual shifts to the right over time as indicated by the. This is a good sign that overall people are gradually becoming more educated and earning more money to live better.

2) Parameter Estimation: Estimate the difference of the mean Education and Income Scores of all zip codes from 2011-2017.

Results and Findings: Difference of Education Score means = 0.126 and Difference of Income Score means = 0.231, which shows, on average, how much the Education and Income scores have changed in 7 years (including the year of 2017).

3) Confidence Interval Calculation: Use Bootstrap replicates method for 2011 and 2017 datasets only for both Education and Income scores to report a 95% bootstrap confidence interval.

Results and Findings:
-95% bootstrap Conf. Int. bounds of Education Scores = [0.112  0.140]
-95% bootstrap Conf. Int. bounds of Income Scores = [0.221   0.241]
These bounds show the Confidence Interval containing the differences of means of Education and Income estimated in Step 2.

4) Hypothesis Testing: Answer the question, “Have Education and Income Scores improved?” (i.e. Null Hypothesis: 2017 - 2011= 0, Alternate Hypothesis:2017 - 2011> 0) by performing a bootstrap permutation test by shifting the two data sets so that they have the same mean and then use bootstrap sampling to compute the difference of means.

Results and Findings: The p-values for both bootstrap hypothesis tests are so small that Python essentially returns zero resulting in statistical signifying that the null hypotheses for both Education and Income can be rejected. Thus, the two means are different which indicate change between 2011 and 2017.

5) Correlation and Covariance Analysis: Calculate Pearson correlation coefficient and covariance between Education Scores and Income Scores from 2011-2017 (confirm relationship between Education and Income).

Results and Findings: The scatterplot suggests, at first glance, that there is a positive relationship between Education and Income plus the two variables vary together. This is confirmed by calculating the Pearson Correlation Coefficient (r = 0.473) and Covariance (cov = 0.027) between the two sets of scores, but also shows that the relationship is not that strong.

6) Linear Regression: Perform a linear regression for both the 2011 and 2017 data. Then, perform pairs bootstrap estimates for the regression parameters. Report 95% confidence intervals on the slope and intercept of the regression line (show how Education and Income change together over time).

Results and Findings:
-2011: slope = 0.573, conf int = [0.565  0.580]
-2011: intercept = 0.020,  conf int = [-0.007  0.052]
-2017: slope = 0.634, conf int = [0.626  0.642]
-2017: intercept = -0.079,  conf int = [-0.112  -0.047]
Calculating these bootstrap results quantify how Education and Income change together over time. These are shown visually from the combined line and scatter plot as the regressing line changes from 2011 to 2017.

7) Calculate 95% bootstrap confidence interval for overall standard of living: compare the mean ratio of Education Scores to Income Scores.

Results and Findings:
2011: mean ratio = 1.750, conf int = [1.747 1.753]
2017: mean ratio = 1.644, conf int = [1.641 1.647]
These results suggest changes in overall standard of living over 7 years (including the year of 2017) and even the confidence intervals overlap. To confirm, bootstrap hypothesis testing is done in the next and final step.

8) Bootstrap hypothesis testing on ratios: Perform a bootstrap permutation test (like in Step 4) by shifting the two data sets so that they have the same mean. Then use bootstrap sampling to compute the difference of means.

Results and Findings: The p-value for the bootstrap hypothesis tests are so small that Python essentially returns zero resulting in statistical signifying that the two means are different. This indicates a change in overall standard of living between 2011 and 2017.
