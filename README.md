# Amazon_Vine_Analysis

# Overview of the Analysis

Since your work with Jennifer on the SellBy project was so successful, you’ve been tasked with another, larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. 
In this project, you’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. You’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, you’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.
In order to accomplish this the following will be created:
  * Deliverable 1: Perform ETL on Amazon Product Reviews
  * Deliverable 2: Determine Bias of Vine Reviews
  * Deliverable 3: A Written Report on the Analysis (README.md)


# Results

 * To review how many helpful and non-helpful Vines reviws first the data needed to be reviewed, then the data needed to be dropped of missing values. According to the prompt, helpful revies were determined by having >50% of the votes as "helpful" so therefore a helpful_reviews_df datafram was created. 

To review how many helpful and non-helpful Vine reviews were 5 stars, the following script was written:
 * five_star_vine_reviews = vine_helpful_reviews_df.filter("star_rating=='5'").count()
 * five_star_not_vine_reviews = not_vine_helpful_reviews_df.filter("star_rating=='5'").count()
 * It was determined that The number of helpful Vine reviews that were 5 stars was 48 and the number of helpful non-Vine reviews were 15,663

The percentage of helpful and non-helpful Vine reviews with 5 stars was also done by writing the following script: 
 * percent_five_star_vine_reviews = (five_star_vine_reviews/total_num_helpful_vine_reviews)*100
 * percent_five_star_not_vine_reviews = (five_star_not_vine_reviews/total_num_helpful_not_vine_reviews)*100
 * It was determined that in the video game category and looking at reviews that meet our "helpful" criteria, Vine reviewers provided 5-stars 51% of the time, while non-Vine reviewers provided 5-stars just less than 39% of the time.
