# Big-Data-ETL
Module 22 Challenge


## Background
In this assignment, you will put your ETL skills to the test. Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. They are quite large and can exceed the capacity of local machines. One dataset alone contains over 1.5 million rows; with over 40 datasets, data analysis can be very demanding on the average local computer. Your first goal will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark or SQL to perform a statistical analysis of selected data.

This Challenge contains two parts. Part 1 is required. Part 2 is optional but highly recommended.

**Part 1:** Extract two Amazon customer review datasets, transform each dataset into four DataFrames, and load the DataFrames into an RDS instance.

**Part 2:** Extract two Amazon customer review datasets and use either SQL or PySpark to analyse whether reviews from Amazon's Vine program are trustworthy.

## Instructions
### Part 1
Upload the `part_one_starter_code.ipynb` into Google Colab and create a duplicate of this file.

Explore the Amazon Reviews datasets and pick two datasets to perform ETL.

Rename each `part_one_starter_code.ipynb` file according to the dataset you are using. For example, if you are going to use the Video Game reviewsLinks to an external site. file, rename file, part_one_video_games.ipynb. Repeat the process for the duplicate file you created in Step 2.

#### Extract the Data

Read in each dataset using the correct header and sep parameters.

Get the number of rows in each dataset.

Transform the Data

For each dataset use the `schema.sql` file located in the *Resources* folder to create the four DataFrames as follows:
1. Create the "review_id_df" DataFrame with the appropriate columns and data types.
2. Create the "products_df" DataFrame that drops the duplicates in the "product_id" and "product_title columns.
3. Create the "customers_df" DataFrame that groups the data on the "customer_id" by the number of times a customer reviewed a product.
4. Create the "vine_df" DataFrame that has the "review_id", "star_rating", "helpful_votes", "total_votes", and "vine" columns.
5. Load the Data into an RDS Instance
6. Export each DataFrame into the RDS instance to create four tables for each dataset.

**NOTE**: This process can take up to 10 minutes for each. Ensure that everything is correct before uploading.

### Part 2
Recall that this part is completely optional; you can complete it as a way to challenge yourself and boost your new skills.

In Amazon's Vine program, reviewers receive free products in exchange for reviews. Amazon has several policies to reduce the bias of its [Vine reviews](https://www.amazon.com/gp/vine/help?ie=UTF8)


But are Vine reviews truly trustworthy? Your task is to investigate whether Vine reviews are free of bias. Use either PySpark or, for an extra challenge, SQL to analyse the data.

If you choose SQL, first use Spark on Colab to extract and transform the data and then load it into a SQL table on your RDS account. Perform your analysis with SQL queries on RDS.

While there are no strict requirements for the analysis, consider steps you can take to reduce noisy data, such as filtering for reviews that meet a certain number of helpful votes, total votes, or both.

Submit a summary of your findings and analysis.

## Requirements
#### Extract (35 points)
- Uses PySpark to connect to and load the AWS datasets into DataFrames. (10 points)
- The correct parameters are used to read in the data into a DataFrame. (15 points)
- The first 20 rows of each DataFrame is displayed. (5 points)
- The number of rows for each DataFrame is displayed. (5 points)
#### Transform (45 points)
- The "review_id_df" DataFrame is created with the appropriate columns and data types. (15 points)
- The "products_df" DataFrame is created and the the duplicate values are dropped. (10 points)
- The "customers_df" DataFrame is created and displays the number of times a customer reviewed a product grouped by the "customer_id". (10 points)
- The "vine_df" DataFrame is created that has the "review_id", "star_rating", "helpful_votes", "total_votes", and "vine" columns. (10 points)
#### Load (20 points)
- The four DataFrames for each dataset are successfully loaded into an RDS instance. (20 points)

## Submission
Download your Google Colab notebooks as .ipynb files and upload them into the "part-1" folder of your "Big-Data-ETL" Git repository.

**IMPORTANT**
- Do not clear the outputs of your .ipynb files, and do not upload notebooks that contain your RDS password and endpoint. Delete these two items before making your notebook public!
- Ensure your repository has regular commits and a thorough README.md file to explain the ETL project.
- If you are doing "part-2" of this assignment, copy your SQL queries into .sql files and upload them into the "part-2" folder of your "Big-Data-ETL" Git repository.

**IMPORTANT**

Remember to closely monitor any AWS resources that you choose to use! It’s crucial that you clean up and stop, or shut down any AWS resources to avoid accruing additional costs. Please refer to the AWS_cleanup.pdf and the AWS_check_billing.pdf files in the Resources folder of the Starter_Code.zip file. Or, you can download the [AWS Billing Guide](https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.1/AWS_check_billing.pdf).

To submit your Challenge assignment, click Submit, and then provide the URL of your GitHub repository for grading.


## References
*Amazon Customer Reviews Dataset. (n.d.)*. Retrieved April 08, 2021, from: https://s3.amazonaws.com/amazon-reviews-pds/readme.html [Link](https://s3.amazonaws.com/amazon-reviews-pds/readme.html)
