---
layout: post
title:  "Bundle Learning"
date:  2023-1-30
categories: Economics
use_math: true
---

### Intro

I was introduced to loss aversion while reading *Thinking, Fast and Slow*, by Daniel Kahneman. I had just finished my Intermediate Microeconomics course and was enamored with the tools it provided---especially the the indifference curve. However, while reading Kahneman's book, I learned that he wasn't quite as impressed with the tool as I was. Kahneman introduces the indifference curve as a "surprising case of theory-induced blindness" (290). He argues that an indifference curve is meaningless without a *reference point*---the bundle currently held by the individual. This is due to loss aversion: The cost of losses hurts more than the benefits of gains. Thus, the set of bundles we are indifferent between depends on the bundle that we're currently holding.

To illustrate his point, Kahneman asks us to imagine an individual selecting between different benefit packages at a new job. Package $$a$$ includes a higher wage but fewer vacation days; package $$b$$ includes more vacation days but a lower wage. Before our individual starts her job, she's indifferent between the two options, so she randomly selects $$a$$. Now imagine that a few years pass, and she's forced by her manager to switch from package $$a$$ to $$b$$. Common sense, as well as loss aversion, would predict that she wouldn't be too happy with the change---Kahneman argues that she would feel the costs of the decreased wage more than the benefit of the additional vacation time. Thus, once a reference point is set, individuals really aren't indifferent between points along the same indifference curve.

It hurt to see my favorite economic tool torn down, but Kahneman's point is well-put. A person's current bundle undoubtedly effects their future bundle selections. However, loss aversion appears to fair worse in an extension of the same situation. Imagine that, after being forced to switch from $$a$$ to $$b$$, the individual's manager calls later that day and lets here know that the earlier forced change was actually unnecessary---she is free to switch back to package $$a$$ if she would like. What would we expect her to do? Common sense suggests that since she was upset about the change earlier that same day, she would gladly switch back to package $$a$$. However, loss aversion predicts the opposite result: Now that her reference point is package $$b$$, she should feel the losses from decreasing her vacation time more than she feels the benefits of increasing her wage. Thus, it predicts that she would decide to keep package $$b$$.

This result seems unsatisfactory. In order to understand why loss aversion lead us astray in this extension but not in Kahneman's original example, we must understand how the contexts of the decisions differed. Whenever the manager induced the switch from $$a$$ to $$b$$, our individual had held package $$a$$ for a long time. It seems likely that she would have been less upset if the change was made after only a week of work instead of after several years. Another key difference is that in the second case, the individual already had experience with package $$a$$---she had held package $$a$$ for several years before being forced to switch to package $$b$$. Intuitively we understand that this makes it easier to switch back to $$a$$. Both differences highlight the importance of experience gained from  using bundles over time

In what follows, I present a framework I call bundle learning in order to address the important role that experience plays when selecting bundles. The basic assumption of bundle learning is that we get better at implementing our bundles the longer that we use them---in other words, we learn how to best use bundles over time. Anyone who has moved cities has experienced this phenomena: You may have the same resources at your disposal on day one as you do on day 100, but you become much more proficient at making the most of them by that hundredth day. I model both loss aversion and bundle learning and apply both to our motivating example. I demonstrate that the two frameworks agree in the Khaneman's orignal example, whereas only bundle learning agrees with common since in the example's extension. I also demonstrate how bundle learning acts as an alternative explanation of the endowment effect.

### Modeling Loss Aversion and Bundle Learning

Here I formalize the concepts of loss aversion and bundle learning. Notice that both frameworks only apply to goods that we hold and use over time, rather than perishable goods that we imediately consume: Under loss aversion, your reference point is the bundle that you currently possess, implying that the bundle isn't simply earten. Likewise, under bundle learning, you must hold your bundle over time in order to learn how to best use it. Example bundles may be the city you choose to live in, the car you choose to drive, or the benefits package you choose at a new job. Thus, individuals in my formalization of loss aversion and bundle learning select between goods which they will hold for all future time, $$t \in [0, \infty)$$. In other words, individuals will be deciding which bundle to hold and use for the foreseeable future. 

I assume that individuals have preferences over bundles described by utility function $$u$$. Thus, if a person would prefer to use bundle $$x$$ over bundle $$y$$ for the foreseeable future, $$u(x) > u(y)$$. However, the bundles themselves are not the only inputs to $$u$$. Under loss aversion, $$u$$ is a function of both the bundle $$x$$ and the individual's reference point $$r$$. The core assumption of loss aversion is that

$$
u(x, r \ne x) = u(y, r) \implies u(x, r = x) > u(y, r).
$$

That is, if a person is indifferent between using $$x$$ and $$y$$ whenever $$x$$ is not that person's reference point, they will prefer using $$x$$ whenever it is. Once they hold $$x$$, they feel the losses from switching away more than they feel the gains.

Within bundle learning, $$u$$ is a function of both the bundle $$x$$ and $$t_x$$, the amount of time that the individual has used that bundle. The core assumption is that

$$
\frac{\partial u}{\partial t_x} > 0,
$$

or that utility increases as one gains more experience with bundle $$x$$. The longer we hold a bundle, the better we get at using it. An implicite assumption here is that $$u$$ is continuous in $$t_x$$. An imediate prediction of bundle learning is that

$$
u(x, t_x) = u(y, t_y) \implies u(x, t_x + \epsilon) > u(y, t_y), \quad \text{where} \quad \epsilon > 0.
$$

