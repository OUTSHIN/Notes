## Cost function (Squared error function & Mean squared error)

- Most commonly used one for **regression problems**

$$
J(\theta_0,\theta_1)=\frac {1}{2m} \sum_{i=1}^n \left({h_\theta {}(x^{(i)})}-y^{(i)}\right)^2
$$

![1563245552416](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563245552416.png)

****

### Simplified 



![1563246854458](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563246854458.png)

### Introduction I

> Data (1,1), (2,2), (3,3) 【only have one Independent variable】

- When $\theta=1$ ,  $J(1)=0$

![1563258494315](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563258494315.png)

- When $\theta=0.5$ ,  $J(0.5)=0$.58

![1563258812073](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563258812073.png)

- When $\theta=0$ ,  $J(0)=\frac{14}{6}$

- ...
- Then according the $J(\theta1)$ function we can find a line that fit the fata well.

![1563259161114](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563259161114.png)



### Introduction II

- When have two Independent variable, that is the cost function looks like.

![1563331537685](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563331537685.png)

> Contour plot (轮廓图)

- When $\theta_0=800$, $\theta_1=-0.15$

![1563331763069](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1563331763069.png)





# Cost Function - Intuition II

A contour plot is a graph that contains many contour lines. A contour line of a two variable function has a constant value at all points of the same line. An example of such a graph is the one to the right below.

![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/N2oKYp2wEeaVChLw2Vaaug_d4d1c5b1c90578b32a6672e3b7e4b3a4_Screenshot-2016-10-29-01.14.37.png?expiry=1563494400000&hmac=hY_Eomld2kK_dGaD8y1b3J8RYHWq1Wn6Z9DYYQgEgvE)

Taking any color and going along the 'circle', one would expect to get the same value of the cost function. For example, the three green points found on the green line above have the same value for $J(\theta_0,\theta_1)$ and as a result, they are found along the same line. The circled x displays the value of the cost function for the graph on the left when $\theta_0 = 800 $and $\theta_1= -0.15$. Taking another h(x) and plotting its contour plot, one gets the following graphs:

![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/26RZhJ34EeaiZBL80Yza_A_0f38a99c8ceb8aa5b90a5f12136fdf43_Screenshot-2016-10-29-01.14.57.png?expiry=1563494400000&hmac=lCSeoJxZ9LeueYm3hVUxyaMTpyvFrj1K3Lezjj-xu8Q)

When $\theta_0= 360$ and $\theta_1= 0$, the value of $J(\theta_0,\theta_1)$ in the contour plot gets closer to the center thus reducing the cost function error. Now giving our hypothesis function a slightly positive slope results in a better fit of the data.

![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/hsGgT536Eeai9RKvXdDYag_2a61803b5f4f86d4290b6e878befc44f_Screenshot-2016-10-29-09.59.41.png?expiry=1563494400000&hmac=79hfTVEuolEwKc6oG1jWEn3Od80YZ3q4WW5xwg9cmUU)

The graph above minimizes the cost function as much as possible and consequently, the result of $\theta_1$and$ \theta_0$ tend to be around 0.12 and 250 respectively. Plotting those values on our graph to the right seems to put our point in the center of the inner most 'circle'.