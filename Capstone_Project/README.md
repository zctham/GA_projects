<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Capstone Project: What's Next?: Anime Recommender System
## Introduction

### Problem Statement

Recommender systems has been a huge portion of our lives. In the last few decades alone, the rise of Youtube, Amazon, Spotify, Netflix and other similar web services are unavoidable in our daily online journeys. The significance of recommender systems is further emphasised in the famous Netflix challenge in 2006, where top coders were given the challenge of improving Netflix's own recommender system algorithm, with the grand prize of 1 million dollars given to whichever team is able to get a higher RMSE score.

In a very general way, recommender systems are algorithms aimed at suggesting relevant items to users (items being movies to watch, text to read, products to buy or anything else depending on industries). When users feel that items recommended are relevant to them, there is higher propensity for users to 'like' or purchase an item, which in turn increases viewership or revenue for companies. It is not far-fetched to say that recommender systems play a huge part in ensuring a companies' survival and continuity.

In this capstone project, we will be looking into recommendation system for anime titles. While this may not translate into earnings of any sort for any company, the algorithm used will be largely similar to what is being deployed in industries today. Measure of success will be evaluated with a RMSE score and a metric 'MAP@K' or 'Mean Average Precision at k', which translates to how many anime titles are relevant out of 'k' number of anime titles recommended. 

Dataset for the project (rating dataset) can be found [here](https://www.kaggle.com/CooperUnion/anime-recommendations-database) and [here](https://www.kaggle.com/hernan4444/anime-recommendation-database-2020).

Dataset for anime_clean can be found [here](https://www.kaggle.com/thamzhicong/anime-clean).

## Executive Summary

We attempted to produce anime title recommendations using the content based filtering and collaborative based filtering approaches.

Content based approach was done using a mixture of TVIDF Vectorizer to turn features like genres and synopsis into vectors, before cosine similarity was used to compute for anime titles with the most similarity. As the number of features were limited, future steps involve incorporating more features into the content based recommender to improve similarity score.

For collaborative filtering, we used the [surprise](https://surprise.readthedocs.io/en/stable/index.html) library to use different models from memory based techniques and model based techniques. Our top-performing model was the SVD (with a RMSE of 1.276 and MAP@10 of 0.917). Using the best model, we predicted a list of top anime titles that were sorted based on predicted scores. A brief search on [www.myanimelist.net](www.myanimelist.net) would show that the recommended titles were quite similar in terms of storyline, which is why similar users have rated them highly.


### Model Evaluation

<table class="dcf-table dcf-table-responsive dcf-table-bordered dcf-table-striped dcf-w-100%">
	<caption>Model Results</caption>
	<thead>
		<tr>
			<th class="dcf-txt-center" data-label="Model" scope="col">Model</th>
			<th class="dcf-txt-center" data-label="RMSE" scope="col">RMSE</th>
			<th class="dcf-txt-center" data-label="MAE" scope="col">MAE</th>
			<th class="dcf-txt-center" data-label="MAP@10" scope="col">MAP@10</th>
			<th class="dcf-txt-center" data-label="MAR@10" scope="col">MAR@10</th>
			<th class="dcf-txt-center" data-label="F1@10" scope="col">F1@10</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td class="dcf-txt-center" data-label="Model">KNNBasic</td>
			<td class="dcf-txt-center" data-label="RMSE">1.519</td>
			<td class="dcf-txt-center" data-label="MAE">1.176</td>
			<td class="dcf-txt-center" data-label="MAP@10">0.901</td>
			<td class="dcf-txt-center" data-label="MAR@10">0.719</td>
			<td class="dcf-txt-center" data-label="F1@10">0.800</td>
		</tr>
		<tr>
			<td class="dcf-txt-center" data-label="Model">KNNWithMeans</td>
			<td class="dcf-txt-center" data-label="RMSE">1.406</td>
			<td class="dcf-txt-center" data-label="MAE">1.066</td>
			<td class="dcf-txt-center" data-label="MAP@10">0.922</td>
			<td class="dcf-txt-center" data-label="MAR@10">0.735</td>
			<td class="dcf-txt-center" data-label="F1@10">0.818</td>
		</tr>
		<tr>
			<td class="dcf-txt-center" data-label="Model">BaselineOnly</td>
			<td class="dcf-txt-center" data-label="RMSE">1.302</td>
			<td class="dcf-txt-center" data-label="MAE">0.996</td>
			<td class="dcf-txt-center" data-label="MAP@10">0.886</td>
			<td class="dcf-txt-center" data-label="MAR@10">0.832</td>
			<td class="dcf-txt-center" data-label="F1@10">0.858</td>
		</tr>
		<tr>
			<td class="dcf-txt-center" data-label="Model">SVD</td>
			<td class="dcf-txt-center" data-label="RMSE">1.276</td>
			<td class="dcf-txt-center" data-label="MAE">0.976</td>
			<td class="dcf-txt-center" data-label="MAP@10">0.917</td>
			<td class="dcf-txt-center" data-label="MAR@10">0.804</td>
			<td class="dcf-txt-center" data-label="F1@10">0.856</td>
		</tr>
		<tr>
			<td class="dcf-txt-center" data-label="Model">NMF</td>
			<td class="dcf-txt-center" data-label="RMSE">1.692</td>
			<td class="dcf-txt-center" data-label="MAE">1.360</td>
			<td class="dcf-txt-center" data-label="MAP@10">0.999</td>
			<td class="dcf-txt-center" data-label="MAR@10">0.608</td>
			<td class="dcf-txt-center" data-label="F1@10">0.756</td>
		</tr>
	</tbody>
</table>


## Conclusion and Future steps

We have explored using content and collaborative filtering to recommend anime titles to users. Content based filtering focuses on using item features to recommend similar items to users. Strengths of content based filtering include ease of implementation compared to collaborative based filtering and recommendations are highly relevant to the user. One shortcoming with content based filtering is that users will only be recommended items that they have searched or purchased before and not anything new. In other words, there is a lack of novelty and serendipity.

Collaborative based filtering seeks to tap into similar users or users who rate in a similar fashion to predict how other users may rate items they have not interacted with before. Strengths of the collaborative based filtering include aiding users to discover items that they never thought they may like and not much domain knowledge is needed. Weaknesses include having to overcome the 'cold-start' problem, which is when there are new user or items in the market and there are no user ratings available for such items. 

While content and collaborative based filtering are not the only approaches for recommender systems, they are widely considered to be the most commonly used and understood approaches. To complement the shortcomings of each other, there is another approach called the hybrid filtering approach, which combines both the content and collaborative based filtering to get a better relevance score and make recommendations more relevant and less 'boring'. 

While there may be metrics to help us have an idea how good our recommendations are, the best form of understanding the result of our recommendations is only through user testing. 

Future steps include implementing a hybrid based anime recommender and doing user testing.                      
