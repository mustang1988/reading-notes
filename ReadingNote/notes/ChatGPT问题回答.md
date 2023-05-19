```ad-question
title: 反向传播算法的四个基本方程

反向传播算法是一种训练深度神经网络的方法。它通过利用链式法则，从网络的输出层向输入层反向传播误差，并在隐藏层更新权值，以使网络的输出更接近正确的结果。

反向传播算法的四个基本方程如下：

1.  误差项（损失函数）对输出层的节点输出的导数： $$\delta_{out} = \frac{\partial L}{\partial z_{out}}$$ 其中 L 是误差项，z_{out} 是输出层的节点输出。
    
2.  误差项对隐藏层的节点输出的导数： $$\delta_{hidden} = \frac{\partial L}{\partial z_{hidden}} = \delta_{out} \times w_{out} \times \sigma'(z_{hidden})$$ 其中 w_{out} 是从隐藏层到输出层的权值，δ_{hidden} 是隐藏层的误差项，δ_{out} 是输出层的误差项，σ'(z_{hidden}) 是隐藏层节点输出的导数。
    
3.  权值对误差项的导数： $$\frac{\partial L}{\partial w} = a_{in} \times \delta_{out}$$ 其中 a_{in} 是输入层的节点输出，w 是从输入层到输出层的权值。
    
4.  权值更新： $$w = w - \alpha \frac{\partial L}{\partial w}$$ 其中 α 是学习率，控制权值更新的速度。

```

```ad-question
title: 任意连续函数都可以进行傅里叶级数展开，这个说法对吗
这个说法是正确的。根据傅里叶级数的定义，任何周期函数都可以展开为正弦和余弦函数的无限和，而任意连续函数都可以通过构造一个周期为 $2\pi$ 的函数来进行傅里叶级数展开。这个构造方法被称为周期延拓。

具体来说，如果 $f(x)$ 是定义在区间 $[-\pi, \pi]$ 上的连续函数，那么可以通过将 $f(x)$ 周期地延拓到整个实数轴上，得到一个以 $2\pi$ 为周期的函数 $F(x)$，即 $F(x) = f(x-k2\pi)$，其中 $k$ 是任意整数。然后，$F(x)$ 可以表示为正弦和余弦函数的无限和：

$$F(x) = \frac{a_0}{2} + \sum_{n=1}^\infty a_n \cos(nx) + b_n \sin(nx)$$

其中

$$a_0 = \frac{1}{2\pi} \int_{-\pi}^\pi f(x) dx$$

$$a_n = \frac{1}{\pi} \int_{-\pi}^\pi f(x) \cos(nx) dx, \quad n \geq 1$$

$$b_n = \frac{1}{\pi} \int_{-\pi}^\pi f(x) \sin(nx) dx, \quad n \geq 1$$

由于 $F(x)$ 是以 $2\pi$ 为周期的函数，因此这个展开式也适用于 $f(x)$。这就是任意连续函数可以进行傅里叶级数展开的原因。
```