That is, if a person is indifferent between using $$x$$ and $$y$$ whenever they've used $$x$$ for time $$t_x$$, they will prefer using $$x$$ once they've used it for any time longer than $$t_x$$. Once they gain more experince with $$x$$, they learn how to better use it, and thus they prefer it.

Let us now return to the individual in Kahneman's example. Before she selected her benefit package from set $$\{a, b\}$$, she was indifferent between the two: $$u(a, r \ne a) = u(b, r \ne b)$$ under loss aversion, and $$u(a, t_a = 0) = u(b, t_b = 0)$$ under bundle learning (neither package is her reference point, and she also doesn't have experience with either).

We assumed that she randomly selected bundle $$a$$. Time $$t$$ passes. Now $$r = a$$ and $$t_a = t$$: Her reference point is now bundle $$a$$ under loss aversion, and she has gained $$t$$ experience under bundle learning. Therefore, it is clear that she would not be happy with a forced switch to bundle $$b$$ under either framework: Loss aversion tells us that $$u(a, r = a) > u(b, r = a)$$: Since she was indifferent between the bundles before, she prefers bundle $$a$$ now that that's her reference point. Likewise, bundle learning tells us that $$u(a, t_a = t) > u(b, t_b = 0)$$: Since she was originally indifferent, she prefers bundle $$a$$ now that she has experience using it. Both frameworks reach the same conclusion in Kahneman's original example.

This is not the case in the extension of the example. Remember that soon after the forced switch to bundle $$b$$, our individual is once again given a choice between the two bundles. Assume $$s$$ time has passed, and that $$s < t$$. Our individual had held bundle $$a$$ for a long time, and was only forced to switch to $$b$$ for a short amount of time before being allowed to switch back. Under loss aversion, her reference point is now bundle $$b$$. Thus,

$$
u(a, r = b) < u(b, r = b) \quad \text{since} \quad u(a, r \ne a) = u(b, r \ne b). 
$$

That is, she will decide to keep bundle $$b$$ since she now feels the losses from switching away more than she feels the gains. However, this conclusion seems unlikely, especially whenever $$s$$ is made very small. If she prefers $$a$$ whenever she is forced to switch to $$b$$, we intuitively know that she would gladly switch back if given the chance soon after. 

Bundle learning formalizes this. Under bundle learning, we now have $$t_b = s < t$$. Since $$u$$ is continuous in $$t_x$$, we know that if $$s$$ is small enough, we still have 

$$
u(a, t_a = t) > u(b, t_b = s).
$$

That is, since our individual preferred bundle $$a$$ whenever she only had experience with $$a$$, there is always some amount of time after the forced switch in which she'd be happy to switch back. Thus, the framework of bundle learning offers a conclusion that matches our intuition, whereas the framework of loss aversion does not. 

### Bundle Learning and the Endowment Effect

Bundle learning is also a potential explanation of the endowment effect. The endowment effect is present whenever a person's willingness to pay ($$WTP$$) for a good is less than their willingness to accept ($$WTA$$). For example, before someone owns their mug, they may be willing to pay at most $5 for it. This is their $$WTP$$. Once they own the mug, they may only be willing to sell it for a price greater than $5. This is their $$WTA$$. Classical economic theory predicts that $$WTP = WTA$$; however, the endowment effect has been observed experimentally in several contexts, where $$WTP < WTA$$. Loss aversion is the most popular explanation of this effect---bundle learning offers an alternative view.

To demonstrate this, we first define a function $$m(u)$$ which maps utility to the amount of money that confers that same level of utility. Assume that 

$$
\frac{\partial m}{\partial u} > 0,  
$$

or that you must be given more money in order to reach higher levels of utility---in other words, assume money is a good. Let $$x$$ be some bundle. Before an individual holds bundle $$x$$, their utility is given by $$u(x, t_x = 0)$$. Their corresponding willingness to pay for bundle $$x$$ would be $$m(u(x, t_x = 0)) = m_0$$. Now assume that they own good $$x$$ for time $$t$$. Therefore, $$m(u(x, t_x = t)) = m_t$$ is now their willingness to accept. But by bundle learning, $$u(x, t_x = 0) < u(x, t_x = t)$$, which implies that $$m_0 < m_t$$. Therefore, $$WTP < WTA$$. This is the endowment effect.

We could also conduct an experiment in order to determine how bundle learning fares compared to loss aversion as an explanation of the endowment effect. The key difference between bundle learning and loss aversion is that bundle learning is a function of time. Under loss aversion, the difference between a person's $$WTP$$ and their $$WTA$$ doesn't change with time. Under bundle learning, this difference should increase the longer that the good is held. As someone gains experience with the good over time, the good becomes more valuable, and thus their $$WTA$$ will increase.

To test this, a professor could give good $$x$$ to half of her students in two different classes. In the first class, she could ask the students who did not receive the good to report their $$WTP$$, and those that did receive the good to report their $$WTA$$. In the second class, she could do the same thing but at a later date, after the students endowed with good $$x$$ are given more time to gain experience with it. Under loss aversion, $$WTP$$ and $$WTA$$ should be about the same in both classes. Under bundle learning, $$WTP$$ across classes should stay consistent, whereas $$WTA$$ for the endowed students in the second class should be greater: They gain more experience with the good and thus value it more. The result of the experiemnt could provide evidence in favor of one framework over the other as an explanation of the endowment effect.