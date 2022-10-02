# Properties of Probability

Probabilities can be discrete (evaluated on a countable set of points), each with individual probability values per point, they can be continuous (evaulated only on intervals) or mixes of the two.

In the continuous case when intervals can be chopped up into smaller and smaller parts of smaller and smaller physical lengths we can ask for a density at a point $$x$$ in the following sense

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

So what does this mean for us? It means that to make sense numerically of the "value" in probability of thing we are often required to make correspondences between abstract concepts like "my wife if committing adultery with my neighbor" and numbers $$\{0,1\}$

A simple way to do this at first is something called an "indicator function" (it indicates things)

$$
\begin{equation}
\mathbb{1}_{\text{Wife is f*$%ing my neighbor}}(A) = 
  \begin{cases}
    1 & \text{Event A includes the event of adultery with my neighbor} \\
    0 & \text{Event A does not includes the event of adultery with my neighbor}
  \end{cases}
\end{equation}
$$
