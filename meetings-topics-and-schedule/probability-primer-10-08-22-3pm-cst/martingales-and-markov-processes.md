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
