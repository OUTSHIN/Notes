

## Gradient Descent for Linear Regression

![19072101](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/19072101.jpeg)

![19072102](https://github.com/OUTSHIN/Markdown_Image/raw/master/ML/19072102.jpeg)

While gradient descent can be susceptible to local minima in general, the optimization problem we have posed here for linear regression has only one global, and no other local, optima; thus gradient descent always converges (assuming the learning rate α is not too large) to the global minimum. Indeed, J is a convex quadratic function. Here is an example of gradient descent as it is run to minimize a quadratic function.

![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/xAQBlqaaEeawbAp5ByfpEg_24e9420f16fdd758ccb7097788f879e7_Screenshot-2016-11-09-08.36.49.png?expiry=1563840000000&hmac=t0hsH64eJ0NntZS-vtms0d7kCzsZlefTpa6lxte1s6w)

The ellipses shown above are the contours of a quadratic function. Also shown is the trajectory taken by gradient descent, which was initialized at (48,30). The x’s in the figure (joined by straight lines) mark the successive values of θ that gradient descent went through as it converged to its minimum.

