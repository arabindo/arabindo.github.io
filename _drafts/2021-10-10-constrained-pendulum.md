---
layout: post
title: "Dynamical Equations of a Pendulum Constrained to Move on a Parabola"
math: true
---
---
The problem of interest is from *Classical Mechanics* by *Goldstein, Herbert & Poole, Charles & Safko, John. (3rd Ed)* : "The point of suspension of a simple pendulum of length l and the mass m is constrained to move on a parabola \\( z=ax^2 \\) in the verticle plane. Derive the Hamiltonian governing the motion of pendulum and its point of suspension. Obtain the Hamilton's equation of motion."

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ryhVL7ucbj4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Here the generalised coordinates are \\(x\\) and \\(\theta\\). The equation of the parabola is \\(z=ax^2\\). We have denoted the coordinate of the mass as \\((x_m ,z_m)\\) while the coordinate of the point of suspension is \\((x,z)\\). The angle between vertical axis and pendulum is denoted by \\(\theta\\).

![constrained pendulum](/assets/images/#)

From the above diagram it is clear that \\((x_m,z_m) \equiv (x+l\sin\theta, z-l\cos\theta)\\).

The potential energy term is \\[V(z,\theta)=mg(z-l\cos\theta) \tag{1} \\]

The Kinetic energy term is :

$$\begin{eqnarray}
T &=& \frac{1}{2}m\left( \dot{x_m}^2 + \dot{z_m}^2 \right) \\ 
\implies &=& \frac{1}{2}m\left( \dot{x}^2 + l^2\dot{\theta}^2\cos^2\theta+2l\dot{x}\dot{\theta}\cos\theta + \dot{z}^2 + l^2\dot{\theta}^2\sin^2\theta+2l\dot{z}\dot{\theta}\sin\theta \right) \\
\end{eqnarray}$$

Using \\(z=ax^2 \implies \dot{z} = 2ax\dot{x} \\) and on grouping terms we have,

\\[ T = \frac{1}{2}m\left( 1+4a^2x^2\right)\dot{x}^2 + \frac{1}{2}ml^2\dot{\theta}^2 + ml\dot{x}\dot{\theta}(\cos\theta + 2ax\sin\theta ) \tag{2} \\]

Therefore the Lagrangian of the system is given by,

\\[ L = \frac{1}{2}m\left( ( 1+4a^2x^2)\dot{x}^2 + l^2\dot{\theta}^2 + 2l\dot{x}\dot{\theta}(\cos\theta + 2ax\sin\theta ) \right) - mg(ax^2-l\cos\theta) \tag{3} \label{3} \\]

Before we start working on Hamiltonian Dynamics, I would like to find Equations of Motion(EOM) from eqn \\( \ref{3} \\), since I used them to animate the system. You may checkout that details [here](https://arabindo.github.io/animation/eom.html){:target="_blank"}. It was also possible to do with Hamilton's equation but the expressions were too long and complex, so I decided to avoid.

The equations of motion are:

For x coordinate: 
\\[\frac{d}{dt}\left(\frac{\partial L}{\partial\dot{x}}\right) - \frac{\partial L}{\partial x} = 0 \\]

\\[\ddot{x} (1+4a^2 x^2) + 4a\dot{x}^2x+l\ddot{\theta}(\cos\theta + 2ax\sin\theta)+l\dot{\theta}^2(-\sin\theta + 2ax\cos\theta) + 2agx = 0 \tag{4} \label{4} \\]

For \\(\theta\\) coordinate: 
\\[\frac{d}{dt}\left(\frac{\partial L}{\partial\dot{\theta}}\right) - \frac{\partial L}{\partial \theta} = 0 \\]


\\[l^2\ddot{\theta} + l\ddot{x}(\cos\theta + 2ax\sin\theta) + 2al\dot{x}^2 \sin\theta + mgl\sin\theta = 0 \tag{5} \label{5} \\]

For the numerical solution, we need to convert the equation \\( \ref{4} \& \ref{5} \\) into two first order equation as follows,

\\[\dot{x} = X \tag{a} \\]

\\[\dot{\theta} = \Theta \tag{b} \\]

\\[\dot{X}(1+4a^2 x^2) + 4aX^2x + l\dot{\Theta}(\cos\theta + 2ax\sin\theta) + l\Theta^2(-\sin \theta + 2ax\cos\theta) + 2gax = 0 \tag{c0} \label{c0} \\]

\\[\dot{\Theta} = -\left(\dot{X}(\cos\theta + 2ax\sin\theta) + 2aX^2\sin\theta+g\sin\theta \right) \tag{d} \label{d} \\]

Substituting \\( \ref{d} \\) in the 3rd term of equation \\( \ref{c0} \\) and grouping with first term we obtain,

\\[\dot{X}[(1+4a^2 x^2) - \cancel{l^2}(\cos\theta + 2ax\sin\theta)^2 / \cancel{l^2}] - \cancel{l}(\cos\theta + 2ax\sin\theta)(2a\cancel{l}X^2 + g\cancel{l})\frac{\sin\theta}{\cancel{l^2}}\\]

Thus we have,

\\[\dot{X} = \frac{\sin\theta(\cos\theta + 2ax\sin\theta)(4aX^2 + g) - 4aX^2x - l\Theta^2(-\sin \theta + 2ax\cos\theta) - 2gax}{(1+4a^2 x^2) - \left(\cos \theta + 2ax\sin\theta\right)^2 } \tag{c} \\]

### Hamiltonian Dynamics:

The Lagrangian (Equation \\( \ref{3} \\)) is in the form \\(L_2 + L_0\\), i.e., quadratic in generalised velocities. Thus we may write the correspoinding matrix:

$$\begin{eqnarray}
\tau &=& m
\begin{pmatrix}
1+4a^2 x^2 & l(\cos\theta + 2ax\sin\theta) \\
l(\cos\theta + 2ax\sin\theta) & l^2 \\
\end{pmatrix}
\\
\implies Adj\quad\tau &=& m
\begin{pmatrix}
l^2 & -l(\cos\theta + 2ax\sin\theta) \\
-l(\cos\theta + 2ax\sin\theta) & 1+4a^2 x^2 \\
\end{pmatrix}
\\
|\tau| &=& m^2 l^2 [1+4a^2 x^2 - (\cos\theta + 2ax\sin\theta)^2] = m^2 s\quad(say)
\end{eqnarray}$$

We can further simplify \\(s\\),

$$\begin{eqnarray}
s &=& l^2[1+4a^2 x^2-\cos^2\theta-4a^2x^2\sin^2\theta-4ax\sin\theta\cos\theta] \\
&=& l^2[ 1-\cos^2\theta + 4a^2x^2(1-\sin^2\theta)-4ax\sin\theta\cos\theta] \\
s &=& l^2(\sin\theta - 2ax\cos\theta)^2 \tag{6} \\
\end{eqnarray}$$

Therefore, 

$$\begin{eqnarray}
\tau^{-1} &=& \frac{Adj \quad \tau }{|\tau|} \\
&=& \frac{1}{ms}
\begin{pmatrix}
l^2 & -l(\cos\theta + 2ax\sin\theta) \\
-l(\cos\theta + 2ax\sin\theta) & 1+4a^2 x^2 \\
\end{pmatrix}
\tag{7}
\end{eqnarray}$$

The Hamiltonian is given by,

$$\begin{eqnarray}
H &=& \frac{1}{2}p^T \tau^{-1} p - L_0 \\
&=& \frac{1}{2ms}
\begin{pmatrix}p_x & p_\theta \end{pmatrix}
\begin{pmatrix}
l^2 & -l(\cos\theta + 2ax\sin\theta) \\
-l(\cos\theta + 2ax\sin\theta) & 1+4a^2 x^2 \\
\end{pmatrix}
\begin{pmatrix} p_x \\ p_\theta \end{pmatrix} + mg(ax^2-l\cos\theta)\\
\implies H &=& \frac{1}{2ms}[{p_x}^2 l^2 -2l(\cos\theta + 2ax\sin\theta){p_x}{p_\theta} + (1+4a^2 x^2){p_\theta}^2] + mg(ax^2-l\cos\theta) \tag{8}
\end{eqnarray}$$

To obtain EOMs, let us calculate two quantity first,

$$\begin{eqnarray} 
\frac{\partial}{\partial x}\left( \frac{1}{s} \right) &=& -s^{-2}2l^2(\sin\theta - 2ax\cos\theta)(-2a\cos\theta)\\
\implies \frac{\partial}{\partial x}\left( \frac{1}{s} \right) &=& 4la\cos\theta\sqrt{s}/s^2\\
\implies \frac{\partial}{\partial x}\left( \frac{1}{s} \right) &=& \frac{4la\cos\theta}{\sigma^3} \tag{9}\\
where, \quad \sigma = l(\sin\theta - 2ax\cos\theta)=\sqrt{s} \tag{10}\\
and,\\
\frac{\partial}{\partial \theta} \left( \frac{1}{s} \right) &=& -s^{-2}2l^2(\sin\theta - 2ax\cos\theta)(\cos\theta + 2ax\sin\theta) \\
\implies \frac{\partial}{\partial \theta} \left( \frac{1}{s} \right) &=& \frac{-2l(\cos\theta + 2ax\sin\theta)}{\sigma^3} \tag{11} \\
\end{eqnarray}$$

\\(\Lambda = {p_x}^2 l^2 -2l(\cos\theta + 2ax\sin\theta){p_x}{p_\theta} + (1+4a^2 x^2){p_\theta}^2\\)
