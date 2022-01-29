---
layout: post
title: "A Small Note on The 'Density Matrix'"
math: true
---
---
The whole game of Quantum Mechanics is about finding out the probability! On the other hand, Statistical Mechanics may be put on the equal foot, although the context is a littile different. But, both the cases, deal with probabilistic approach(Atleast to the Born Oppenheimer interpretation). Whenever these two high-achiever intertwine, something beautiful happen. We get all sort of useful results as the by product. And an interesting quantity appear, known as 'Density Matrix'. Perhaps it is possible to study Quantum mechanical systems statistically without introducing *Density Matrix*, nevertheless, it simplifies many thing and it is rich in concept.

Suppose, one starts heating up a silver foil. The electrons coming out of the foil, can only have two spin states either spin up or down. In the electron beam, coming out of the foil, the spin orientation of an arbitrary choice of an \\(e^-\\) is completely random, therefore known as *random state*. Now, say, we introduce an instrument to polarize the \\(60\%\\) of the electron to be in spin up state along z-axis and \\(40\%\\) in spin down state. This kind of system is said to be in *mix state*. We could have polarized all the electrons in either direction, say in up state, then it would be known as *pure state*. One more interesting thing is, dimensionality of the system need not to be same as of the ket space, neither they need to be orthogonal. For example, we may polarize \\(30\%\\) of electron in positive x direction, \\(45\%\\) in negative y direction and the rest \\(25\%\\) in positive z direction.

It's clear from the above example, here we're dealing with two different type of probability. One is intrinsically quantum mechanical, another we may say *Classical Probability*. 

Suppose, we want to measure ensemble average of some observable \\(A\\) then it is fruitful to introduce a quantity,

\\([A] = \sum_{i} w_i \langle \alpha^{(i)}\|A\| \alpha^{(i)} \rangle \\) 

with a obvious constrained on classical probability \\( \sum_{i} w_i = 1 \\)

$$ \implies \sum_{i} \sum_{a'} w_i | \langle a' | \alpha^{(i)} \rangle |^2 a' $$ 

where, \\(\|a' \rangle\\) is an eigenket of \\(A\\).

In a more general context,

$$\begin{eqnarray}
[A] &=& \sum_{i} w_i \sum_{b'} \sum_{b^"} \langle \alpha^{(i)} | b' \rangle \langle b'|A | b^" \rangle \langle b^"| \alpha^{(i)} \rangle \\
&=& \sum_{b'} \sum_{b^"} \left( \sum_{i} w_i \langle b^" | \alpha^{(i)} \rangle \langle \alpha^{(i)} | b' \rangle \right) \langle b'|A | b^" \rangle
\end{eqnarray}$$

From the completeness property, it is clear, \\(b'\\) and \\(b^"\\) are the dimensionality of ket space whereas \\(i\\) depends on how the ensemble is prepared. In the above equation, it is seen that the properties of ensemble doesn't explicitly depends on the particular observable. This lead us to define density operator
\\[\rho \equiv \sum_{i} w_i |\alpha^{(i)} \rangle \langle \alpha^{(i)}|\\] and the elements of the density matrix are \\[\langle b^"|\rho|b'\rangle = \sum_{i} w_i \langle b^" | \alpha^{(i)} \rangle \langle \alpha^{(i)} | b' \rangle\\]

The density operator contains all the information about the ensemble. A great simplification can be done, 

$$\begin{eqnarray} 
[A] &=& \sum_{b'} \sum_{b^"} \langle b^"|\rho|b'\rangle \langle b'|A | b^" \rangle \\
&=& \sum_{b^"} \langle b^"|\rho A | b^" \rangle \\
&=& tr(\rho A) \\
\end{eqnarray}$$

For the illustration let us take our old example
>  we may polarize \\(30\%\\) of electron in positive x direction, \\(45\%\\) in negative y direction and the rest \\(25\%\\) in positive z direction.

__Solution :__

\\[ w(S_x;+)=3/10, \quad w(S_y;-)=9/20, \quad w(S_z;+)=1/4\\]
$$\begin{eqnarray}
\rho &=& \frac{3}{10}|S_x;+ \rangle \langle S_x;+ | + \frac{9}{20}|S_y;- \rangle \langle S_y;- | + \frac{1}{4}|S_z;+ \rangle \langle S_z;+ | \\
&=& \frac{3}{10} \frac{1}{\sqrt{2}}(|+\rangle + |- \rangle) \frac{1}{\sqrt{2}}(\langle + | + \langle - |) + \frac{9}{20} \frac{1}{\sqrt{2}}(|+\rangle -i |- \rangle) \frac{1}{\sqrt{2}}(\langle + | + i\langle - |) + \frac{1}{4} | + \rangle \langle + | \\
&=&
\begin{pmatrix}
3/20 & 3/20 \\
3/20 & 3/20 \\
\end{pmatrix} +
\begin{pmatrix}
9/40 & 9i/40 \\
-9i/40 & 9/40 \\
\end{pmatrix} +
\begin{pmatrix}
1/4 & 0 \\
0 & 0 \\
\end{pmatrix} \\
&=& 
\begin{pmatrix}
5/8 & 3/20+9i/40 \\
3/20-9i/40 & -3/40 \\
\end{pmatrix} 
\end{eqnarray}$$

Therefore,
$$\begin{eqnarray}
\rho S_x &=&
\begin{pmatrix}
5/8 & 3/20+9i/40 \\
3/20-9i/40 & -3/40 \\
\end{pmatrix} 
\frac{\hbar}{2}
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix} 
&=&
\begin{pmatrix}
3/20+9i/40 & 5/8 \\
-3/40 & 3/20-9i/40 \\
\end{pmatrix} 
\end{eqnarray}$$

\\[\implies [S_x] = tr(\rho S_x) = \frac{3 \hbar}{20} \\]

__Ref:__ *Moden Quantum Mechanics(2nd Edition) - Sakurai*
