---
layout: page_mathjax
title: Mathematical Formula Demos
category: Technical
tags: Project
description: 数学公式Web展现的例子
---
方程组 \begin{aligned} \dot{x} & = \sigma(y-x) \\ \dot{y} & = \rho x - y - xz \\ \dot{z} & = -\beta z + xy \end{aligned}

求和 $$\sum_{i=1}^n a_i=0$$ $$f(x)=x^{x^x}$$

微分 $$\frac{\partial u}{\partial t} = h^2 \left( \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} + \frac{\partial^2 u}{\partial z^2}\right)$$

薛定谔方程 $$ i\hbar\frac{\partial \psi}{\partial t} = \frac{-\hbar^2}{2m} \left( \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + \frac{\partial^2}{\partial z^2} \right) \psi + V \psi$$

\mbox{text} 标签的使用 $$\mbox{对任意的$x>0$}, \mbox{有 }f(x)>0. $$

画表格线
$$
\begin{array}{c|lcr}
n & \text{Left} & \text{Center} & \text{Right} \\
\hline
1 & 0.24 & 1 & 125 \\
2 & -1 & 189 & -8 \\
3 & -20 & 2000 & 1+10i \\
\end{array}
$$

积分表示 
$$
\[ \int_0^{+\infty} x^n e^{-x} \,dx = n!.\] \[ \int \cos \theta \,d\theta = \sin \theta.\] \[ \int_{x^2 + y^2 \leq R^2} f(x,y)\,dx\,dy = \int_{\theta=0}^{2\pi} \int_{r=0}^R f(r\cos\theta,r\sin\theta) r\,dr\,d\theta.\] \[ \int_0^R \frac{2x\,dx}{1+x^2} = \log(1+R^2).\] \[ \int \!\!\! \int_D f(x,y)\,dx\,dy.\] \[ \int \int_D f(x,y)\,dx\,dy.\]
$$
最后来一段连贯的
$$
One would typeset this in LaTeX by typing In non-relativistic wave mechanics, the wave function $\psi(\mathbf{r},t)$ of a particle satisfies the \emph{Schr\"{o}dinger Wave Equation} \[ i\hbar\frac{\partial \psi}{\partial t} = \frac{-\hbar^2}{2m} \left( \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + \frac{\partial^2}{\partial z^2} \right) \psi + V \psi.\] It is customary to normalize the wave equation by demanding that \[ \int \!\!\! \int \!\!\! \int_{\textbf{R}^3} \left| \psi(\mathbf{r},0) \right|^2\,dx\,dy\,dz = 1.\] A simple calculation using the Schr\"{o}dinger wave equation shows that \[ \frac{d}{dt} \int \!\!\! \int \!\!\! \int_{\textbf{R}^3} \left| \psi(\mathbf{r},t) \right|^2\,dx\,dy\,dz = 0,\] and hence \[ \int \!\!\! \int \!\!\! \int_{\textbf{R}^3} \left| \psi(\mathbf{r},t) \right|^2\,dx\,dy\,dz = 1\] for all times~$t$. If we normalize the wave function in this way then, for any (measurable) subset~$V$ of $\textbf{R}^3$ and time~$t$, \[ \int \!\!\! \int \!\!\! \int_V \left| \psi(\mathbf{r},t) \right|^2\,dx\,dy\,dz\] represents the probability that the particle is to be found within the region~$V$ at time~$t$.
$$
