---
layout: post
title:  "R&D Races Without Patents"
date:  2023-3-15
categories: Economics
use_math: true
---

### Intro

Innovation is often studied through R&D race models. In such models, firms incur a cost for the chance to be the first to discover some innovation. Once a firm discovers the innovation, they patent their discovery and receive monopoly profits. Loury introduced the framework in 1979, and it is still being used by economist today [(Loury 1979)](https://academic.oup.com/qje/article-abstract/93/3/395/1890051). For example, Awaya and Krishna recently leveraged the R&D race framework in order to understand how differences in information quality may effect firm profits in a duopoly R&D race [(Awaya *et al.* 2021)](https://www.journals.uchicago.edu/doi/abs/10.1086/711953).  

The core assumption of these models is that firms face a constant rate $$\lambda$$ that they will discover an innovation once they enter the race. In some specifications, this $$\lambda$$ is endogenous; in others, it's taken as given. The assumption of a constant rate implies that the distribution of a firm's innovation arrival time is distributed exponentially, with parameter $$\lambda$$.

R&D race models have helped economists answer a range of questions, from the effect of competition on innovation [(Loury 1979)](https://academic.oup.com/qje/article-abstract/93/3/395/1890051)[(Lee and Wilde 1980)](https://academic.oup.com/qje/article-abstract/93/3/395/1890051), to the impact of information inequalities between innovating firms [(Choi 1991)](https://www.jstor.org/stable/2600992)[(Awaya *et al.* 2021)](https://www.journals.uchicago.edu/doi/abs/10.1086/711953). However, in every use of the model that I've seen, it's always assumed that firms can perfectly patent their innovation. Once a firm discovers the innovation, they secure a patent and the game ends.

Most industries do not appear to exhibit such behavior. Instead, firms continue to innovate and enter after the first firm has discovered the initial innovation [(Levin *et al*. 1985)](https://www.jstor.org/stable/1805564). Thus, relaxing the patent assumption allows us to more accurately explore how marketets evolve. I demonstrate that we should expect the rate of firm entry to decrease over time. As firms enter, less firms are left innovating, increasing the amount of time between successful innovations. A corollary of this finding is that we should expect the rate of innovation to decrease over time. I also characterize the problem firms face when deciding whether or not to enter such an R&D race.

### The Model

To enter the market, firms must conduct research in order to discover some new innovation. Once the firm successfully innovates, they earn a flow of profits $$V_i$$ that changes based on the quantity of firms $$i$$ currently in the market. We assume that $$V_i$$ is non-increasing in $$i$$, and that $$V_i \to 0$$ as $$i \to \infty$$. This is quite a reasonable assumption: Such behavior is exhibited in both Cournot and Bertrand competition, and it's difficult to imagine a market exhibiting anything to the contrary. As firms enter the market over time, the profit flows for each firm decrease until the market eventually exhibits perfect competition. 

A firm must pay a fixed cost $$c$$ in order to enter the innovation race. Think of $$c$$ as the cost of setting up a lab to discover the innovation necessary to enter the market.  We assume no variable costs for now, but I may amend this in the future. Once a firm pays the fixed cost $$c$$, the distribution of the arrival time of their innovation is $$Exp(\lambda)$$, where $$\lambda$$ is the exogenous innovation rate present in that market. This rate remains constant no matter how many firms have already innovated. Note that this implies zero spillover between innovations---it doesn't become easier for firms to innovate once the initial innovation is discovered. I'll explore the implications of the alternative in the future. Let $$r$$ be the interest rate. This comes into play later whenever firms decide whether or not to enter the R&D race based on discounted expected profits.

First, we explore how the market evolves over time. Assume $$n$$ firms enter the R&D race. Firms will discover innovations and enter the industry at different points in time. Let $$\tau_1, \tau_2, ..., \tau_n$$ be the times at which firm $$1, 2, ..., n$$ innovates, and let $$\tau_{(1)}, \tau_{(2)},...,\tau_{(n)}$$ be the arrival times of the first, second, and $$nth$$ innovation. In order to understand how the composition of the market will change over time, we must understand the distribution of these $$\tau_{(i)}$$.

To find the distribution of each $$\tau_{(i)}$$, we define $$X_1, X_2, ..., X_n$$ as the interarrival times between each innovation. Thus, $$X_i$$ describes the time between the $$i - 1$$ and $$i$$th successful innovation. We begin by defining $$X_1$$ and subsequently define $$X_i$$ generally.

In order to find the distribution of $$X_1$$, note that

$$
P(X_1 < t) = 1 - P(X_1 >t) = 1 - P(\tau_1 > t, \tau_2 > t,..., \tau_n > t).
$$

$$X_1$$ can be interpreted as the minimum time necessary for at least one of the firms to innovate. Thus, the CDF of $$X_1$$ is the probability that at least one firm innovates before time $$t$$. The compliment of this probability is the probability that every firm takes more than time $$t$$ to innovate. Since each $$\tau_i$$ is independent,

$$
1 - P(\tau_1 > t, ..., \tau_n > t) = 1 - P(\tau_1 > t)P(\tau_2 > t)...P(\tau_n >t).
$$

Notice that since $$\tau_i \sim Exp(\lambda)$$, $$P(\tau_i > t) = 1 - P(\tau_i < t) = 1 - (1 - e^{-t \lambda}) = e^{-t \lambda}$$. Therefore,

$$
1 - P(\tau_1 > t)P(\tau_2 > t)...P(\tau_n >t) = 1 - e^{-tn\lambda}.
$$

But this is just the CDF of an exponential random variable with parameter $$n\lambda$$. Thus, 

$$
X_1 \sim Exp(n\lambda).
$$

We can define $$X_2$$ in the same manner. This is because the exponential distribution is *memoryless*---the distribution of arrival times does not depend on the amount of time already spent conducting R&D. Each firm faces the same instantaneous probability of innovating no matter how long they've already been attempting to innovate. Therefore, the only difference between $$X_1$$ and $$X_2$$ is that there are now only $$n-1$$ firms still searching for an innovation. More generally, $$X_i$$ is only dependent on the fact that $$n - (i- 1)$$ firms are still searching for an innovation. Thus,

$$
X_i \sim Exp[\lambda(n - (i - 1))].
$$

Now that we've defined the distribution of the interarrival times, we can describe the distribution of each $$\tau_{(i)}$$---the arrival time of the $$i$$th innovation. Notice that

$$
\tau_{(i)} = \sum_{k = 1}^i X_k.
$$

The time of the $$i$$th innovation is just the sum of all of the proceeding interarrival times. This leads us to our first proposition: 

**Proposition 1.** *The expected rate of firm entry decreases over time.*

*proof.* First, notice that

$$
E[\tau_{(i)} - \tau_{(i - 1)}] = E[X_i].
$$

Since $$X_i \sim Exp(\lambda(n - i + 1))$$,

$$
E[X_i] = \frac{1}{\lambda(n + 1 - i)}.
$$

Thus, the expected time between $$\tau_{(i)}$$ and $$\tau_{(i - 1)}$$ is increasing in $$i$$. Therefore, there will be more time between later expected firm entries than earlier ones. $$\blacksquare$$

**Corollary.** *The expected rate of innovation decreases over time.*

*proof.* This is just a refraining of Proposition 1. Firms only enter once they innovate. $$\blacksquare$$ 

Now we can characterize the problem facing firms who are deciding whether or not to enter the R&D race. Let $$B$$ be the benefit incurred by a firm who enters the race. The cost of entering is $$c$$ as previously stated. A firm will only enter the market if $$E[B] \ge c$$. Therefore, we need an expression for $$E[B]$$. Let $$Y$$ be the relative position of the firm's innovation. For example, if the firm innovates first, $$Y = 1$$. If the firm innovates last, $$Y= n$$. Notice that

$$
E[B] = E[E[B | Y]] = \sum_{k = 1}^n P(Y = k)E[B | Y = k],
$$

by the law of total probabilities. Each firm in the race has the same chance of finishing in any position since they are identical. Thus, $$P(Y = k) = 1/n$$ for all $$k$$. To simplify notation, let $$B \vert Y = k$$ be $$B_k$$. Thus,

$$
E[B] = \frac{1}{n} \sum_{k = 1}^n E[B_k].
$$

Now we will define the distribution of the $$B_k$$ random variables. To do so, we first define $$b_1, b_2, ..., b_n$$ as the interarrival benefits between innovations. Here, $$b_i$$ is the discounted profits that firms in the market earn between the $$i$$th and $$i + 1$$ innovation. Notice that

$$
b_i = \int_{\tau_{(i)}}^{\tau_{(i + 1)}} V_i e^{-tr} \: dt = \frac{V_i}{r}
(e^{\tau_{i + 1}} - e^{\tau_i}).
$$

Firms earn $$V_i$$ profits between the $$i$$th and $$i + 1$$ innovation, and these profits are discounted according to the time they are earned. The arrival times of these innovations are $$\tau_{(i)}$$ and $$\tau_{(i + 1)}$$, whose distribution we defined above. Also notice that

$$
B_k = \sum_{i = k}^n b_i = \frac{1}{r} \sum_{i = k}^n V_i (e^{\tau_{i + 1}} - e^{\tau_i}). 
$$

The profit conferred to the $$i$$th innovator is simply the sum of all inter-arrival profits following their entry into the market.

Now that we've defined $$B_k$$, we can express the expected benefit of entering the R&D race. Replacing our $$B_k$$ terms and simplifying, we find that

$$
\begin{aligned}
E[B] &= \sum_{k = 1}^n \sum_{i = k}^n \frac{1}{n} \cdot \frac{V_i}{r} (e^{E[\tau_{i + 1}]} - e^{E[\tau_i]}) \\
&= \sum_{i = 1}^n \frac{i}{n} \cdot \frac{V_i}{r} (e^{E[\tau_{i + 1}]} - e^{E[\tau_i]}).
\end{aligned}
$$

The simplified expression is actually quite intuitive. Think of the time between innovations as stages of the race, where stage 1 is the time between the first and second innovation. The first term $$i/n$$ is the probability of being in the market by stage $$i$$. The probability of being in the market in the first stage is of course $$1/n$$, since only one firm will have entered the market by that point. The probability of being in the market in the second stage is $$2/n$$, since two firms will have entered at that point, and so on. The second term is the benefit conferred in stage $$i$$ to the firms that have already entered the market. And from above, we know that

$$
E[\tau_{(i)}] = \sum_{k = 1}^{i} \frac{1}{\lambda(n - k + 1)}.
$$

Now that we have defined $$E[B]$$, we can clearly express the problem firms face when deciding whether or not to enter the R&D race. Firms enter up until $$n^*$$, where

$$
\sum_{i = 1}^{n^*} \frac{i}{n^*} \cdot \frac{V_i}{r} (e^{E[\tau_{i + 1}]} - e^{E[\tau_i]}) = c.
$$

We can show that $$n^*$$ is unique and finite. We can also explore how our parameters effect $$n^*$$. For example, is $$n^*$$ increasing or decreasing in $$\lambda$$, the instantaneous rate of innovation? The answer is not immediately clear. If $$\lambda$$ is too low, innovations may be too difficult to find, and less firms may enter. However, a lower $$\lambda$$ also implies a greater amount of time between innovations, which confers greater profits to the firms already in the market. This may induce more firms to enter. I hope to answer questions like this in the future using this framework.