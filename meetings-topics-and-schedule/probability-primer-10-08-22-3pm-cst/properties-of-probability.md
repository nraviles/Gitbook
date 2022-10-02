# Properties of Probability

Probabilities can be discrete (evaluated on a countable set of points), each with individual probability values per point, they can be continuous (evaulated only on intervals) or mixes of the two.

In the continuous case when intervals can be chopped up into smaller and smaller parts of smaller and smaller physical lengths we can ask for a density at a point $$x$$ in the following sense

$$
\lim_{\epsilon \rightarrow 0} \frac{P[x-\epsilon/2, x + \epsilon/2]}{\epsilon} \doteq p(x)
$$

which can be interpreted in units of probability mass per infintesimal space. When such a function exists we can define probabilities as the accumulation of mass as before and have

$$
P[a,b] = \int_{x \in [a,b]} p(x) dx
$$

and have the special function called the distribution funtion of our probability

$$
F(b) = \int_{x \in [-\infty,b]} p(x) dx = \int_{-\infty}^{b} p(x) dx
$$

Note if we take the density or rather derivative of this function $$F(x)$$

$$
\lim_{\epsilon \rightarrow 0} \frac{F(x+\epsilon/2) - F(x - \epsilon/2)}{\epsilon} = p(x)
$$

which is why you will often see $$f(x)$$ rather than $$p(x)$$


## Random Variables

Now, what actually corresponds to these probabilities? 

Flipping a coin and getting heads or tails is not a number, its some arbitary event, so what does it mean to ask "whats the average number of heads we should expect?", well the natural way to think about it is to count! 

This equates to making a "correspondence", not to label "heads" or "tails" which are complimentary events (only one happens) but to say "heads is now the value 1" and the number of heads is just the sum of 1's (counting them).

So what does this mean for us? It means that to make sense numerically of the "value" in probability of something arbitrary we are often required to make correspondences between abstract concepts like "my wife if committing adultery with my neighbors" and numbers.

A simple way to do this at first is something called an "indicator function" (it indicates things). 

Let $$B$$ be some circumstance and $$A$$ be the situation of adultery with all the neighbors, then we define

$$
\begin{align}
  1_{A} (B) &= 1 \quad \text{if B includes the circumstance of n-many adultery, and } \\
  1_{A} (B) &= 1 \quad \text{if B does not includes the circumstance of n-many adultery}
\end{align}
$$

Not all functions/correspondences work as there are certain events that are not "measurable", we can't assign them a probability.

If you only register 0 or 1, and I give you 2 and ask you how probable that is, it doesn't mean shit.

More specifically what I am asking is, "is there an inverse?", can I go from the number you gave me, to an event, and then assign a probability to it?

If we define the function $$X(\omega) = 1_{A}(\omega)$$ where $$\omega$$ is just some event (we caught the wife in the act), we call $$X(\omega)$$ a random variable when $$X^{-1}(x)$$ corresponds to some event with explicit probability, where x is just the value "realized" by X which is a real number (if all the neighbors were present $$x = 1$$).

In math-y terms, for any subset of possible values for X, $$C$$ of the real numbers $$\mathbb{R}$$, if $$\Omega$$ is the set of all events then we say $$X$$ is a random variable if and only if 

$$
X^{-1}(C) \in \Omega
$$

if you're interested in the specifics and foundations here, look up "measureable functions" and $$\sigma$$-algebra. We might talk about it down the road but its just some extra work for cleanliness. 

For now its not important. The synopsis is that if we can only give probabilities to well defined events, and when we attempt to associate numbers to those events we better be able to assign them probabilities.

If $$A \in \Omega$$ then $$P(A)$$ is well defined by construction, if we want the probability that $$X \in C$$ (say X = 1) the above relation must give us that

$$
P(\{X \in C\}) = P(\{\omega : \omega \in X^{-1}(C)\}) \doteq P(X^{-1}(C))
$$

where $$P(X^{-1}(C))$$ needs to be a probability for all C. 

Again point here is that a random variable $$X$$ is just a measurable function (one you can assign probabilities to) it not anything fancy, in math its just a function we can give a probability value to, no hocus-pocus of whether "chance" exists, or what "uncertainty" is here, its just the thing that works well for what we're trying to do. 

## Expectation

The above is just fancy bullshit that will be used later where instead of being confused by "what's a stochastic process" we can easily just say "its the measurable function evaluate over time.

Now for every random variable X, and probability over events P, we have a probability over the values of X and therefore a distribution function for it $$F(x)$$.

We'd now like to ask, what probability to we expect that our wife is cheating on us? We can use $$1_A(x) \doteq 1_{X^{-1}(x) \in A}$$ to accomadate for the fact that X and A may be in different spaces. With fancy notation let the "expectation" be defined as the first

$$
\mathbb{E}[1_A] = \sum_x 1_A(x) P(X^{-1}(x))
$$

then we have expanding over whether $X^{-1}(x) \in A$ or not that

$$
\sum_x 1_{X^{-1}(x) \in A} P(X^{-1}(x)) = \sum_{X^{-1}(x) \in A} 1 \times P(X^{-1}(x)) + \sum_{X^{-1}(x) \notin A} 0 \times P(X^{-1}(x))
$$

and therefore

$$
\mathbb{E}[1_A] = \sum_{X^{-1}(x) \in A} P(X^{-1}(x)) = P(X^{-1}(X(A)) = P(A)
$$

This can be generalized to arbitrary linear combinations of indicators of disjoint events $$A_i$$

$$
\phi_n = \sum_i^n c_i 1_{A_i}
$$

where we do exactly the same process above and note that we have 

$$
\mathbb{E}[\phi_n] = \mathbb{E}[\sum_i c_i 1_{A_i}] = \sum_i^n c_i \mathbb{E}[1_{A_i}] = \sum_i c_i P(A_i)
$$

and from here to any function say $$g(x)$$ that can be realized as the limit of $$\phi_n$$. For now on, we will ignore the cumbersome $$P(X^{-1}(x))$$ and just assume you know thats what I mean when I write $$P(X = x)$$

If the values of our random variable $$X$$ are discrete, none of the above matters really, we just have that

$$
\mathbb{E}[g] = \sum_x g(x) P(X = x)
$$

but this is a required aside for continuous distributions where it truly does matter that we not evaluate probabilities on points (probability of a point is 0). Instead of a sum here, we can show that under the density assumption

$$
\mathbb{E}[g] = \int_x g(x) dP(x) = \int_x g(x) p(x) dx
$$
