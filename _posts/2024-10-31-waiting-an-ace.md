---
layout: post
title: Waiting for An Ace
tags: [Green-eyed Dragon]
mathjax: true
---

How many cards do you need to deal from a standard deck, on average, to get your first ace? A standard deck contains 52 cards, four of which are aces.

"On average"--the question is asking what the expectation is for the position of the first ace.

$$C_{52}^4$$

- the first position is 1
  $$P(1)=\frac{4}{52}$$
- the first position is 2
  $$P(2)=\frac{48}{52}\frac{4}{51}$$
- the first postition is 3
  $$P(3)=\frac{48}{52}\frac{47}{51}\frac{4}{50}$$
- until the first position is 49
  $$P(49)=\frac{4}{52}\frac{3}{51}\frac{2}{50}\frac{1}{49}$$

the expectation is
$$E=\sum_{k=1}^{49} 4k\frac{A_{48}^{49-k}}{A_{52}^{53-k}}=\sum_{k=1}^{49} k\frac{C_{52-k}^{3}}{C_{52}^{4}}$$

Really hard to calculate, try simpler conditions.

$$E(N,n)=\sum_{k=1}^{N+1-n} 4k\frac{A_{N-n}^{N+1-n-k}}{A_{N}^{N+1-k}}=?=\frac{N+1}{n+1}$$

- N=2, n=1, E=3/2
- N=3, n=1, E=1/3 \* (1+2+3)=4/2
- N=4, n=1, E=1/4 \* (1+2+3+4) =5/2
- N=3, n=2, E=1\* 2/3 + 2\* 1/3 \* 2/2= 4/3
- N=4, n=2, E=1\* 2/4 + 2\* 2/4 \* 2/3 + 3\* 2/4 \* 1/3=5/3

Guess the answer is
$$E(N,n)=(N+1)/(n+1)$$

---

It's easy to write
$$E(N,1)=\frac{1}{N}\times(1+2+...+N)=\frac{1}{N}\times \frac{N(N+1)}{2}=\frac{N+1}{2}$$

$$E(N,N-1)=1\times \frac{N-1}{N}+2\times \frac{1}{N}=\frac{N+1}{N}$$

$$E(N,N)=1$$
If you added one more ace (N doesn't change), how would that affect the result?

This change can happen at N-n positions, the additional ace sometimes could be the first ace, always add more chances to show an ace at one position, from 0 to 1, from 1 to 2, etc. At random position k.

$$E(N,0)=N+1$$

means will never happen

consider where is the last ace, which is symmetric to where is the first ace

| (1) 0 0 0 | 1 0 0 0 | 1 0 0 0   |
| --------- | ------- | --------- |
| (0) 1 2 3 | 4 5 6 7 | 8 9 10 11 |

divide the N+1 positions in to n+1 stacks

$$E(N,n)=\frac{N+1}{n+1}$$

---

Place all the cards randomly in a **circle**, add an (n+1)th ace. Now there are (N+1) cards. Let the location of the (n+1)th ace be the stating point, clockwise. The average clockwise distance to the next ace(which is the expection) is the same as the average distance between any other sucessive aces. There are n+1 ace-to-ace intervals, and there are N+1 cards, so the common average distance is (N+1)/(n+1).

---

So the answer to the stated problem is 53/5=10.6.
