# Martingales and Markov Processes

At the title suggests we will be discussing to classes of objects which form much of the theory of stochastic processes. They are both very special and useful but often things can go awry due to misunderstanding and laziness.

I will mostly just define them here, and during the discussion do my best to make some simple examples.

Most people are familiar with Markov processes, but fewer with Martingales.

A Markov process is a random process $$X_t$$ such that conditional probabilties work in the following way

$$
P(X_t | \mathcal{F}_s) = P(X_t | X_s)
$$

Remember $$\mathcal{F}_s$$ is the entire past of the stochastic process $$X_t$$ up to time $$s$$, so if we considered the discrete set of times and the entire sequence

$$ 
X_0, X_1, ... , X_s, X_{s+1}, ... X_n
$$

Then the information of all of them up to time $$s$$ is

$$
\sigma(X_0, X_1, ... , X_s) = \mathcal{F}_s
$$

So rewriting this we would have

$$
P(X_t | \mathcal{F}_s) = P(X_t | X_0, X_1, ... , X_s) = P(X_t | X_s)
$$

So the distribution of the future $$X_t$$ is independent of the past given the present. 

Physicists really appreciate these processes as it is exactly how we think of the world in that only the current state of the system informs future states given some equilibrium conditions.

As the probability is just as special case of an expectation, you can also rephrase the above more generally (as it it usually done) as

$$
\mathbb{E}(X_t | \mathcal{F}_s) = \mathbb{E}(X_t | X_s)
$$


This naturally pops up when we consider a process than can be decomposed into independent increments (pairwise independence between $$X_i$$ and $$X_j$$ for any $$i,j$$)

$$
S_n = X_0 + X_1 + ... + X_n
$$

or rather recursively definng $$S_0 = X_0$$ and

$$
S_{n+1} = S_n + X_{n+1}
$$

then given $$S_n$$ the only thing left to determine $$S_{n+1}$$ is that extra "increment" $$X_{n+1}$$

We can generalize to arbitrary $$k$$ as

$$
S_n = S_k + (S_n - S_k) \doteq S_k + \Delta_{n-k} S_k
$$

where $$\Delta_{n-k} S_k$$ is the "forward difference" or increment by $$n-k$$ units of time. Probabilistically we can say

$$
\begin{align}
  P(S_{n} = s_n | \mathcal{F}_k) &= P(S_{n} = s_n | S_k = s_k) \\
  &= P(s_{k} + \Delta_{n-k} S_k = s_n | S_k = s_k) \\
  &= P(\Delta_{n-k} S_k = s_n - s_{k} | S_k = s_k) \\
  &= P_k (\Delta_{n-k} S_k = s_n - s_{k}) \\
  &= P_k (\Delta_{n-k} S_k = s')
\end{align}
$$

where in the above we have abridged the notation to say that it may depend on k as $$\Delta_{n-k} S_k$$ may not have the same distribution for some other $$k'$$, $$\Delta_{n-k'} S_{k'}$$ and leave the $$S_k$$ capitalized to denote that it is in fact a random variable. 

When the distribution is the same as long as the time increment is the same for any $$t,s$$ if $$t - s = h$$ we have that

$$
\begin{align}
  P(X_t = x_t | X_s = x_s) &= P(X_h = x_h | X_0 = x_0) \\
  P_s (\Delta_{h}X_s = x') &= P_0 (\Delta_{h}X_0 = x') \\
\end{align}
$$

we would say that are process is Markov with Stationary (same distribution) Independent increments or rather that they are "independent and identically distributed" (iid).
