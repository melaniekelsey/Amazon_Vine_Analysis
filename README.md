# Amazon_Vine_Analysis

## Overview of the Analysis

I was asked to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows companies to receive reviews for their products. Companies can bay a small fee to Amazon and provide products to Amazon Vine Members, who are required to publish a review. 

## Results

I selected the Amazon Vine Pet Supply dataset to examine if there is any bias toward favorable reviews from Vine Members in my data set. Since, it was such a large data set, I used Amazon Web Services to house the data. I used Google Colab to convert the data and push it to tables in PostgreSQL. From Postgres, I exported the data from the Vine Table to a CSV file. See below the image of the vine_data_df. There were 2643619 total reviewers.

![vine_data_df.png](https://github.com/melaniekelsey/Amazon_Vine_Analysis/blob/main/images/vine_data_df.png)

I was next tasked with filtering down to the Vine reviewers who have received over 20 votes to pick reviews that are more likely to be helpful and avoid as division errors. There were 33950 total reviewers with 20+ total votes. 

![total_votes_over_20.png](https://github.com/melaniekelsey/Amazon_Vine_Analysis/blob/main/images/total_votes_over_20.png)

Next, I filtered that dataframe into a new dataframe for the reviews whose % of helpful votes were over 50% of the total votes. That dataframe was filtered down to 5440 reviewers who have were given a high percentage of helpful votes. 

![helpful_votes_df.png](https://github.com/melaniekelsey/Amazon_Vine_Analysis/blob/main/images/helpful_votes_df.png)

I was next tasked with creating a new dataframe with helpful reviews were part of the paid Vine program and one where they not part of the Vine program. There were 14 paid reviewers and 5426 unpaid reviewers with helpful votes. 

![paid_unpaid_reviews.png](https://github.com/melaniekelsey/Amazon_Vine_Analysis/blob/main/images/paid_unpaid_reviews.png)

Next, I looked at paid and unpaid 5 star reviews. There were 4 paid 5 star reviews and 3737 unpaid 5 star reviews. 

![paid_unpaid_5_star.png](https://github.com/melaniekelsey/Amazon_Vine_Analysis/blob/main/images/paid_unpaid_5_star.png)

Finally, I calculated the % of paid and unpaid 5 star reviews. 28.6% of the paid reviews were helpful. 68.9% of the unpaid reviews were helpful. 

![paid_unpaid_percent.png](https://github.com/melaniekelsey/Amazon_Vine_Analysis/blob/main/images/paid_unpaid_percent.png)

## Summary

Overall, I believe that there in not bias towards unpaid or paid reviewers. As you can see, the paid reviewers tend to give less reviews overall than the upaid reviewers. if anything, maybe they are more critical and less likely to give 5 stars than the unpaid reviewers. The comparison of 68.9% unpaid reviewers to the 28.5% paid reviewers is staggering. Maybe the paid reviewers rate so many products that they are more discerning of their 5 stars? While, the unpaid reviewers are giving their unbiased opinions? 

I think a further deep dive would be to look at the actual different product categories. I selected Pet Supplies, but there might be better datasets that hit a bigger audience than just pet owners to really fully determine if there is bias. If could be, that pet owners are more likely to vote a review as helpful as opposed to the a more general category. 
