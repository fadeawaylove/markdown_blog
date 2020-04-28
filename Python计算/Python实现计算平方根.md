### 1.二分法

#### 原理
> 举例计算数字$num$的平方根：
> 1.判断：如果$num>1$，计$low=1$，$high=num$，否则计$low=num$，$high=1$；
> 2.计算$mid={\frac{high+low}{2}}$，如果$mid^2>high$，那么更新$high$的值为$mid$，否则更新low的值为$mid$，重复这个步骤直到$|mid^2-num|<\delta$($\delta为可容忍的最小误差$)

#### 代码实现
```python
def dichotomy_sqrt(x):
    if x > 1:  
        a = 1.0
        b = x
    else:
        a = x
        b = 1.0
    y = (a + x)/2
    while abs(y * y - x) > 1e-6:
        if y * y > x:
            b = y
            y = (y + a) /2
        else:
            a = y
            y = (y + b) /2
    return y

```

### 2.牛顿迭代法

#### 原理
> 从函数上分析：就是求$x^2-num=0$的近似解
> 从几何上分析：就是求抛物线$g(x)=x^2-num$与$X$轴的交点
> 假设$x_0$为$g(x)$与$X$轴的交点，我们的工作就是让近似解$x$不断的逼近$x_0$

![牛顿迭代公式](https://raw.githubusercontent.com/fadeawaylove/article-images/master/%E7%89%9B%E9%A1%BF%E8%BF%AD%E4%BB%A3%E5%85%AC%E5%BC%8F-1588058540.png)

> 这里我们将$f(x)=g(x)$带入公式，可得
> $$x_{k+1}=\frac{1}{2}(x_k+\frac{num}{x_k})$$
> 使用这个公式进行迭代，直至$|x_{k+1}-x_{k}|<\delta$($\delta为可容忍的最小误差$)

#### 代码实现

```python
def Newton_sqrt(num, x_k=1):
    if abs(num/x_k - x_k) < 1e-6:
        return num/x_k
    else:
        y = (num/x_k + x_k)/2
        return Newton_sqrt(num, y)
```
