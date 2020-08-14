# Project 3: Sentiment Analysis of COVID-19 Social Media Posts
#### Project completed by Paulene Barnes, Ari Kerdell & Matt Williams
#### August 14th, 2020
 
### Problem Statement:

The COVID-19 response has been largely regional and state-based in nature. Some states have enacted strictly enforced stay-at-home policies, while others have provided guidelines. Here we will compare the sentiment analysis of social media posts across the US by state, and compare them to both the local policies on social distancing and the occurrences of the pandemic in those areas. We decided that we were only going to look at Twitter and Reddit data taken from July to determine how each state was feeling about the coronavirus.
 
---

### Contents:
- [Data Sources, Cleaning, Dictionaries & EDA](#Data_Sources)
- [Modeling](#Modeling)
- [Presentation](#Presentation)
- [Conclusions and Recommendations](#Conclusions_and_Recommendations)

---
### Data Cleaning and Exploratory Data Analysis (EDA):
#### Twitter Data and EDA:
We gathered Twitter data from https://ieee-dataport.org/open-access/coronavirus-covid-19-geo-tagged-tweets-dataset which is a subset of https://ieee-dataport.org/open-access/coronavirus-covid-19-tweets-dataset. Both of these datasets were put together by Rabindra Lamsal School of Computer and Systems Sciences, JNU. We decided that we would use the subset because our specific problem statement requires geographic information and the subset filtered out non-geotagged tweets for us. The data taken from this site came in the form of 1 csv of tweet IDs per day. A hydrator was required to gather all the data back in by using the tweet IDs. The hydrator we used was from Documenting the Now. (2020). Hydrator [Computer Software]. Retrieved from https://github.com/docnow/hydrator. After retrieving all of the data from the hydrator, the next step was to concatenate all of the daily csvs into one larger July csv. We found that most of the columns of data that we retrieved from the hydrator was unnecessary and kept only information pertaining to location and text. Additionally, we removed all of the remaining tweets that were not from U.S. states.
 
#### Reddit Data and EDA:
Reddit data was compiled using the Pushshift API. On the Reddit website, the majority of the coronavirus or COVID-19 related posts are categorized into subreddits for each state. Searches on Reddit were conducted using the state’s full name, abbreviated name, “coronavirus”, and/or “COVID-19”. Subreddit posts were only pulled for the month of July for analysis. Once the posts were pulled, all 50 states including Washington DC were compiled into a single data frame for cleaning and EDA. 
 
For the EDA process, a variety of features were assessed and visualized. These features include 1) the number of posts or tweets per state, 2) word counts for each subreddit title and Twitter, 3) most frequent words across each state for each platform, and 4) the most frequent bi-grams across each platform across the US as a whole. 
 
#### Policy Data:
State policy data was taken from https://www.kff.org/coronavirus-covid-19/issue-brief/state-data-and-policy-actions-to-address-coronavirus/ and converted into a pandas dataframe so that we could compare policy, health, and social media data side by side. The csv included policy on reopening, stay at home orders, emergency declaration, large gatherings, and public mask requirements.
 
#### Health Data: 
Health data was taken from https://covidtracking.com/api/v1/states/daily.csv and included data on total tests, positive rest rate, total hospitalized, total positive cases, and a lot of other important health data for each state. The data dictionary can be found here: https://covidtracking.com/about-data/data-definitions  
 
#### Tableau:

---

### Modeling:
#### VADER Sentiment Analysis:
Our group used VADER (Valence Aware Dictionary and sEntiment Reasoner) to assess sentiment of each individual Twitter and Reddit post. We picked VADER over other sentiment analysis tools because it is especially proficient on social media posts. Overall, the compound sentiment scores from Twitter were more positive than the compound sentiment scores from the subreddit posts. 
 
#### Random Forest 
Random forest classifier was used to predict whether or not the overall sentiment score for each tweet or subreddit post was positive or negative. For the subreddit posts, this model had an accuracy score of 0.616 for training data and 0.568 for testing data. For Twitter tweets, the model essentially predicted the baseline data with a training accuracy of 0.76 and a testing accuracy of 0.76.
 
#### Linear Regression
Linear regression was used to predict the total deaths due to coronavirus using sentiment scores, policy data, and health data. This linear regression model had an R<sup>2</sup> score of 0.98 for training data and 0.98 for testing data using Reddit post sentiment scores in addition to policy and health information for each state. This means that 0.98 of the data was accounted for in the model. Additionally, using linear regression with Twitter data resulted in an R<sup>2</sup> score of 0.98 for training and 0.95 for testing.

---

### Presentation:
---

### Conclusions and Recommendations:

COVID-19 continues to evolve as more information is gathered and new policies are set in place. Some recommendations and next steps for the continuation of this project include, but are not limited to, exploring data prior to July 2020 as well as in future months, analysing the policy information by state, further exploring correlation between health and policy mandates, and deeper exploration between the correlation of sentiment scores and policy information. Additionally, Reddit and Twitter were the only social media platforms assessed in the project. Future projects may find it beneficial to explore other social media platforms.
 

 
 
 

