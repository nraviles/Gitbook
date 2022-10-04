# Stochastic Processes

Welp, we've gotten to the more interesting part, Stochastic processes! 

Theres way way way too much to cover in a brief conversation, and any "understanding" that you could come to from it would probably just be BS-ing yourself. I'm probably just an idiot but having taken like 4 PhD level courses dedicated to it and read and worked on the topic quite a bit on my own, I'm still mostly just floundering around.

As such I'll do my best, but please cut me a break here or there and know that questions are sometimes better answered through hardwork than wisecrack analogies.

A stochastic process, usually denoted $$X(t, \omega)$$

$$
X: \mathbb{R}_+ \times \Omega \rightarrow \mathbb{R}
$$

is a random function in two arguments, one the event $$\omega$$ and the other $$t \in \mathbb{R}_{+}$$ the positve real numbers which we can best think of as time. 

$$X(\cdot, t)$$ as a random variable must of course be measurable accross all time points. If we consider $$X(\cdot, \omega)$$ this is exactly a random path!  

And as one usually thinks, what one usually draws, it must be the weird squiggly lines of say a brownian motion, the staircase of jumps of a point process, or whatever else.

For time $$t$$, $$X_t ( \omega)$$ being a random variable must therefore at each time has a probability $$P_t$$ associated to it! So the next natural question is regarding the dynamics of each, how does $$X_s$$ compare to $$X_t$$ for different times, and in the same way how does $$P_s$$ compare to $$P_t$$.




