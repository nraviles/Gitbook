# Properties of Probability

Probabilities can be discrete (evaluated on a countable set of points), each with individual probability values per point, they can be continuous (evaulated only on intervals) or mixes of the two.

In the continuous case when intervals can be chopped up into smaller and smaller parts of smaller and smaller physical lengths we can ask for a density at a point $$x$$ in the following sense

$$
\lim_{\epsilon \rightarrow 0} \frac{P[x-\epsilon/2, x + \epsilon/2]}{\epsilon} \doteq p(x)
$$

where we call $$p(x)$$ the density which can be interpreted in units of probability mass per infintesimal space. When such a function exists we can define probabilities as the accumulation of mass as before and have

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

This equates to making a "correspondence", not to label "heads" or "tails" which are complimentary events (only one happens) but to say "heads is now the value 1, and tails is now 0" and now only measure in number of heads by the sum of 1's (counting them).

If I flip 10 times, and observe 3 heads the number of tails is obvious and is just 10 - 3 = 7.

So what does this mean for us? It means that to make sense numerically of the "value" in probability of thing we are often required to make correspondences between abstract concepts like "my wife if committing adultery with my neighbors" and numbers

A simple way to do this at first is something called an "indicator function" (it indicates things). 

Let $B$ be some circumstance and $A$ be the situation of adultery with all the neighbors, then we define

$$
\begin{align}
  1_{A} (B) &= 1 \quad \text{if B includes the circumstance of n-many adultery, and } \\
  1_{A} (B) &= 1 \quad \text{if B does not includes the circumstance of n-many adultery}
\end{align}
$$

There are certain events that are not "measurable", like if I give you the number 2, theres no way you can parse the probability of such an event because it doesn't mean anything to you in how you've defined your system of probabilities (the outcome of our indicator is 1 or 0, nothing more). 

More specifically what I am asking is, "is there an inverse?", can I go from the number you gave me, to an event, and then assign a probability to it?

Define $$X(\omega) = 1_{A}(\omega)$$ where $$\omega$$ is just some event, we call $$X(\omega)$$ a random variable when $$X^{-1}(x)$$ corresponds to some event with explicit probability; x is just the value "realized" by X which is a real number.

In math-y terms, for any subset (union of intervals you can think) of possible values $$C$$ of the real numbers $$\mathbb{R}$$, if $$\Omega$$ is the set of all events then $$X$$ is a random variable if and only if 

$$
X^{-1}(C) \in \Omega
$$

if you're interested in the specifics and foundations here, look up "measureable functions" an we might talk down the road about it. For now its not important but the synopsis is that if we can only give probabilities to well defined events, and when we attempt to associate numbers to those events we better be able to assign them probabilities.

If $$A \in \Omega$$ then $$P(A)$$ is well defined, if we want the probability that $$X \in C$$ (say X is in the interval (0,2)) the above relation is

$$
P(\{X \in C\}) = P(\{\omega : \omega \in X^{-1}(C)\}) \doteq P(X^{-1}(C))
$$

where $$P(X^{-1}(C))$$ needs to be a probability for all C. The point here is the a random variable $$X$$ is just a measurable function (one you can assign probabilities to)

