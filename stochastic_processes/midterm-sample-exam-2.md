---
title: Sample midterm 2, Stochastic Processes
author: Pierre C Bellec
documentclass: amsart
papersize: a4paper
urlcolor: blue
output: pdf_document
header-includes:
  - \usepackage{amsmath}
  - \usepackage{nccmath}
  - \usepackage{autonum}
---


- This document in PDF: <https://github.com/bellecp/CC-BY-SA-teaching-material/blob/master/stochastic_processes/midterm-sample-exam-2.pdf>
- Source code (markdown/latex): <https://github.com/bellecp/CC-BY-SA-teaching-material/blob/master/stochastic_processes/midterm-sample-exam-2.md>
- License: CC-BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0/>


## Length: 1h and 20 minutes.


## Contraction in expectation

Let $\mathcal X$ be the set of functions from $\{1,...,n\}$ to $\{0,1\}$,
and for any two functions $x,y\in \mathcal X$, let $\rho(x,y)$ be the number of disagreements,
\begin{equation}
\rho(x,y) = | \{i=1,...,n : x(i) \ne y(i) \} | = \sum_{i=1}^n I_{x(i)\ne y(i)}.
\end{equation}
Consider a transition matrix $P(\cdot,\cdot)$ on $\mathcal X$
and a random mapping representation, given by a deterministic function $f:\mathcal X\times [0,1]\to \mathcal X$ and a random variable $Z\sim Unif[0,1]$ with 
$\mathbf P(f(x,Z)=y) = P(x,y)$. We also consider an iid sequence $(Z_t)_{t\ge 0}$
of independent copies of $Z$
and the Grand Coupling defined by $X_0^x = x$ and $X_t^x = f(X_{t-1}^x, Z_t)$ for all $x\in\mathcal X$ and all $t\ge 0$.

For the first four questions, we assume that there exists some $a>0$ such that
for all $x,y$ with $\rho(x,y)=1$ we have $\mathbf E[\rho(f(x,Z),f(y,Z)]\le e^{-a}$.

1. Prove that $\rho$ satisfies the triangle inequality $\rho(x,z)\le\rho(x,y)+\rho(y,z)$ for any states $x,y,z\in\mathcal X$.
2. Prove that $\mathbf E[\rho(f(x,Z), f(y,Z))]\le \rho(x,y) e^{-a}$ for all $x,y\in\mathcal X$.
3. Prove that $\mathbf E[\rho(X_t^x,X_t^y)] \le \rho(x,y) e^{-at}$ for any $t\ge 1$ and all $x,y\in\mathcal X$. Clearly explain in words every steps of your reasoning.
4. Provide an upper bound on the mixing time $t_{mix}(\epsilon)$ for any $\epsilon \in (0,1)$.

## Lower bound on the mixing time for a lazy random walk on regular graph

Let $d\ge 3$. Consider an undirected connected
graph $G=(V,E)$ such that each vertex has __exactly__ $d$ neighbors.
Let $P$ be the __lazy__ random walk on $V$ (the chain stays on the current vertex with probability $1/2$, and jumps to a neighbor with probability $1/(2d)$).

1. Draw such a graph for $d=3$ and $|V|=8$ (these values of $d$ and $|V|$ apply ONLY to this question).
2. Prove that the uniform distribution is stationary. 
3. Why is the stationary distribution unique? Denote by $\pi$ the stationary distribution.
4. Let $V_t^x = \{y\in V: P^t(x,y) > 0\}$ be the subset of $V$ of states accessible from $x$ after $t$ steps. Show that
$|V_t^x| \le (d+1)^t$.
5. Prove that $\|P^t(x,\cdot)- \pi\|_{TV} \ge 1 - (d+1)^t/|V|$.
6. Prove a lower bound on $t_{mix}(1/4)$. Clearly explain your reasoning.



