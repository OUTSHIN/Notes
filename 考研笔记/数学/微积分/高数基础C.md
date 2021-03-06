#### /极限

##### 定义

- 定义的等价

  > 证明函数$\frac{1}{x}sin\frac{1}{x}$在(0,1)内无界，但$x\rightarrow0^+$时这个函数不是无穷大 *[答案](https://md-imag.oss-accelerate.aliyuncs.com/image-20200209223343541.png)*

##### 性质

- 函数极限（保号性）

  > 设$f'(1)=0,且\lim_{n\rightarrow1}\frac{f'(x)}{(x-1)^3}=2$, 则f(x)在x=1处 _*[答案](https://md-imag.oss-accelerate.aliyuncs.com/image-20200208120021497.png)*_
  >
  > A: 不取极值	B: 取极大值	C: 取极小值	D: 是否取极值无法确定
  
  
  
- 海涅定理

  > 求$lim_{n\rightarrow\infin}\frac{ln\,n}{n}$. *[答案](https://md-imag.oss-accelerate.aliyuncs.com/image-20200208191934118.png)*

#### 无穷小

- 定义运算

  ![image-20200209204104894](https://md-imag.oss-accelerate.aliyuncs.com/image-20200209204104894.png)

  ![image-20200209204254186](https://md-imag.oss-accelerate.aliyuncs.com/image-20200209204254186.png)

#### 无穷大和无界

  ![image-20200209223343541](https://md-imag.oss-accelerate.aliyuncs.com/image-20200209223343541.png)

#### 单调有界准则

### ![](https://md-imag.oss-accelerate.aliyuncs.com/20200211103338.png)

  ![](https://md-imag.oss-accelerate.aliyuncs.com/20200211104926.png)

  > 注意需要先证明xn恒大于0后才可以使用不等式sinx<x

#### 连续性与间断性

##### 运算

![](https://md-imag.oss-accelerate.aliyuncs.com/20200213104030.png)

##### 证明

![](https://md-imag.oss-accelerate.aliyuncs.com/20200213111417.png)

![20200213112553](https://md-imag.oss-accelerate.aliyuncs.com/20200213112553.png)

![20200213113238](https://md-imag.oss-accelerate.aliyuncs.com/20200213113238.png)

> 考点11最后

##### 性质

- 零点定理

  ![20200213115752](https://md-imag.oss-accelerate.aliyuncs.com/20200213115752.png)



#### 导数

##### 导数和连续

![20200215115407](https://md-imag.oss-accelerate.aliyuncs.com/20200215115407.png)

##### 高阶导数(*注意求导对象*)

![20200216095633](https://md-imag.oss-accelerate.aliyuncs.com/20200216095633.png)

##### 应用

![20200218093706](https://md-imag.oss-accelerate.aliyuncs.com/20200218093706.png)

##### 方程的根

> 设当x>0时，方程$kx+\frac{1}{x^2}=1$有且只有一个根，求k的取值范围. *[答案](https://md-imag.oss-accelerate.aliyuncs.com/20200219103659.png)*

#### 中值定理

---

##### 辅助函数

> 小心等价变换，例如四则运算，幂函数相乘，指数函数的化简等等

1. $见f(x)f'(x),做 F(x)=f^2(x)$
2. $见[f'(x)]^2+f(x)f''(x),做 F(x)=f(x)f'(x)$
3. $见f'(x)+f(x)g'(x),做 F(x)=f(x)e^{g(x)}$
   1. $f'(x)-f(x)=0,则g(x)=-x, 令F(x)=f(x)e^{-x}$
   2. $f'(x)+f(x)=0,则g(x)=x, 令F(x)=f(x)e^x$
   3. $f'(x)+kf(x)=0,则g(x)=kx, 令F(x)=f(x)e^{kx}$

