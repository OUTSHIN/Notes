



##　Ｇradient descent

![1907181](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1907181.jpeg)

![1907183](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1907183.jpeg)
$$
\theta_j:=\theta_j-\alpha{\frac{\partial} {\partial\theta_j}}J(\theta_0+\theta_1)
$$

- $:=$  
  - Assignment （赋值）
- $\alpha$  
  - Learning rate. (control the descent rate (step's size))

### Simultaneous update (同时更新)

![1907182](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/1907182.jpeg)

$$
temp0:=\theta_0-\alpha{\frac{\partial} {\partial\theta_0}}J(\theta_0+\theta_1)
$$

$$
temp1:=\theta_1-\alpha{\frac{\partial} {\partial\theta_1}}J(\theta_0+\theta_1)
$$

$$
\theta_0:=temp0
$$

$$
\theta_1:=temp1
$$

> Update the $\theta_0$ and $\theta_1$ at the same time.



### Intuition



![19071806](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/19071806.jpeg)

> The introduction graph.

![](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/19071805.jpeg)

> If the $\alpha$ is so big, it may fail to converge,or even diverge.

![](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/19071804.jpeg)

> If already at the local minimize position, after running the update **does not change** the location.

![19071807](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/19071807.jpeg)

> As we approach local minimum, this derivative term will automatically get smaller.
>   越接近局部最低点，每次更新的step越小，因为倒数值变小了

