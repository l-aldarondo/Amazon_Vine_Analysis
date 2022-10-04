# Amazon_Vine_Analysis
Using PySpark to perform the ETL process, connect to AWS RDS instance and load transformed data into pgAdmin

## Background

### Overview

This new assignment consists of two technical analysis deliverables and a written report. You will submit the following:

- Deliverable 1: Perform ETL on Amazon Product Reviews

- Deliverable 2: Determine Bias of Vine Reviews

- Deliverable 3: A Written Report on the Analysis (README.md)



### Purpose

Analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, you’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. You’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, you’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.


## Resources

Data source:

- (1) Amazon_Reviews_ETL_starter_code, (2) challenge_schema

Software:

- Google Colab, AWS RDS, pgAdmin 6.14, Visual Studio Code 1.71.2
 
<br/>

## Results

### D1: Linear Regression to Predict MPG:

(a)![Mecha Car Linear Regression Summary](./Images/MechaCar_linear_regression_summary.png)
 
<sub> Figure (a) MechaCar Linear Regression Summary

<br/>

- Q1. Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

    - Methodology: Pr(>|t|) value represents the probability that each coefficient contributes a random amount of variance to the linear model.

    - A1. Using the MechaCar_mpg dataset, vehicle_lenght and ground_clearance (as well as intercept) are statistically unlikely to provide random amount of variance to the linear model. In other word **The vehicle_length and grond_clearance have a significant impact on mpg.**

- Q2. Is the slope of the linear model considered to be zero? Why or why not?

    - Methodology: Examine the Pr(>|t|) value in the summary above for the (Intercept).

    - A2. **The Intercept is statistically significant** (less than the 0.05) **and not zero**. This would indicate that the Intercept term explains a significant amount of variance in the dependant variable when all the independant variables are equal to zero. it could be that the significant feature (such as vehicle lenght and ground_clearance) may need scaling or transforming to help improve the prdictive power of the model; or there are other variables that can help explainthe variability of our dependant variable (mpg) that has not been included in our model.


- Q3. Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

    - Methodology: Examine the multiple R-squared to indicate how well the regression model approximate to rea-world data points. In most caese, the value will range between o and 1 and can be use as probability metric to determine the likelihood that future data point will fit the model.

    - A3. **The Multiple R-squared value is 0.71**, while the p-value remained significant (very small). **Indicating that the model does an adequate job predicting mpg**.

<br/>

### D2: Summary Statistics on Suspension Coils:


(b)![Total Summary](./Images/total_summary.png)
 
<sub> Figure (b) Total Summary for Suspension Colis.

<br/>

(c)![View by lot using group_by](./Images/View%20by%20lot%20using%20group_by.png)
 
<sub> Figure (c) View by lot using group_by

<br/>

Q1.The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

- Methodology:

- A1. **In Total the specifications are met with a variance of 62.29 (less than a 100)**.

- A2. **By lots, lots 1 and 2 meets specifications, however lot 3 has a variance that exceed specifications (100 psi)**.


<br/>


### D3: T-Tests on Suspension Coils:

**Lot 1 is NOT significantly different from the population mean with a p-value of 1**.

(d)![t_test_lot1](./Images/t_test_lot1.png)
 
<sub> Figure (d) T-Test for Lot 1

<br/>

**Lot 2 is NOT significantly different from the population mean with a p-value of 0.61**.

(e)![t_test_lot2](./Images/t_test_lot2.png)
 
<sub> Figure (e) T-Test for Lot 2

<br/>

**Lot 3 is significantly different from the population mean with a p-value of 0.042**.

(f)![t_test_lot3](./Images/t_test_lot3.png)
 
<sub> Figure (f) T-Test for Lot 3

<br/>

### D4: Study Design: MechaCar vs Competition

- Q1. What metric or metrics are you going to test?

- A1. An additional metric not in the MechaCar_mpg dataset are horsepower, engine size or number of cylinders. Manufacturers may look into this data, since is usually noted that smaller engine size (8 cyl vs 6 cyl vs 4 cyl) result in improved mpg.

- Q2. What is the null hypothesis or alternative hypothesis?

- A2. The Null hypothesis would be that there is NO statistical difference and the Alternative hypothesis would be there is a statistical difference.

    - H0 : The means of all groups are equal, or µ1 = µ2 = … = µn.
    - Ha : At least one of the means is different from all other groups.

- Q3. What statistical test would you use to test the hypothesis? And why?

- A3. Since a car manufacturer may have multiple competitiors, we are interested in comparing the means across more than two samples or groups. The most straightforward way to do this is to use the analysis of variance (ANOVA) test, which is used to compare the means of a continuous numerical variable across a number of groups. In this case we're going to use a **two way ANOVA test**; to determine if there a statistical difference between the distribution means from multiple samples.

- Q4. What data is needed to run the statistical test?

- A4. To perform an ANOVA test in R, we have to provide the aov()function two arguments:

    - formula - a formula specifiying the model.
    - data - a DataFrame in which the variable specified in the formula is found.

## Summary

For this project we were able to use R, RStudio and VS Code to complete all the deliverable requested by the client: D1: Linear Regression to Predict MPG, D2: Summary Statistics on Suspension Coils, D3: T-Test on Suspension Coils, D4: Design a Study Comparing the MechaCar to the Competition.



## References

[Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[Spark](https://downloads.apache.org/spark/)
