# Amazon_Vine_Analysis
Using PySpark to perform the ETL process, connect to AWS RDS instance and load transformed data into pgAdmin

## Background

### Overview of Analysis

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

## Methodology

<br/>

## Results

- How many Vine reviews and non-Vine reviews were there?

    - There were 170 vine reviews and 37840 non_vine reviews


- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

    - There were 65 5 star Vine reviews and 20612 5 star non-Vine reviews.

- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

    - 38.24% of the 5 star reviews were Vine and 54.47% of 5 star reviews were non-ine.


## Summary

Ho: 5star_vine = 5star_not_vine (no difference in the percenage(proportion) of 5star ratings paid(vine) vs unpaid(not vine).

Ha: 5star_vine <> 5star_not_vine(there is a difference).

- percentage_5star_vine = **38.24%**
- percentage_5star_not_vine = **54.47%**
- **findings: the percentage of 5star rating is not the same when comparing vine reviewsto not_vine reviews.**
- **There is reason to believe that the percentage of 5star raitings is not directly tied to whether the review is paid or unpaid.**
- note: this hypo thesis testwould need tobe evaluated comparing the proportion of 5star reviews among the two samples.


## References

[Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[Spark](https://downloads.apache.org/spark/)



(a)![Mecha Car Linear Regression Summary](./Images/MechaCar_linear_regression_summary.png)
 
<sub> Figure (a) MechaCar Linear Regression Summary

<br/>

