---
layout: page
title: "Final assignment 2021"
use_math: true
--- 
Consider the 2 consecutive first order reactions:


<center>A->B->C</center>

$k_1$ is the reaction rate constant for the first reaction and its value is
$0.15\ \mathrm{min^{-1}}$

$k_2$ is the reaction rate constant for the second reaction and its value is
$0.35\ \mathrm{min^{-1}}$

At t=0 the concentration of A is 2 mol/L, while the concentration of B and C are
both 0.

The concentration of species A, B and C, as a function of time, is given by the
following equations:

$ [A] = [A]_0 \exp(-k_1 t)$

$[B] = [A]_0 \frac{k_1}{k_2 - k_1} \big(\exp(-k_1 t) - \exp(-k_2 t)\big)$

$[C] = \frac{[A]_0}{k_2 -k_1} \big[k_2 \big(1-\exp(-k_1 t)\big) -
k_1\big(1-\exp(-k_2 t)\big)\big]$

where $[A]_0$ is the initial concentration of A.


* Define 3 functions describing the change in concentration of each of the three
chemical species as a function of time.
* Plot the time evolution of [A], [B] and [C] from t = 0 to t = 20 min. You
should also label the axes and add a legend to the plot.
* Estimate **when** the concentration of B reaches its maximum. What is the
maximum value of [B]?
* Evaluate how the maximum value of [B] and the corresponding time would change,
if the second reaction had a rate constant $k_2$ of $0.10\ \mathrm{min^{-1}}$.
