---
name: Celebrity Tweet Emotion Analysis
tools: [Pytorch, Gephi]
image: /images/twitter_emotion.svg
description: Analysis of celebrity tweet emotions by using the method of clustering and topic generation using SentenceBert embeddings.
---

# The project was developed in following process<br>
### Dataset selection
Tweets Dataset - Top 20 most followed users in Twitter social platform https://dataverse.harvard.edu/dataset.xhtml?id=3047332 <br>
I used this mostly because, number of tweets per person ration in the dataset was pretty high, which gives better clustering.

### Preprocessing of the dataset<br>
1. Filter out all the tweets, not in English, the language column of the dataset is used to accomplish this.
2. Removed URLs from all the files.
3. Replace the # and @ symbol with '' because hashtag and mention could contain contextual info.

### Generating embeddings <br>
I have tried using a multiple sentence transformer to get the contextual embeddings of the tweet data, and further employed Uniform Manifold Approximation and Projection (UMAP) technique to reduce dimension and aid in visualizing the clusters of twitter emotions.
Based on this clustering I was able to find choose the best sentence transformer for this task. (all-mpnet-base-v2 based on the results)<br>
1. Clustering in all-distilroberta-v1 embedding space
![preview](/images/graph_1.png)
2. Clustering in all-mpnet-base-v2 embedding space
![preview](/images/graph_2.png)

### Clustering and result<br>
Finally, HDBSCAN technique was used on these generated contextual embeddings to get a high-density hierarchical clustering to get topic representation (in numbers). Furthermore, Gephi was used to create a network graph for the celeb to topic clustering graph.

![preview](/images/tweet.png)


<p class="text-center">
{% include elements/button.html link="https://github.com/Pavan-pk/celeb-tweet-emotion-analysis" text="Project repository" %}
</p>