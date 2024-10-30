---
layout: post
title: The Hotel Problem
tags: [Green-eyed Dragon]
mathjax: true
---

You are driving down a one-way road and pass a strip of a large number, N, of hotels. These all have different rates, arranged randomly. You want to maximize your chance of choosing the cheapest hotel, but you can't return to one you've passed up. Assume that your only goal is to obtain the cheapest hotel (the second cheapest is of no more value to you than the most expensive). If your strategy is to proceed past a certain fraction, x, of the hotels and then pick the next one that is cheaper than all the ones you've seen so far, what should x be? What, then, is your probability of success? Assume that N is very large, and ignore terms in your answer that are of subleading order in N.

In other words, if one is presented with a series of numbers in random order and N is very large, what is the probability of finding the minimum by skipping the first x and choosing the next number that is smaller than all the numbers considered?

There are two possible outcomes:
1. The minimum is not in the x
2. The minimum appears before the other numbers which are smaller than the numbers in x

$$P_k=\frac{1}{k+1}x(1-x)^{k+1}$$

A complex function of x and k, then, calculate the sum of $P_k$

原本在这一步尝试列出所有排列去计算概率，忽略了概率本身的便利。也忽略了达成条件的基本概率要求，每一步都有概率。要让 k 不那么模糊，是一个可以计算出确定概率的情况。

---

Assume H1 denote the cheapest hotel, H2 the second cheapest, etc.

- H1 in the first x, failure, $P=0$
- H2 in the first x, while H1 not, success, $P=(1-x)x$
- H3 in the first x, while H1 H2 not, and H1 shows before H2, success, $P=1/2(1-x)^2 x$

$$P(x)=0+x(1-x)+\frac{1}{2}x(1-x)^2+\frac{1}{3}x(1-x)^3+...=\sum_{k=1} \frac{1}{k}x(1-x)^k$$

Similar to the Taylor series $\ln (1-y)=-(y+y^2/2+y^3/3+...)$

$$P(x)=-x\ln x$$

the maximum P(x) happens when $x=1/e, P=1/e \approx 37\%$.

打开“购物”软件，同类产品一字排开，下滑浏览，当然你可以回头，那么多久决定要买哪一个呢？平台调整产品的顺序，暗暗操纵选择的结果。我能否打乱顺序，创造一个适合挑选的池子？多个池子，多次选择试验，得出最佳结果。

比如限定条件下取出 100 个商品，打乱顺序，多次按照 37%选取，比较获得的产品（价格不是唯一因素）。
