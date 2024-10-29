---
layout: post
title: Flipping a coin
---


This is a question from the book *The Green-Eyed Dragons and Other Mathematical Monsters*

(a) Consider the following game. You flip a coin until you get a tails. The number of dollars you win equals the number og coins you end up flipping. (So if you immediately get a tails, you win one dollar; if you get one heads before a tails, you win two dollars, etc.) What is the expectation value of your winnings?

(b) Play the same game, except now let the number of dollars you win be equal to $2^{n-1}$, where n is the number of coins you end up flipping. What is the expectation value of your winnings now? Does your answer make sense?

Answer:

Part (a):

$$ E = \sum _{n=1} ^{\infty} \frac{n}{2^n} = 2$$

$$ 1/2 + 2/4 + 3/8 + 4/16 + ... = 1 + 1/2 + 1/4 + ... = 2$$

Part (b):

$$ E = \sum _{n=1} ^{\infty} \frac{2^{n-1}}{2^n} = n/2$$

In this case, the expectation over infinity trails is far from the real experiment (not infinity). How much money would a person be willing to put up for the opportunity to play these N games? 
