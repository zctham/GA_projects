# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

# Project 3- Subreddit Classification
---
In this project, we will be looking at creating a binary classifier to classify two Reddit posts of choice. Reddit is a social news, content, and discussions website. Posts are organised according to subject into user-created 'subreddits'. Members submit content (such as images, texts, and links) to subreddits, which can be voted up ('upvote') or down ('downvote') by other members. As of June 2021, Reddit ranked among the most popular mobile social apps in the United States with almost 48 million monthly active users.

### Problem Statement 
---
With the increasing popularity of data, technology and their uses in the past decade, it seems that the age of technology is here to stay. Not only is the world learning to harness the power of data, it is also learning to live with it. It comes as no surprise that such a relatively new industry attracts many talents to join in and seek a career from within, be it for the lucrative remuneration, or its challenges. We will be using data from two subreddits, 'datascience' and 'dataengineering' to understand, from a career switcher's point of view, the key differences between the two and if the results will enable him/her to decide which path to pivot to, taking into account his/her skillsets, academic qualification and interests.

---
### Data Dictionary

|Feature |Type|Dataset|Description|
|---|---|---|--|
|title|str|datascience_posts/dataengineering_posts|title of reddit post|
|selftext|str|datascience_posts/dataengineering_posts|selftext of reddit post|
|subreddit|str|datascience_posts/dataengineering_posts|subreddit name|
|title lemmatized|str|datascience_posts/dataengineering_posts|title after lemmatizing|
|selftext lemmatized|str|datascience_posts/dataengineering_posts|selftext after lemmatizing|
|lemma_comb|str|datascience_posts/dataengineering_posts|merge of title lemmatized and selftext lemmatized| 

---
### Conclusions and Recommendations
---
With an accuracy score of 80%, the **Logistic Regression model with TfidfVectorizer** was the best performer among the models tested, albeit not by a huge margin. Among the tested models, TfidfVectorizers tend to score better than CountVectorizer models and random forest models have a high degree of overfit.

Even though the subreddit topics are closely related in nature, we can see through the top words in each posts that they do have their differences. Words in dataengineering reddit posts tend to steer towards technical terms and data engineering tools such as 'spark','snowflake', 'apache' and 'airflow'. These are tools which data engineers commonly use. 

On the other hand, top words in datascience reddit posts are more academic and analytical in nature. Words such as 'statistics', 'model', 'ml', 'dataset' are very relevant to what data scientists do on a daily basis. It is also interesting to note that there are some words such as 'university', 'degree', 'master', 'study', 'phd', which suggests that the entry barrier into this field is high and it is very academic in nature. This is to be expected with data science being a highly sought after industry as of recent years and data scientist roles being termed 'The Sexiest Job of the 21st Century'. 

To improve model accuracy, a bigger dataset with more vocabulary could be obtained. The industry is changing at a very rapid pace, with new machine learning models, data engineering tools being developed every few years to futher streamline processes, make learning about data easier and generally helps people be familiar with the concept of living with data. We could also look to increase the range of models to test on, such as K-Nearest-Neighbor, Support Vector Machine or explore using other classifier methods such as word similarities with Word2Vec or vector distances with GloVe.

