---
title: Sample midterm 1--Stochastic Processes
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

- This document in PDF: <https://github.com/bellecp/CC-BY-SA-teaching-material/blob/master/stochastic_processes/midterm-sample-exam-1.pdf>
- Source code (markdown/latex): <https://github.com/bellecp/CC-BY-SA-teaching-material/blob/master/stochastic_processes/midterm-sample-exam-1.md>
- License: CC-BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0/>

## Length: 1h and 20 minutes.


## Problem 1: Unicity of the optimal coupling

Consider two distributions on $\{1,2,3,4\}$ given by 
\begin{equation}
    \mu = \left(\frac 1 4, \frac 1 4, \frac 1 4, \frac 1 4\right) \qquad \text{ and }\qquad
    \nu = \left( \frac 1 8, \frac 3 8, \frac 1 8, \frac 3 8\right).
\end{equation}

1. Provide an optimal coupling of $(\mu,\nu)$ as a $4\times 4$ matrix (it does not matter whether you provide the matrix or its transpose).
2. Provide another optimal coupling of $(\mu,\nu)$, **different** than the one obtained in question 1.
Highlight (with color, a circle or otherwise) the entries of the matrix that are different from your answer in question 1. Conclude that the optimal coupling is not always unique.
3. Provide, as a $4\times 4$ matrix, the coupling of $(\mu,\nu)$
for which the two coordinates are independent.

## Problem 2: A metropolis chain

Consider a connected undirected graph $G=(V,E)$. We consider a base chain on $\mathcal X = V\times V$ that consists of two particles moving as a simple random walk
on the graph, independently of each other. In other words
\begin{equation}
    \Psi\Big( (u_1,u_2), (v_1,v_2) \Big) = 
        1 / \big( |N(u_1) |\; |N(u_2)| \big)  \text{ if both } v_1\in N(u_1), v_2\in N(u_2),
\end{equation}
and
\begin{equation}
    \Psi\Big( (u_1,u_2), (v_1,v_2) \Big) = 
        0  \text{ if } v_1\notin N(u_1) \text{ or } v_2\notin N(u_2),
\end{equation}
for any four vertices $u_1,u_2,v_1,v_2$, where $N(v)\subset V$ is the set of neighbors of a vertex $v$ and $|N(v)|$ the cardinality of $N(v)$. 
(A vertex $v$ is not a neighbor of itself so that $v\notin N(v)$ always holds.)
We are interested in constructing a Markov Chain on $\mathcal X = V\times V$ with stationary distribution
\begin{equation}
    \forall (u_1,u_2)\in V\times V, \qquad \qquad 
    \pi( (u_1,u_2) ) = 
    \begin{cases}
        0 & \text{ if } u_1=u_2, \\
        1/Z & \text{ if } u_1\ne u_2,
    \end{cases}
\end{equation}
where $Z>0$ is a normalizing constant not depending on $u_1,u_2$.

1. Is the base chain symmetric? (Prove or disprove).
2. If you apply the Metropolis scheme to construct a Chain with stationary distribution $\pi$ from the base chain $\Psi$,
what is the acceptance probability 
\begin{equation}
    a\Big( (u_1,u_2), (v_1,v_2) \Big)
\end{equation}
to accept a move from the base chain? Clearly write and simplify $a( (u_1,u_2), (v_1,v_2) )$ and verify that the
detailed balance equations are satisfied. 


## Problem 3: Two irreducible and aperiodic chains that move independently will eventually meet

Consider a transition matrix $P$ and the transition matrix $Q$ 
over the set $\mathcal X\times \mathcal X$ defined by
\begin{equation}
    Q\Big( (x_1,x_2), (y_1,y_2) \Big) = P(x_1,y_1) P(x_2,y_2).
\end{equation}
In words, in the chain $Q$, each coordinate is updated independently according to $P$.
Denote by $(X_t,Y_t)_{t\ge 0}$ a Markov chain valued in $\mathcal X\times \mathcal X$ with transition matrix $Q$
($X_t$ is the first coordinate, $Y_t$ is the second coordinate).

We assume that $P$ is aperiodic and irreducible, so that by a result of Chapter 1, there exists an integer $r>0$
and positive real $\epsilon>0$ such that
\begin{equation}
    \forall t\ge r, \forall x,y\in\mathcal X, \quad P^t(x,y) = \mathbf P_x[X_t = y] \ge \epsilon > 0.
\end{equation}

1. Show that $Q$ is irreducible.
2. Show that $Q$ is aperiodic.
In the next question you may use without proof the following fact:    
**Fact I**: if $\bar P$ is an irreducible transition matrix of a Markov Chain $(M_t)_{t\ge 0}$ on a set $\bar{\mathcal{X}}$, then there exists an integer $\bar r>0$ and real number $\bar \epsilon \in (0,1)$ such that for any integer $k\ge 1$,
\begin{equation}
    \mathbf P_{\bar x}( \tau_{\bar y}^+ > k\bar r ) \le (1-\bar\epsilon)^k
    \qquad
    \text{ where }
    \quad
    \tau_{\bar y}^+ = \min \{ t\ge1 : M_t = \bar y \},
\end{equation}
for any two states $\bar x,\bar y\in \bar{\mathcal{X}}$.   
3. Using the Markov Chain $(X_t,Y_t)_{t\ge 0}$ from the previous page, show that
\begin{equation}
    \forall k\ge 1, \quad\max_{x,y\in\mathcal X}\| P^{kr}(x, \cdot) - P^{kr}(y,\cdot) \|_{TV} \le \alpha^k
\end{equation}
for some $\alpha\in (0,1)$ and some integer $r>0$.
4. (Extra credit question, if you have time). Prove **Fact I** above.

