---
layout: post
title: A Recap of the 9/9 General Meeting
author: anthony
---

On September 9, 2022, I (Anthony) delivered a lecture on Vieta's Formulas and power sums. Unlike the previous lecture, I gave the audience members time to solve problems instead of trying to cover as much information as possible. I think this was a positive change, as you learn much more from problem solutions if you actually try to solve them first.

# Vieta's Formulas

Consider the equation $ax^2+bx+c=0$. Vieta's formulas state that if the two solutions (also called *roots*) to this equation are $p$ and $q$, then

$$ p+q = -\frac{b}{a} \qquad \text{and} \qquad pq = \frac{c}{a}. $$

The proof is straightforward: first divide the equation by $a$ to get

$$ x^2 + \frac{b}{a}x + \frac{c}{a} = 0, $$

then notice that the quadratic can also be written in the form

$$ (x-p)(x-q) = x^2 - (p+q)x + pq. $$

Since these two forms are equivalent, each term must also be equal. Thus, we can equate coefficents to get

$$ -(p+q) = \frac{b}{a} \qquad \text{and} \qquad pq = \frac{c}{a}, $$

from which the result follows.

The benefit of proving Vieta's Formulas like this is that this is easily extensible to all equations of degree greater than $2$. For example, for a cubic, the standard form equation can be written as

$$ x^3 + \frac{b}{a}x^2 + \frac{c}{a}x + \frac{d}{a} = 0 $$

and the factored form as

$$ (x-p)(x-q)(x-r) = x^3 - (p+q+r)x^2 + (pq+qr+pr)x - pqr, $$

so we can prove that

$$ p+q+r = -\frac{b}{a}, pq+qr+pr = \frac{c}{a}, pqr = -\frac{d}{a}. $$

In general, if the polynomial has degree $n$, let $a$ be the coefficient of $x^n$, $b$ be the coefficient of $x^{n-1}$, and $c$ be the constant term (the coefficient of $x^0$). Then,

* the sum of the roots is always $-\frac{b}{a}$.
* the product of the roots is $\frac{c}{a}$ if $n$ is even and $-\frac{c}{a}$ if $n$ is odd.

## Exercise: [2021 Spring AMC 10A/14](https://artofproblemsolving.com/wiki/index.php/2021_AMC_12A_Problems/Problem_12)

From the problem statement, Vieta's Formulas immediately tell us that the sum of the roots is $10$ and the product is $16$. The problem statement also tells us that all the roots are positive integers. Note that this is a degree $6$ polynomial, so there must be $6$ roots.

From some trial and error, we find that the roots are $2,2,2,2,1,1.$ Then we can write the polynomial in the form

$$ (z-2)(z-2)(z-2)(z-2)(z-1)(z-1). $$

Expanding this out and taking the $z^3$ coefficient gives us our final answer of $\boxed{-88}$.

## Problems

* [2015 AMC 10A/23](https://artofproblemsolving.com/wiki/index.php/2015_AMC_10A_Problems/Problem_23)

# Power Sums

There's no formula to this--it's just an approach that can solve problems. The best way to demonstrate this is to solve a problem using the power sums approach.

**Problem**: If $x+\frac{1}{x}=4$, find $x^2+\frac{1}{x^2}$.

**Solution**: Of course, you could solve for $x$ using the quadratic formula and plug it into $x^2+\frac{1}{x^2}$ to get the answer. However, there is a much faster way of arriving at the answer. If we square the first equation, we get

$$ \left(x+\frac{1}{x}\right)^2 = 16, $$

and the left side can be expanded to get

$$ x^2 + 2(x)\left(\frac{1}{x}\right) + \frac{1}{x^2} = x^2 + \frac{1}{x^2} + 2 = 16. $$

Subtracting $2$ from both sides gives us our final answer of $\boxed{14}$.

Let's try another problem!

**Problem**: If $p$ and $q$ are the solutions to the equation $x^2-3x-5=0$, find $p^2 + q^2$.

**Solution**: From Vieta's Formulas, we know that

$$ p+q = 3 \qquad \text{and} \qquad pq = -5.$$

Squaring the first equation yields

$$ (p+q)^2 = p^2 + 2pq + q^2 = 9. $$

But we know $pq = -5$, so we can just plug that in:

$$ p^2 + 2(-5) + q^2 = 9. $$

From here, we can just add $10$ to both sides to get our answer of $\boxed{19}$.

## Exercise: [2021 Spring AMC 10B/15](https://artofproblemsolving.com/wiki/index.php/2021_AMC_10B_Problems/Problem_15)

The given expression doesn't look too nice, but we notice that the exponents of $x$ are $11,7,3$. $11$ is $4$ above $7$, and $3$ is $4$ below $7$, so we can make this symmetrical by factoring out $x^7$:

$$ x^{11} - 7x^7 + x^3 = x^7\left(x^4 - 7 + \frac{1}{x^4}\right). $$

The $x^7$ term looks like it's going to be something ugly, so let's evaluate the stuff inside the parentheses first. Using the same approach as before, we can figure out that

$$ \left(x+\frac{1}{x}\right)^2 = 5 \implies x^2 + \frac{1}{x^2} = 3. $$

We can do the exact same thing again to find $x^4 + \frac{1}{x^4}$:

$$ \left(x^2+\frac{1}{x^2}\right)^2 = 9 \implies x^4 + \frac{1}{x^4} = 7. $$

So the stuff in the parentheses is equal to $0$. That means we don't even have to worry about the $x^7$ term (anything multiplied by $0$ is $0$), so the answer is $\boxed{0}$.

## Problems

* [2020 AMC 10A/14](https://artofproblemsolving.com/wiki/index.php/2020_AMC_10A_Problems/Problem_14) (hint: solve for $x^2+y^2$ and $x^3+y^3$, then from there you can get $x^5+y^5$)
* [2019 AIME I/8](https://artofproblemsolving.com/wiki/index.php/2019_AIME_I_Problems/Problem_8) (hint: let $a = \sin^2 x$ and $b = \cos^2 x$. you also don't know what $ab$ is, so you can set that equal to $c$ to start out. from the given information you can solve for $c$: try to find $\sin^{10} x + \cos^{10} x$ in terms of $c$)

That's all for this lecture! If you have any questions, feel free to DM me on Discord (ew_combinatorics#0746).
