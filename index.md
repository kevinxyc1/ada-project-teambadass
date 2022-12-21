---
layout: page
title: The Recipe For A Movie's Success 🎬
subtitle: Analysis of various factors that lead to high box office
cover-img: /assets/img/movie.jpeg
thumbnail-img: /assets/img/movie.jpeg
share-img: /assets/img/movie.jpeg
use-site-title: true
---

The global film industry is a **$100 billion worth industry**. There is a vast potential to earn money, and the producers are willing to sacrifice considerable costs to become a movie success. Pirates of the Caribbean: On Stranger Tides, the most expensive film, cost $379 million. With such an amount at your disposal, you may wonder how you should spend the money. Should you use them to get one of the biggest movie stars in your cast? For many, this may be tempting. One of the most famous actors, Tom Cruise, was rewarded $100,000,000 for his performance in Top Gun: Maverick. But was it worth it? Or could the money be better spent? 


### The Data Used:
We will be using the CMU Movie Summary Corpus which contains data on the revenue of **8 401 movies**. We will analyze this data to create a recipe for a successful movie.



### Goal:

In our initial analysis, we define the success of a movie in terms of box office revenue. To create a recipe for the production of a successful film, we have limited ourselves to five main research questions:

* Does the movie release date have a significant impact on the success of a film, and if so, what is the optimal release date concerning the time of the year? Subsequently, the question arises whether this result differs for different genres.
* How do the gender ratio and the fraction of ethnicities in the cast affect the success of a movie?
* Do certain actors have a significant positive or negative impact on the success of a movie?
* Is the length of a movie related to its success, and if so, in what way?
* Is the use of negatively connoted words, positively connoted words, and words related to violence in the movie plot associated with the success of the movie?

-----------------

## Release Date

This is the interactive plot:

<iframe src="assets/plot/genre-plot.html" width="100%" height="100%">Genre plot</iframe>

-----------------------

## Diversity

-----------------------

## Cast
In this analysis, we aim to investigate the influence of a movie's cast on its box office revenue. By analyzing the CMU Movie Summary Corpus dataset, we will explore the potential impact of individual actors and combinations of actors on a film's financial success. To further understand the relationship between cast and revenue, we will conduct network analysis to evaluate the roles of individual actors and actor combinations in generating revenue.

### Summary
- Our analysis found that actors are significant contributors to a movie's box office revenue, as seen in the linear regression model. 
- Our network analysis revealed that actors tend to form communities that frequently work together on films. 
- By examining these communities, we discovered that movies tend to have higher revenues when the cast is drawn from a single community, rather than mixing actors from multiple communities.

### Linear Regression
We are using linear regression to examine the relationship between a movie's cast and its box office revenue. By fitting a linear model to the data, we can determine the strength and direction of the relationship between these variables, as well as identify any potential confounding factors that may influence the relationship. Linear regression allows us to quantitatively estimate the impact of the individual actors on a movie's financial performance.

We have chosen to only include those who have appeared in more than 10 movies. This threshold of 10 has the advantage of excluding one-hit wonders from our analysis, which can help to ensure that our findings are more representative of the broader movie industry. While it is possible for actors who have appeared in fewer than 10 movies to have a significant impact on a film's financial performance, these cases are likely to be less reliable and may not accurately reflect broader trends in the industry. By limiting our analysis to actors who have a more established track record in the movie industry, we can confidently draw conclusions about the factors that contribute to financial success in the film industry. Overall, our findings will be more reliable and meaningful when we focus on experienced and reliable actors who have a strong track record in the industry.

<table>
  <tr>
    <th>Variable</th>
    <th>coef</th>
    <th>std err</th>
    <th>t</th>
    <th>P>|t|</th>
    <th>[0.025</th>    <th>0.975]</th>
  </tr>
  <tr>
    <td>Cate Blanchett</td>
    <td>107800000.0</td>
    <td>25000000.0</td>
    <td>4.305</td>
    <td>0.000</td>
    <td>58700000.0</td>
    <td>157000000.0</td>
  </tr>
  <tr>
    <td>Seann William Scott</td>
    <td>83170000.0</td>
    <td>23300000.0</td>
    <td>3.571</td>
    <td>0.000</td>
    <td>37500000.0</td>
    <td>129000000.0</td>
  </tr>
  <tr>
    <td>budget</td>
    <td>81760000.0</td>
    <td>3310000.0</td>
    <td>24.671</td>
    <td>0.000</td>
    <td>75300000.0</td>
    <td>88300000.0</td>
  </tr>
    <tr>
    <td>James Franco</td>
    <td>74500000.0</td>
    <td>24600000.0</td>
    <td>3.026</td>
    <td>0.003</td>
    <td>26200000.0</td>
    <td>123000000.0</td>
  </tr>
  <tr>
    <td>Johnny Depp</td>
    <td>60650000.0</td>
    <td>21000000.0</td>
    <td>2.890</td>
    <td>0.004</td>
    <td>19500000.0</td>
    <td>102000000.0</td>
  </tr>
  <tr>
    <td>Anna Faris</td>
    <td>58480000.0</td>
    <td>22600000.0</td>
    <td>2.593</td>
    <td>0.010</td>
    <td>14200000.0</td>
    <td>103000000.0</td>
  </tr>

</table>

One interesting finding from our analysis is that, among the top 10 coefficients with the highest magnitudes and p-values below 0.05, the only factors that appear to significantly influence movie revenue besides budget are the actors. This suggests that these actors make a significant contribution to the revenue. However, it's important to keep in mind that the contribution of an actor to revenue may not solely depend on their individual performance, but also on the combination of actors they appear with in a movie. For example, an actor may have a stronger influence on revenue when paired with certain co-stars, but a weaker influence when paired with others. This highlights the need to further analyze movie casts using network analysis techniques to gain a more nuanced understanding of the relationships between actors and their impact on revenue. For example, will Cate Blanchett rank among the top revenue-generating actors when we take actor communities into consideration?

