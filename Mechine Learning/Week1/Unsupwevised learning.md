

## Unsupervised Learning

Unsupervised learning allows us to approach problems with little or no idea what our results should look like. We can derive structure from data where we don't necessarily know the effect of the variables.

We can derive this structure by clustering the data based on relationships among the variables in the data.

With unsupervised learning there is no feedback based on the prediction results.

**Example:**

**Clustering**: Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.

**Non-clustering**: The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a [cocktail party](https://en.wikipedia.org/wiki/Cocktail_party_effect)).



### Clustering

- Genes

![Genes analysis](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563188024574.png)

- Unsupervised Learning or clustering is used for a bunch of other applications. It's used to organize large computer clusters. That is large computer clusters and trying to figure out which machines tend to work together and if you can put those machines together, you can make your data center work more efficiently. 
- This second application is on social network analysis. So given knowledge about which friends you email the most or given your Facebook friends or your Google+ circles, can we automatically identify which are cohesive groups of friends, also which are groups of people that all know each other? 
- Market segmentation. Many companies have huge databases of customer information. So, can you look at this customer data set and automatically discover market segments and automatically group your customers into different market segments so that you can automatically and more efficiently sell or market your different market segments together? Again, this is Unsupervised Learning because we have all this customer data, but we don't know in advance what are the market segments and for the customers in our data set, you know, we don't know in advance who is in market segment one, who is in market segment two, and so on. But we have to let the algorithm discover all this just from the data. 
- Finally, it turns out that Unsupervised Learning is also used for surprisingly astronomical data analysis and these clustering algorithms gives surprisingly interesting useful theories of how galaxies are formed.



![Four kinds of cluster analysis](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563188131007.png)



### Non-clustering 

- Cocktail party problem


![Cocktail party problem](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563188734332.png)

> Just use this code you can allows the machine to separate two sounds from one recording.


![Code of "Cocktail party problem"](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563187003945.png)



## Q&A

1. Why "Cocktail party problem" is non-clustering.

	> In the cocktail problem which is indeed non-clustering, we know in advance that one sound is music and the other is human voice. We are classifying what is what. Whereas in a clustering problem, we do not typically know what is present in the data. A data is given without any labels to us and we ask the algorithm to find structure (clusters) in it.
1. 