# Properties of Probability

Probabilities can be discrete (evaluated on a countable set of points), each with individual probability values per point, they can be continuous (evaulated only on intervals) or mixes of the two.

In the continuous case when intervals can be chopped up into smaller and smaller parts of smaller and smaller physical lengths we can ask for a density at a point $x$ in the following sense

$$
\lim_{\epsilon \rightarrow 0} \frac{P[x-\epsilon/2, x + \epsilon/2]}{\epsilon} \doteq p(x)
$$

where we call $p(x)$ the density which can be interpreted in units of probability mass per infintesimal space. When such a function exists we can define probabilities as the accumulation of mass as before and have

$$
P[a,b] = \int_{x \in [a,b]} p(x) dx
$$

and have the special function called the distribution funtion of our probability

$$
F(b) = \int_{x \in [-\infty,b]} p(x) dx = \int_{-\infty}^{b} p(x) dx
$$

## Random Variables
