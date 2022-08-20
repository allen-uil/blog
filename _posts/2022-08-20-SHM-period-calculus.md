---
layout: post
title:  "A Derivation of the SHM Period Formula with Calculus"
author: warith
---

# A Derivation of the SHM Period Formula with Some Calculus
This was a post that Anthony wanted me to do, so here we go!

## Variables
Let's get some variables out of the way first, so I can explain this more fluently.
- $x(t)$ is the SHM position as a function of time
- $v(t)$ is the SHM velocity as a function of time
- $a(t)$ is the SHM acceleration as a function of time
- $A$ is the amplitude of the oscillator: how far it traverses from the starting position in $\text{m}$
- $T$ is the period: how long it takes to complete one cycle in $\text{s}$
- $m$ is the mass of the object oscillating in $\text{kg}$
- $k$ is the spring constant, measured in $\dfrac{\text{N}}{\text{m}}$

## Deriving $a(t)$ with Calculus
We start out with the formula for position in SHM (**S**imple **H**armonic **M**otion)

$$x(t) = A \cos \left( \dfrac{2\pi t}{T} \right)$$


We can state velocity as a time derivative of position, so taking the derivative of $x(t)$ we get:

$$v(t) = \dfrac{\mathrm dx}{\mathrm dt} = -A \left( \dfrac{2\pi}{T} \right) \sin \left( \dfrac{2\pi t}{T} \right)$$


We can then state a similar relation for acceleration: acceleration is a time derivative of velocity.

$$a(t) = \dfrac{\mathrm dv}{\mathrm dt} = \dfrac{\mathrm d^2 x}{\mathrm dt^2} = -A \left( \dfrac{2\pi}{T} \right)^2 \cos \left( \dfrac{2\pi t}{T} \right)$$


After some rearranging, we can substitute $x(t)$ into the equation of $a(t)$, representing acceleration as a function of position.

$$-A \left( \dfrac{2\pi}{T} \right)^2 \cos \left( \dfrac{2\pi t}{T} \right) = - \left (A \cos \left( \dfrac{2\pi t}{T} \right)\right ) \left( \dfrac{2\pi}{T} \right)^2 = -\dfrac{4\pi^2}{T^2}x(t) = a(t)$$


## Deriving $a(t)$ without Calculus
Newton's second law states that $F = ma$, and Hooke's law states that $F_\text{restoration} = -kx$

If we set these forces equal to each other and solve for acceleration $(a)$, we get $a = -\dfrac{kx}{m}$, and as functions of time we get $a(t) = -\dfrac{kx(t)}{m}$

## The Final Algebra
We now have two equations equal to $a(t)$, so we just need to set these equal to each other and solve for $T$.

$$-\dfrac{4\pi^2}{T^2}x(t) = -\dfrac{kx(t)}{m}$$

$$-4\pi^2 x(t) = T^2 \cdot -\dfrac{kx(t)}{m}$$

$$T^2 = -4\pi^2 x(t) \div -\dfrac{kx(t)}{m}$$

$$T^2 = \dfrac{4\pi^2 m}{k}$$

$$T = \boxed{2\pi \sqrt{\dfrac{m}{k}}}$$
