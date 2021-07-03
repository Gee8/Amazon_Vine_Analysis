# Amazon_Vine_Analysis

## Overview of the analysis: 
For this analsis we looked at an Amazon review dataset for electronics. The purpose of our analsis was to determine if Amazon's Vine program was worth the reviews it generated. The products within the dataset have unpaid and paid reviews. The paid reviews were from those enrolled in the Vine program. Using PySpark in Google Colab we imported the dataset from an Amazon S3 bucket into a dataframe. We then created our `vine_df` using the columns `review_id`, `star_rating`, `helpful_votes`, `total_votes`, `vine`, and `verified_purchase`. We then filtered the df to include reviews that had more than 20 votes. We then filtered further to include only reviews condidered "helpful" by using only the rows where `helpful_votes/total_votes>=.5`. Now that we have a `helpful_df`, we broke this into those who were included and not included in the Vine program, these DataFrames were called `paid_vine_df` and `unpaid_vine_df`, respectively. To determine if the Vine program was worthwhile, we wanted to look at the number of 5 star reviews and their percentages for the paid/unpaid reviews. Shown below is how we attained the total number of reviews, the number of 5 star reviews, and the five star percentage of total reviews for each the total number of helpful reviews, paid reviews, and unpaid reviews. 

<img width="400" alt="totalNumber" src="Images\totalReviews.png">
<img width="400" alt="total5Stars" src="Images\5StarReviews.png">
<img width="400" alt="fiveStarPercentages" src="Images\fiveStarPercentages.png">

After collecting the values, we placed them in our `five_star_df` shown below.

<img width="400" alt="fiveStarDF" src="Images\fiveStarDF.png">

## Results: 

From our `five_star_df` shown above, we can see that there were 47808 total reviews. 
- 1032 of these were Vine reviews and 46776 were non-Vine reviews. 
- There were 440 and 21755 5 star reviews for Vine and non-Vine reviews, respectively. 
- We have that 42.64% of the Vine reviews and 46.51% of the non-Vine reviews were five stars.

## Summary:

Since there is a higher percentage of five star reviews from the non-Vine reviews, we can conclude that there was not a positivity bias for reviews in the Vine program. For additional analysis, we can look to see what the average rating given by each group is and determine if Vine reviews tend to be higher than non-Vine reviews on average, even if they have a lower percentage of 5 star reviews overall.