Additionally, we should note that budget is a significant factor that can impact revenue, but is closely related to revenue itself and may not be the most informative when analyzing the contribution of individual actors. We will return to the role of budget in our analysis later.


### Network Analysis of Actors
In the context of analyzing the impact of actors on movie revenue, network analysis allows us to look at the connections between actors and how they may influence each other's contribution to revenue. By visualizing the relationships between actors as a network, we can identify patterns and communities within the movie industry, and gain a more nuanced understanding of the ways in which actors contribute to revenue. Overall, incorporating network analysis into our analysis of actor contributions to movie revenue can provide valuable insights and help us better understand the complex relationships within the data.

<img src="assets/img/net1.png" class="center"/>

- We have created a flavor network graph where the nodes represent actors and the edges represent the movies that they have appeared in together. The size of the nodes reflects the average revenue of the movies that the actor has appeared in, while the width of the edges indicates the number of times that the actors have appeared in a movie together.
- This graph includes 61 actors and 256 connections. In the following section, we will delve deeper into this visualization to gain insights into the relationships between actors and their influence on revenue.

- To gain a deeper understanding of the relationships depicted in our flavor network graph, we will utilize network analysis techniques to identify communities of actors who frequently appear in movies together and to measure the centrality of each actor in the network.

- To identify communities of actors, we will apply a network community detection algorithm. This will allow us to identify groups of actors who tend to appear in movies together and examine how these communities contribute to movie success. In particular, we will use the Louvain method to identify the "best" partition of communities in the network. By identifying these actor communities, we can gain a more detailed understanding of the patterns of collaboration and the impact of different actor combinations on movie revenue.

<img src="assets/img/net2.png" class="center"/>

- Using the Louvain method, we have partitioned the network of actors into six distinct communities based on their connections through movies. This suggests that there are subgroups of actors who tend to work together more frequently. 
- Upon further analysis, we found that the average revenue generated by actors within each community varies, with some actors standing out as particularly successful in terms of average revenue.
- While we have not yet explored the potential reasons for these patterns, some possibilities could include the genre or type of film associated with each community, the fame or recognition of the actors within the industry, or the social connections between the actors. 
- For the purpose of our analysis, we are interested in examining how revenue is affected by including actors from different communities versus including actors from the same community. This will allow us to gain insights into the impact of actor combinations on movie revenue.

- We will plot the initial flavor graph again, but this time we will distinguish between connections within communities and those between communities. This will allow us to see the patterns of collaboration within and between different actor communities and better understand the impact of these connections on movie revenue. 

<img src="assets/img/flavour_plot2.png" class="center"/>

In this revised flavor plot, we have highlighted the edges that cross between two different actor communities in yellow. The other edges have a colour corresponding to their community. Our goal is to determine whether there is a difference in revenue when creating a movie cast with actors from a single community versus actors from multiple communities. To do this, we will analyze the patterns of collaboration within and between communities and examine the impact of these connections on movie revenue. Let's delve deeper into this analysis!

To gain a deeper understanding of the relationships between actors and their impact on revenue, we will divide the movies into two categories: those with a cast that is largely concentrated within a single actor community, and those with a cast that is more evenly distributed among multiple communities. This will enable us to compare the performance of movies with more homogenous casts versus those with more diverse casts, and determine whether there is a relationship between cast composition and revenue. By analyzing these two categories of movies, we can gain insights into the potential benefits and drawbacks of casting actors from a single community versus a mix of communities, and how this may impact the success of a movie.

We observed a significant difference in the average revenue between movies with a cast that is largely concentrated within a single community and those with a more evenly distributed cast. To more accurately assess the impact of cast composition on revenue, it is important to consider other factors that could influence the results. One way to control for these potential confounds is through the use of matching, which allows us to compare movies with similar characteristics. By controlling for these other factors, we can more confidently attribute any observed differences in revenue to the effect of cast composition. This will help us better understand the relationship between cast composition and movie revenue and identify any trends or patterns. The following plots show a difference-in-difference approach on matched and unmatched data. 

<img src="assets/img/evenly_vs_majority.png" class="center"/>

Our revised difference-in-differences analysis revealed that movies with a majority of actors from a specific community have a significant impact on box office revenue. The treatment effect was substantial in both estimates, with and without matching, at $51620924.7 and $39424016.7, respectively. The difference between the two estimates was approximately -23.63%, and both estimates were statistically significant with a p-value of 0.0.

In this analysis, we chose to exclude budget as a matching variable because it is likely closely related to actor cast. Using budget as a matching variable could potentially control for the effect of the actor cast, making it difficult to determine the independent effect of the actor cast on revenue. However, budget is an important factor that can influence a movie's production value and overall appeal to audiences. For example, a movie with a high budget may be more likely to generate revenue due to a larger marketing budget and wider distribution.

Although we do not have data on how budgets were specifically allocated for each movie, we speculate that a significant portion of the film's budget is often used for casting. It is possible that it is more costly to assemble a cast primarily from one community, which is irrelevant for our analysis of how movie cast affects revenue made.

-----------------------

## Runtime

Blockbuster movies ($400 million+) have, on average, 10.1% longer runtime than non-blockbuster movies.
Movies with short runtime (<80min) have 54.8% less revenue than non-short movies.

-----------------------

## Plot Summary

-----------------------

## Conclusion & Our recipe:

-------------
