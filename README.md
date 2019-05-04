<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
<script></script>

# Image Processing HW1
> Rotate 30 degrees without using rotate library

Source is a single English letter image and a nature image

![](https://i.imgur.com/x6mPnAX.png) ![](https://i.imgur.com/SLSwhLT.png)


## Method

$(x0,y0)$ is old coordinate and $(x1,y1)$ is new coordinate.

> $x1 = x0 \times cos\theta - y0 \times sin\theta$
> $y1 = x0 \times sin\theta + y0 \times cos\theta$

In this method, some pixels will not get value

![](https://i.imgur.com/M6uVwf7.png)

So I use inverse mapping

![](https://i.imgur.com/yexCTcq.jpg)

The equation will become
> $x0 = x1 \times cos\theta + y1 \times sin\theta$
> $y0 = -x1 \times sin\theta + y1 \times cos\theta$

## Interpolation
And then I use **Nearest Neighbor Interpolation** and **Bilinear Interpolation**

#### Nearest Neighbor Interpolation
> I use `np.around()` to get the most close pixel

![](https://i.imgur.com/pGwxlht.jpg)
#### Bilinear Interpolation
>  $x1 = (0，0) + d1 * ((1，0) – (0，0))$
>  $x2 = (0，1) + d1 * ((1，1) – (0，1))$
>  $(x，y)= x1+ d3 * (x1- x2)$

![](https://i.imgur.com/tZLRzzG.jpg)


## Result 
![](https://i.imgur.com/pleDUUs.png) ![](https://i.imgur.com/n5U8LAk.png)

![](https://i.imgur.com/WKuLcnQ.png) ![](https://i.imgur.com/gdrt7XM.png)

**Different between NN and BI**
![](https://i.imgur.com/aOhrln6.png) ![](https://i.imgur.com/HQNlinT.png)


