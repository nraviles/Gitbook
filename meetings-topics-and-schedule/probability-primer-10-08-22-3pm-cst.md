# Probability Primer: 10/08/22, 3PM CST

This discussion with hopefully be tolerable for those without an extensive math background.

A probability is simply an assignment or measure associated with an outcome or event $$A$$ . The value itself mathematically does not have any physical meaning. This can be a problem philosphically but operationally you really shouldn't give a damn.

The value itself can be thought of as a "weight" or "mass" $$w(A)$$ , like a physical body where you assign some "heft" to certain body-parts. If a body can be seperated to arbitrary precision, in that it can be assigned arbitary small enough parts, say a point $$x$$ in $$A$$ , a weight $$dw(x)$$ such that

$$
w(A) = \sum_{x \text{ in } A} dw(x)
$$

The usual human thing to do here would be to thing of a density, an amount of mass in a given space, and them scale by the amount of space occupied, something like:

$$
dw(x) = f(x) \times dx
$$

where the $$d(\cdot)$$ is really just saying "measure the size!"

In the simplest case if we were to ask for the total mass of an entire body $\Omega$ which is the union of all its disjoint parts (arm, leg, torso, etcetera), $$\{A_i\}_i$$ mathematically denoted $$\Omega = \bigcup_i A_i$$ we would require that 

$$
w(\Omega) = \sum_i w(A_i)
$$

and in the case of the density

$$
\sum_i w(A_i) = \sum_i \int_{x \in A_i} dw(x)  = \sum_i \int_{x \in A_i} f(x) dx
$$

Alright, well whats the deal? Masses shmasses, we want probabilities! Well probabilities are just relative weights "the chance of landing on heads versus tails is 1/2" is the same as saying "heads weighs the same as tails, and the weight of the coin is 1 arbitrary unit", i.e. take you mass

$$
w(A) \mapsto \frac{w(A)}{w(\Omega)} = P(A)
$$

This transfers nicely to betting whereby we generally thing in odds of disjoint outcomes $P:Q$ which add to $P+Q$ of course, thus by the weighted "chance you give to outcome associated with P $A_P$ is 

$$
P:Q = w(A_P):w(A_Q) \mapsto \frac{w(A_P)}{w(A_P) + w(A_Q)} = P(A_P)
$$

I'm not gonna get into the frequentist versus bayesian bullshit, a probability is whatever the fuck works and does so rigorously (either keeps you from dying, or makes sense with the world as it actually is).

