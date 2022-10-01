# Probability Primer: 10/08/22, 3PM CST

This discussion with hopefully be tolerable for those without an extensive math background.

A probability is simply an assignment or measure associated with an outcome or event $A$. The value itself mathematically does not have any physical meaning. This can be a problem philosphically but operationally you really shouldn't give a damn.

The value itself can be though of as a "weight" or "mass" $m(A)$, like a physical body where you assign some "heft" to certain body-parts. If a body can be seperated to arbitrary precision, in that it can be assigned arbitary parts of weight given accumulating the "density" $dm(x)$ at for any point $x$.

We will denote the space it occupies as $dx$. Then we have the weight we are interested in is $dm(x) \times dx$, where of course density is of course in units of weight/space.

In the simplest case if we were to ask for the total mass of an entire body $\Omega$ which is the union of all its disjoint parts (arm, leg, torso, etcetera), $\set{ A_i }_i$ which is denoted $\Omega = \bigcup_i A_i$ we would require that 

$$m(\Omega) = \sum_i m(A_i)$$

and in the case of the density

$$m(\Omega) = \sum_i \int_{x \in A_i} dm(x) dx$$

$$
\begin{align}
  F(x) &= x^2 \\
  G(x) &= k^3 \\
  \sum_{i=0}^n i^2 &= \frac{(n^2+n)(2n+1)}{6}
\end{align}
$$

