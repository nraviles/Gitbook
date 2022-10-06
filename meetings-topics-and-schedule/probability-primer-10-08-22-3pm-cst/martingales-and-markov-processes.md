# Martingales and Markov Processes

At the title suggests we will be discussing to classes of objects which form much of the theory of stochastic processes. They are both very special and useful but often things can go awry due to misunderstanding and laziness.

I will mostly just define them here, and during the discussion do my best to make some simple examples.

Most people are familiar with Markov processes, but fewer with Martingales.

## Markov Property

A Markov process is a random process $$X_t$$ such that conditional probabilties work in the following way

$$
P(X_t | \mathcal{F}_s) = P(X_t | X_s)
$$

Remember $$\mathcal{F}_s$$ is the entire past of the stochastic process $$X_t$$ up to time $$s$$, so if we considered the discrete time process and the entire sequence

$$ 
X_0, X_1, ... , X_s, X_{s+1}, ... X_t
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
\mathbb{E}(g(X_t) | \mathcal{F}_s) = \mathbb{E}(g(X_t) | X_s)
$$


This naturally pops up when we consider a process than can be decomposed into independent increments (pairwise independence between $$X_i$$ and $$X_j$$ for any $$i,j$$)

$$
S_n = X_0 + X_1 + ... + X_n
$$

or rather defining it recursively with $$S_0 = X_0$$ and

$$
S_{n+1} = S_n + X_{n+1}
$$

then given $$S_n$$ the only thing left to determine $$S_{n+1}$$ is that extra "increment" $$X_{n+1}$$, so we could say something like

$$
\mathbb{E}[S_{n+1}|\mathcal{F}_n] = \mathbb{E}[S_{n+1}|S_n] = \mathbb{E}[S_{n} + X_{n+1}|S_n] = S_n + \mathbb{E}[X_{n+1}|S_n]
$$

We can generalize to arbitrary $$k$$ as

$$
S_n = S_k + (S_n - S_k) \doteq S_k + \Delta_{n-k} S_k
$$

where $$\Delta_{n-k} S_k$$ is the "forward difference" or increment by $$n-k$$ units of time. Probabilistically we can say

