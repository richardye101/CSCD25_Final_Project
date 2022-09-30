# How emotions fuel the growth and decline in activity online
#### An Analysis of the Activity Level Changes within reddit Communities in Relation to Sentiment

### [The project blog page]("https://richardye101.github.io/CSCD25-Final-Project/")  
https://richardye101.github.io/CSCD25_Final_Project/

### [Github repo]("https://github.com/richardye101/CSCD25-Final-Project")

## Abstract
The year 2019 to 2021 has seen countless events with global ramifications. As individuals become increasingly interconnected online through social media, it raises questions about how they are interacting with one another on these platforms and why. To understand these changes is to understand what people find most interesting or important, and how they feel about them. In this work, we will take a stab at answering this question by examining a subset of ~5000 reddit communities and the changes in activity level within them, as well as whether the sentiment associated with the activity is positive or negative. We will find similarities between subreddits that have grown in size, as well as those that have contracted. We will then identify whether the activity through the grown/contraction phases is largely related to positive or negative sentiment.

## Research Questions
1. What are the similarities shared between subreddits that experienced similar activity level changes?  
  * Did the ones that grew/contracted:
  - experience that growth during similar time periods, and are there any reasons why?  
  - share common topics?
  2. What kind of sentiment can we relate to subreddits that experienced similar activity level changes?  
  * Was there any sentiment associated with these changes?  
  * Was growth/contraction associated with very positive/negative sentiments? (I.e. Was the change driven by love/attraction or by hate/repulsion?)  
  
~~3. (Time Permitting) Can we say which subreddits are due to grow/contract based on our results?~~
  
## Hypothesis
  Activity level changes in subreddits are **positively** correlated with **the degree** of positive or negative sentiment associated with the activity.

## Methods
- Collect the `text_submissions` and `text_comments` datasets
- Determine the size of the data we have to work with, and the distribution of activity across datasets with histograms
- Converting columns to sensible datatypes (Unix time to normal date and time)
- Removing data from communities with little to no activity throughout the time period
- Aggregate activity by week and extract changes in levels of activity per subreddit
- Filter out subreddits which had low activity levels or a small slope of activity change (subreddits having below 5 posts a week on average, and an average change in activity level less than |1| per week)
- Create new matrix of submissions with a column containing all the comments
- Create a tf-IDF matrix on that matrix and perform SVD to reduce dimensionality
- Use kmeans to cluster subreddits together by topic, and visualize with interactive plots based on PCA components
- Divide subreddits clusters into those that grew and those that contracted by percentile. (Ie. those in the top 90th percentile of growth are put together, while those in the 10th percentile of growth are put together)
- Examine the clustering by looking at which subreddits were clustered together and attempt to name each cluster. This will help determine if growing/contracting subreddits shared common topics.
- Plot line charts of activity over time per cluster and attempt to connect them to external events. If we see high correlation or spikes in activity in multiple clusters during the same time period, we can conclude there was a common factor that affected those clusters. 
- Perform sentiment analysis on each cluster to examine whether the sentiment associated with the activity level changes

# Conclusion

We were able to find some interesting results with our analysis of the activity level changes between subreddits that grew and subreddits that contracted, and we were somewhat successful in clustering subreddits based on similar topics. We found that regardless of the overall activity change observed over the 2.5 years of data we have, there was a significant uptick in activity for all our filtered subreddits in early 2020, when COVID-19 lockdowns were being put in place around the world.

Based on our brief sentiment analysis of the sentiment associated with each subreddit’s submissions, we cannot say whether activity level changes in subreddits are positively correlated with the degree of positive or negative sentiment associated with the activity. We have only seen that there seems to be more positive sentiment than negative sentiment associated with these all the subreddits we looked at.

Therefore we cannot accept/reject our hypothesis, that activity level changes in subreddits are positively correlated with the degree of positive or negative sentiment associated with the activity.
