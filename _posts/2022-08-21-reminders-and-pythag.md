---
layout: post
title:  "Meeting Reminders (Plus a Nice Problem)"
author: warith
---

# Meeting Reminders for the Week of 08/22/22 (and a Pythagorean Problem)

## Meetings
As a reminder...
- The first general UIL (math) meeting is **08/26** in LFC's B110
- Computer Science will first meet on **09/01** in LFC's Lower E Pod
- Science will first meet on **09/07** in LFC's Lower E Pod

## A "Small" Pythagorean Problem

### The Statement
Find all Pythagorean Triples i.e. Find all non-negative integral triples $(x, y, z)$ that satisfy $x^2 + y^2 = z^2$ 

### Turn a Diophantine into a Unit Circle
If we divide each side of our original equation by $z^2$, we get the new equation $x_1^2 + y_1^2 = 1$. This makes our equation a bit easier, so we're solving for 
rational pair $(x, y)$ that satisfies a unit circle instead.

### A Nice Slope Trick
Say that we pick a point $P = (x_P, y_P)$ on a unit circle, and draw a line with rational slope that goes through $P$ i.e. $y - y_P = \dfrac{m}{n}(x - x_P)$ such 
that $\dfrac{m}{n}$ is rational. We can prove that if this hits the unit circle at another point $Q$, its coordinates will **also** be rational!

#### Small Proof
We can start out this proof by saying $y = \dfrac{m}{n}x + 1$ via slope and $x^2 + y^2 = 1$ via the unit circle. Eliminating $y$ as we know $P = (0,1)$ satisfies 
both equations, we get $x^2 + \left( \dfrac{m}{n}x + 1 \right)^2 = 1$.

- The coefficients of such an equation are rational
- By Vieta's Formulas, the sum of the roots are rational
- As one root must be rational as we used rational point $P$, the other root must be rational
- If $x$ is always rational, we can then say $y$ will always be rational
- This means that both $x$ and $y$ are rational, stating that point $Q$ is rational `Q.E.D.`

### Some More Algebra
Note that we can expand the above proof with some logic. Since a rational point $Q$ must be connected to rational point $P$ through a rational slope, drawing every 
rational line that goes through $P$ will hit *every* rational point on the circle!

Expanding the combined equation from our proof, we get $\dfrac{m^2+n^2}{n^2}x^2 + \dfrac{2m}{n}x = 0$. As we already know $0$ is a root, solving for the other root 
gives us $x = \dfrac{-2mn}{m^2+n^2}$ and $y = \dfrac{n^2-m^2}{m^2+n^2}$. Tidying up, we get our final triple as:

$$(x,y,z) = (2mn, n^2-m^2, n^2+m^2)$$