# Stochastic Processes

Welp, we've gotten to the more interesting part, Stochastic processes! 

Theres way way way too much to cover in a brief conversation, and any "understanding" that you could come to from it would probably just be BS-ing yourself. I'm probably just an idiot but having taken like 4 PhD level courses dedicated to it and read and worked on the topic quite a bit on my own, I'm still mostly just floundering around.

As such I'll do my best, but please cut me a break here or there and know that questions are sometimes better answered through hardwork than wisecrack analogies.

A stochastic process, usually denoted $$X(t, \omega)$$

$$
X: \mathbb{R}_+ \times \Omega \rightarrow \mathbb{R}
$$

is a random function in two arguments, one the event $$\omega$$ and the other $$t \in \mathbb{R}_{+}$$ the positve real numbers which we can best think of as time. 

$$X(\cdot, t)$$ as a random variable must of course be measurable accross all time points. 

What does this mean? Well at each time $$t$$, $$X_t ( \omega)$$ is a random variable as we've previously discussed and therefore at each time has a probability $$P_t$$ associated to it. 

If we consider $$X(\cdot, \omega)$$ this is exactly a random path! 

This is what one usually draws, the weird squiggly lines of a brownian motion, or the jumps of a point process