$$
\begin{align*}
  P(S_{n} = s_n | \mathcal{F}_k) &= P(S_{n} = s_n | S_k = s_k) \\
  &= P(s_{k} + \Delta_{n-k} S_k = s_n | S_k = s_k) \\
  &= P(\Delta_{n-k} S_k = s_n - s_{k} | S_k = s_k) \\
  &= P_k (\Delta_{n-k} S_k = s_n - s_{k}) \\
  &= P_k (\Delta_{n-k} S_k = s')
\end{align*}
$$

where in the above we have abridged the notation to say that it may depend on k as $$\Delta_{n-k} S_k$$ may not have the same distribution for some other $$k'$$, $$\Delta_{n-k'} S_{k'}$$ and leave the $$S_k$$ capitalized to denote that it is in fact a random variable. 

When the distribution is the same as long as the time increment is the same, say for any $$t,s$$ if $$t - s = h$$ and we have that

$$
\begin{align*}
  P(X_t = x_t | X_s = x_s) &= P(X_h = x_h | X_0 = x_0) \\
  P_s (\Delta_{h}X_s = x') &= P_0 (\Delta_{h}X_0 = x') \\
\end{align*}
$$

we would say that our process is Markov with Stationary (same distribution) Independent increments or rather that they are "independent and identically distributed" (iid).

This is the case as with a Brownian Motion or Wiener Process, or a homogeneous Poisson process (homogenous here means stationary) if you know what those are.

Lastly we say a process has the Strong Markov property when the Markov Property is true for arbitrary stopping times $$\tau$$ i.e.

$$
P(X_t | \mathcal{F}_{\tau}) = P(X_t | X_{\tau})
$$

which is true for many processess including Brownian Motion and Markov Point processess, but not all.

And fun fact! If as before $$h = t - s$$  

$$
X_t = f(X_s, N_h)
$$

where $$N_t$$ is some random variable or noise term independent of $$X_s$$ then $$X_t$$ is Markov (think for a second on this).

This makes many optimization techniques inherently Markov (stochastic or otherwise; deterministic is a special case of stochastic)

## Martingale Property

Martingales are one of the most useful objects you'll ever come across in probability and stochastic processess, it is also sadly one that almost never pops up in the discussion of statistical phenomena.

A Martingale may sound fancy, and is usually associated with things like finance or gambling where it's in everyones interest to sound more intelligent than they are (I make a note of trying to sound as stupid and hopefully genuine as possible), but now that we've built up some familiarity with defintions its actually quite simple.

A Martingale is a stochastic process such that

$$
\mathbb{E}[|X_t|] < \infty \quad \forall t 
$$

$$
\mathbb{E}[X_t | \mathcal{F}_s] = X_s \quad s \leq t
$$

i.e. our expectation of future time $$t$$ for $$X_t$$ is our present value $$X_s$$ at time $$s$$. 

This expresses some intrinsic dynamic of lacking any forcing/driving motion up or down but rather a kind of wandering.

This does not mean that the distribution is symmetric but rather that the weights balance out in expectation.

A process is a sub-Martingale (b points up) if

$$
\mathbb{E}[X_t | \mathcal{F}_s] \geq X_s \quad s \leq t
$$

and super-Martingale (p points down)

$$
\mathbb{E}[X_t | \mathcal{F}_s] \leq X_s \quad s \leq t
$$

Why the counter-intuitive names? They're related to a kind of math I have little involvement in called harmonic analysis where you can have sub- and super-harmonic functions. Other than that, no clue.

## Stopped martingale

Let $$\tau$$ be a stopping time, define  

$$
\tau \wedge t = \min \{\tau, t \}
$$

i.e. the smaller of the two times.

Then, taking for granted what I tell you now, if $$M_t$$ is a Martingale

$$
M_{\tau \wedge t}
$$

is also a martingale called the "stopped" Martingale. 

It is called this because once $$\tau$$ happens $$M_{\tau}$$ is forever fixed and can be written as 

$$
M_{\tau \wedge t} = M_{\tau} 1_{\tau \leq t} + M_t 1_{\tau > t} = \sum_{i=1}^{t} M_{\tau} 1_{\tau = t} + M_t 1_{\tau > t}
$$

This stopped Martingale is important because it makes calculating things absurdly easy as long as conditions are met for something called the Optional Stopping Theorem. 

As an example calculation, lets just say the "condtions are met" in that we can justify passing the limit through the expectation here, and importantly as well

$$
P(\tau < \infty) = 1
$$

i.e. you always hit $$\tau$$ in a finite amount of time ($$\tau < t$$ happens eventually for large enough $$t$$)

$$
\lim_{t \rightarrow \infty} \mathbb{E}[M_{\tau \wedge t}] = \mathbb{E}[ \lim_{t \rightarrow \infty} M_{\tau \wedge t}] = \mathbb{E}[M_{\tau}]
$$

and let $$\mathbb{E}[M_0] = 0$$, or even more strongly $$M_0 = 0$$

Then we have that as $$M_{\tau \wedge t}$$ is a Martingale

$$
\mathbb{E}[M_{\tau \wedge t}] = \mathbb{E}[M_0] = 0
$$

which implies that

$$
\mathbb{E}[M_{\tau}] = 0
$$

now if we let 

$$
\tau = \inf\{ t : M_t = a, \ M_t = -b\}
$$

and respectively

$$
\tau_a = \inf\{ t : M_t = a\}, \quad \tau_{-b} = \inf\{ t : \ M_t = -b\}
$$

we would have that

$$
\begin{align*}
  0 &= \mathbb{E}[M_\tau] \\
  &= a P(M_\tau = a) - b P (M_\tau = -b) \\
  &= a P(\tau_a < \tau_b) - b P (\tau_b < \tau_a) \\
  &= a P(\tau_a < \tau_b) - b (1 - P(\tau_a < \tau_b))
\end{align*}
$$

which implies that

$$
P(\tau_a < \tau_b) = \frac{b}{a+b}, \quad P(\tau_b < \tau_a) = \frac{a}{a+b}
$$

i.e. the probability that you hit $$a$$ before $$b$$ or $$b$$ before $$a$$ respectively.

The fancy conditions here can be summed up as 

$$
P(\tau < \infty) = 1
$$

plus whatever you need to move the limit inside the expectation (integral).

In our case 

$$
|M_{\tau \wedge t}| \leq |M_{\tau}| = \max\{a,b\} < \infty
$$

which is completely bounded allows the limiting argument, and both the above conditions are satisfied for things like a simple 1 dimensional random walk and a Browninan motion.
