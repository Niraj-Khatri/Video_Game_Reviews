<h1 align="center"> Pyspark-AWS Project </h1>

The goal of this project was to extract Amazon product review data, clean the data, and load the data to a Postgres database using AWS RDS. Afterwards, I did analysis on the data to determine whether a certfied Amazon vine reviewer provided more helpful reviews than a non-vine reviewer.


<h2 align="center"> ETL </h2>

I extracted Amazon video game review data from the following site: 
https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz
![Extract](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/Extract%20Data.PNG)


- - - 
I cleaned the data and created 4 tables to do future analysis with: customers, products, reviews, and vines.

![Cleaning](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/Cleaning.PNG)

- - - 
I created a AWS RDS instance and used an SQL script to create the 4 tables in Postgres. 
![AWS](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/AWS.PNG)


![Postgres](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/Postgres.PNG)
- - - 
With PySpark, I loaded the data tables to Postgres.

![Upload](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/Upload.PNG)

<h2 align="center"> Data Analysis </h2>

I wanted to analyze the Amazon video game data to determine if Amazon vine reviewers provided more helpful reviews.
- - - 
First, using the vine table, I filtered out reviews that had less than 50% of the helpful votes and reviews with less than 20 total votes.

![Filter](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/Filter.PNG)
- - -
Next, I calculated the number of vine reviews and non-vine reviews in the filtered data set.

![Vine](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/Vine.PNG)
- - -
Finally, I wanted to look at top products (5 stars). I filtered out the data set for five star reviews only and calculated the percentage of 5 star reviews among vine and non-vine reviews.

![5Stars](https://github.com/Niraj-Khatri/Pyspark-AWS/blob/master/images/5%20stars.PNG)

Conclusion: Vine reviewers gave a product 5 stars half the time a vine review was found helpful. This is 10% more compared to non-vine reviews. This may suggest 5 star reviews are found more helpful overall since they instill confidence in the reader to buy the product. 


