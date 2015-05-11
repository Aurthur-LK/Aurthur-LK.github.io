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

$$
% outer vertical array of arrays
\begin{array}{c}
% inner horizontal array of arrays
\begin{array}{cc}
% inner array of minimum values
\begin{array}{c|cccc}
\text{min} & 0 & 1 & 2 & 3\\
\hline
0 & 0 & 0 & 0 & 0\\
1 & 0 & 1 & 1 & 1\\
2 & 0 & 1 & 2 & 2\\
3 & 0 & 1 & 2 & 3
\end{array}
&
% inner array of maximum values
\begin{array}{c|cccc}
\text{max}&0&1&2&3\\
\hline
0 & 0 & 1 & 2 & 3\\
1 & 1 & 1 & 2 & 3\\
2 & 2 & 2 & 2 & 3\\
3 & 3 & 3 & 3 & 3
\end{array}
\end{array}
\\
% inner array of delta values
\begin{array}{c|cccc}
\Delta&0&1&2&3\\
\hline
0 & 0 & 1 & 2 & 3\\
1 & 1 & 0 & 1 & 2\\
2 & 2 & 1 & 0 & 1\\
3 & 3 & 2 & 1 & 0
\end{array}
\end{array}
$$

矩阵
$$
\begin{matrix}
1 &amp; x &amp; x^2 \\
1 &amp; y &amp; y^2 \\
1 &amp; z &amp; z^2 \\
\end{matrix}
$$

其他
$$\begin{align}
\sqrt{37} & = \sqrt{\frac{73^2-1}{12^2}} \\
 & = \sqrt{\frac{73^2}{12^2}\cdot\frac{73^2-1}{73^2}} \\ 
 & = \sqrt{\frac{73^2}{12^2}}\sqrt{\frac{73^2-1}{73^2}} \\
 & = \frac{73}{12}\sqrt{1 - \frac{1}{73^2}} \\ 
 & \approx \frac{73}{12}\left(1 - \frac{1}{2\cdot73^2}\right)
\end{align}$$

$$
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
e^{i\frac{\pi}2} \quad e^{\frac{i\pi}2}& e^{i\pi/2} \\
\int_{-\frac\pi2}^\frac\pi2 \sin x\,dx & \int_{-\pi/2}^{\pi/2}\sin x\,dx \\
\end{array}
$$

$$
\begin{array}{cc}
\mathrm{Bad} & \mathrm{Better} \\
\hline \\
\int\int_S f(x)\,dy\,dx & \iint_S f(x)\,dy\,dx \\
\int\int\int_V f(x)\,dz\,dy\,dx & \iiint_V f(x)\,dz\,dy\,dx
\end{array}
$$

$$
x = a_0 + \cfrac{1^2}{a_1
          + \cfrac{2^2}{a_2
          + \cfrac{3^2}{a_3 + \cfrac{4^4}{a_4 + \cdots}}}} \tag{\cfrac}
$$
$$
x = a_0 + \frac{1^2}{a_1
          + \frac{2^2}{a_2
          + \frac{3^2}{a_3 + \frac{4^4}{a_4 + \cdots}}}} \tag{\frac}
$$

$$
\left\{ 
\begin{array}{c}
a_1x+b_1y+c_1z=d_1 \\ 
a_2x+b_2y+c_2z=d_2 \\ 
a_3x+b_3y+c_3z=d_3
\end{array}
\right. 
$$

$$
\begin{array}{|rc|}
\hline
\verb+\color{black}{text}+ & \color{black}{text} \\
\verb+\color{gray}{text}+ & \color{gray}{text} \\
\verb+\color{silver}{text}+ & \color{silver}{text} \\
\verb+\color{white}{text}+ & \color{white}{text} \\
\hline
\verb+\color{maroon}{text}+ & \color{maroon}{text} \\
\verb+\color{red}{text}+ & \color{red}{text} \\
\verb+\color{yellow}{text}+ & \color{yellow}{text} \\
\verb+\color{lime}{text}+ & \color{lime}{text} \\
\verb+\color{olive}{text}+ & \color{olive}{text} \\
\verb+\color{green}{text}+ & \color{green}{text} \\
\verb+\color{teal}{text}+ & \color{teal}{text} \\
\verb+\color{aqua}{text}+ & \color{aqua}{text} \\
\verb+\color{blue}{text}+ & \color{blue}{text} \\
\verb+\color{navy}{text}+ & \color{navy}{text} \\
\verb+\color{purple}{text}+ & \color{purple}{text} \\ 
\verb+\color{fuchsia}{text}+ & \color{magenta}{text} \\
\hline
\end{array}
$$