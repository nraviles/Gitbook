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

A special case of a markov process is a stationary Markov process where where if $$t - s = h$$ we have that

$$
P(X_t | X_s) = P(X_h | X_0)
$$

for all 
