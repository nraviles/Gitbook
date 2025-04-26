# Probability Primer: 10/08/22, 3PM CST

This discussion with hopefully be tolerable for those without an extensive math background.

A probability is simply a measure (some number of "ruler lengths") associated with an outcome or event $$A$$ . The value itself mathematically does not have any physical meaning. This can be a problem philosphically but operationally you really shouldn't give a damn.

Equivalently we can think of a probability value itself as a "weight" or "mass" $$w(A)$$ , like a physical body where you assign some "heft" associated with the body-parts. If a body can be seperated to arbitrary precision or say even as small as a point $$x$$ in $$A$$ , we would like to say somethling like there is a weight $$dw(x)$$ such that

$$
w(A) = \sum_{x \text{ in } A} dw(x)
$$

The usual person would do this via a density, an amount of mass in a given space, and then just scale by the amount of space occupied to get the weight, something like:

$$
dw(x) = f(x) \times dx
$$

where we can think of $$d(\cdot)$$ as really just saying "measure a tiny bit".

In the simplest case if we were to ask for the total mass of an entire body, call it $$\Omega = \bigcup_i A_i$$, which is the union of all its disjoint parts (arm, leg, torso, etcetera make the body), $$\{A_i\}_i$$, we would require that the mass of the whole be the sum of the masses of it's parts

$$
w(\Omega) = \sum_i w(A_i)
$$

and in the case where we had the density

$$
\sum_i w(A_i) = \sum_i \int_{x \in A_i} dw(x) = \sum_i \int_{x \in A_i} f(x) dx
$$

Alright, well whats the deal? Masses shmasses, we want probabilities! Well probabilities are just relative weights "the chance of landing on heads versus tails is 1/2" is the same as saying "heads weighs the same as tails, and the weight of the coin is 1 arbitrary unit", i.e. we just require that $$w(\Omega) = 1$$, or in the case that it isn't you just rescale like

$$
w(A) \mapsto \frac{w(A)}{w(\Omega)} = P(A)
$$

Then $$P(\Omega) = 1$$ and $$0 \leq P(A) \leq 1$$ by definition.

This transfers nicely to betting whereby we generally think in terms of odds of complementary outcomes, something like $$P:Q$$ associate with event $$A_P$$ and $$A_Q$$ thus by the weighted "chance" you give to the outcome, formally

$$
P:Q = w(A_P):w(A_Q) \mapsto \frac{w(A_P)}{w(A_P) + w(A_Q)} = P(A_P)
$$

I'm not gonna get into the frequentist versus bayesian crap of interpreting ALL probabilities this way or not, a probability is whatever the fuck works and does so rigorously (either keeps you from dying, or makes sense with the world at the best it is known to operate).

So at the end of the day a probability is just a measure with some nice properties, for those who care about the math (again the math has nothing to do with real life, so happens mimic some of it - by definition) a probability is defined to have the three following items:

$$
P(A) \geq 0 \quad \text{for all A in} \ \Omega
$$

$$
P(\Omega) = 1
$$

$$
P(\bigcup_i A_i) = \sum_i P(A_i) \quad \text{for disjoint events}
$$

Literally it's just the "thing" that does what you want and expect a "probability" to do.
