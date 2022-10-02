# Probability Primer: 10/08/22, 3PM CST

This discussion with hopefully be tolerable for those without an extensive math background.

A probability is simply an assignment or measure associated with an outcome or event $A$. The value itself mathematically does not have any physical meaning. This can be a problem philosphically but operationally you really shouldn't give a damn.

The value itself can be though of as a "weight" or "mass" $w(A)$ , like a physical body where you assign some "heft" to certain body-parts. If a body can be seperated to arbitrary precision, in that it can be assigned arbitary small enough parts, say a point $x$ in $A$ , a weight $dw(x)$ such that

$$w(A) = \sum_{x \text{ in } A} dw(x)$$

The usual human thing to do here would be to thing of a density, an amount of mass in a given space, and them scale by the amount of space occupied, something like:

$$dw(x) = f(x) \times dx$$

where the $d(\cdot)$ is really just saying "measure the size!"

In the simplest case if we were to ask for the total mass of an entire body $\Omega$ which is the union of all its disjoint parts (arm, leg, torso, etcetera), $\set{ A_i }_i$ mathematically denoted $\Omega = \bigcup_i A_i$ we would require that 

$$w(\Omega) = \sum_i w(A_i)$$

and in the case of the density

$$w(\Omega) = \sum_i \int_{x \in A_i} dm(x)  = \sum_i \int_{x \in A_i} f(x) dx$$

$$
\begin{align}
  F(x) &= x^2 \\
  G(x) &= k^3 \\
  \sum_{i=0}^n i^2 &= \frac{(n^2+n)(2n+1)}{6}
\end{align}
$$

