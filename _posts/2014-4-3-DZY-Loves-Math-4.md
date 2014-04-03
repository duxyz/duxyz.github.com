---
layout: post
category : solution
title: "DZY Loves Math 4"
tags : [math]
---
{% include JB/setup %}

虽然是jc大爷出的题，但为了骗流量，还是写一下题解吧。。

令$$S(n,m)=\sum_{i=1}^{m}\varphi(ni)$$

在\\(|\mu(n)|=1 \\)时，有$$\varphi(nk)=\sum_{d|(n,k)}\varphi(\frac{n}{d})\varphi(k)$$

这个考虑\\(\varphi(k)\\)与\\(\varphi(nk)\\)的倍数关系就能推出来了。。。

那么两边求和可以得


\begin{equation}
\begin{split} 
S(n,m)&=\sum_{k=1}^{m}\sum_{d|(n,k)}\varphi(\frac{n}{d})\varphi(k)\\\
&=\sum_{d|n}\varphi(\frac{n}{d})\sum_{k=1}^{\lfloor \frac{m}{d} \rfloor} \varphi(dk)\\\
&=\sum_{d|n}\varphi(\frac{n}{d})S(d,\lfloor \frac{m}{d} \rfloor)\\\
\end{split} 
\end{equation}

对于\\(\mu(n)=0\\)的情况，找到最大的那个\\( k|n\\),使\\(|\mu(k)|=1\\)，那么\\(S(n,m)=\frac{nS(k,m)}{k}\\)

还有$$S(1,m)=\frac{m(m+1)}{2}-\sum_{k \geq 2}S(1, \lfloor \frac{m}{k} \rfloor)$$

然后把小点的情况预处理出来之后，记搜就好了。

（其实我是看pe432题解的。。。）