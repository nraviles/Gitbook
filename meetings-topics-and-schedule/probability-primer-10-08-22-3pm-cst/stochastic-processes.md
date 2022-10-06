# Stochastic Processes

Welp, we've gotten to the more interesting part, Stochastic processes!

Theres way way way too much to cover in a brief conversation, and any "understanding" that you could come to from it would probably just be BS-ing yourself. I'm probably just an idiot but having taken graduate level courses and dedicated effort on my own, I'm still mostly just confused and floundering around.

As such I'll do my best, but please cut me a break here or there and know that questions are sometimes better answered through hardwork than wisecrack analogies.

A stochastic process, usually denoted $$X(t, \omega)$$

$$
X: \mathbb{R}_+ \times \Omega \rightarrow \mathbb{R}
$$

is a random function in two arguments, one the event $$\omega$$ and the other $$t \in \mathbb{R}_{+}$$ the positve real numbers which we can best think of as time.

$$X(\cdot, t)$$ as a random variable must of course be measurable accross all time points. If we consider $$X(\cdot, \omega)$$ this is exactly a random path!

And as one usually thinks, what one usually draws, it must be the weird squiggly lines of say a brownian motion, the staircase of jumps of a point process, or whatever else.

For time $$t$$, $$X_t ( \omega)$$ being a random variable must therefore at each time has a probability $$P_t$$ associated to it! So the next natural question is regarding the dynamics of each, how does $$X_s$$ compare to $$X_t$$ for different times, and in the same way how does $$P_s$$ compare to $$P_t$$.

But when someone says compare, they need to first "know" something, thus we need to discuss the information of a random variable and how to use what we know mathematically.

## Filtrations

This is gonna get notationally heavy for a second but I'm gonna keep the the math simple.

Easy thing to ask is then why am I even including it? Well its a useful concept and traces philosphically how we think of "knowledge" or more specifically for our purposes how the amount we know changes as time goes on.

Let $$\sigma(Y)$$ be the thing that contains "all the information" about $$Y$$ when we wrote

$$
\mathbb{E}[X|Y]
$$

what we really meant was

$$
\mathbb{E}[X|\sigma(Y)]
$$

it's just mathematical sematics, but it matters.

Let $$s \leq T$$ then what we want to say is that if I have all the information up to time T of $$X_t$$ (all of it's past and present) we should have all the information regarding $$X_s$$ right? It's contained in its past!

We will denote $$\sigma(X_{0\leq s \leq T}) = \mathcal{F}_T$$ then in set notation we should have

$$
\mathcal{F}_s \subset \mathcal{F}_t
$$

We call the set of $$\mathcal{F}_t$$ for $$t \geq 0$$ a filtration when the above is true for any $$s \leq t$$

A brief and final aside here will be something called a stopping time, which is something important for decision making and pops up extensively whether it be in math, or in games and finance.

A stopping time $$\tau$$ is a random variable such that the event

$$
\{ \tau \leq t \} \in \mathcal{F}_t \quad \forall t \geq 0
$$

What does this mean? Well it says that I need to be able to make the decision to stop at time $$t$$ given only information up to time $$t$$ (I can't require future information to make a decision now).

An example of something that is not a stopping time is

$$
\tau = \text{``Time of the first `peak`"}
$$

This is not a stopping time, because I will not know until after any given time that I will need to stop. If you're going to give in, your uncle point shouldn't be called after they've broken your shins.

This is like gambling and saying "I'll stop before I'm close to losing all my money", you often won't know you've lost it all until you do - by the time you feel the need to go to the doctor, you're often as good as dead.

Now that we have these tools under our belt, even if we don't completely understand them, lets slap haphazardly slap together some fun objects.
