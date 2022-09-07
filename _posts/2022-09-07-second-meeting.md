---
layout: post
title:  "A Recap of the 9/2 General Meeting"
author: anthony
---

On September 2, 2022, I (Anthony) delivered a lecture on the basics of number theory. I also touched on modular arithmetic and went over an AIME problem. This blog post serves as a recap of that lecture.

# Basics of Number Theory

## Prime factorization

Each number has a prime factorization, which is made of a product of powers of primes. For example, the number $60$ has prime factorization

$$ 2^23^15^17^011^013^0\dots $$

Note that any prime not in the prime factorization can be thought to have an exponent of $0$, since any number to the power of $0$ is $1$.

## Factorials!

Here's a classic problem: what's the exponent of $5$ in the prime factorization of $13!$? (For those of you who don't know what the exclamation point means, $n! = n\cdot n-1\cdot n-2\cdot\dots\cdot2\cdot1$. For example, $13! = 13\cdot12\cdot11\dots\cdot2\cdot1.$)

Well, if we look at $13\cdot12\cdot11\dots\cdot2\cdot1$, we realize that only two numbers in there can contribute to the exponent of the $5$: $10$ and $5$. None of the other numbers contribute any $5$s to the prime factorization, so we can ignore them. Each of $10$ and $5$ contributes one factor of $5$ to the prime factorization, so the answer to this problem is $\boxed{2}$.

Next problem: what's the exponent of $5$ in the prime factorization of $26!$?

You might say that $5$ numbers contribute to the exponent of $5$ in the prime factorization: $25, 20, 15, 10, 5$. This is correct, but we forgot to consider that $25$ actually contributes two $5$s, since $25=5\cdot5.$ This means the answer to this problem is $\boxed{6}$.

In general, the exponent of some prime $p$ in the prime factorization of $n!$ is

$$ \left\lfloor\frac{n}{p}\right\rfloor + \left\lfloor\frac{n}{p^2}\right\rfloor + \left\lfloor\frac{n}{p^3}\right\rfloor + \dots $$

where the brackets indicate floor division (dividing and throwing away the remainder). More information [here](https://artofproblemsolving.com/wiki/index.php/Legendre%27s_Formula).

Another similar problem is: how many zeroes does $26!$ end in?

Well, the number of zeroes that a number ends in is the same as the largest power of $10$ that divides it. And the largest power of $10$ that divides it is dependent only on the exponents of $2$ and $5$ in the prime factorization.

As we determined before, the exponent of $5$ in the prime factorization of $26!$ is $6$. The exponent of $2$ in that factorization is $23$.

To make a $10$, we need one $2$ and one $5$. So with $6$ $5$s and $23$ $2$s, we can make $6$ $10$s, so $26!$ ends in $\boxed{6}$ zeroes. (The extra $2$s aren't relevant.)

## A MATHCOUNTS problem

This problem is from the 2020 MATHCOUNTS Chapter competition. It was Sprint Round Problem 29.

*Consider the number $9!$ in base $9$.*

*a. How many zeroes does it end in?*

*b. What's the last nonzero digit?*

One way to do this problem would be to calculate $9!$, convert it to base $9$, and find the answers from there. This is a viable strategy (cough cough warith), but let's do this problem using the principles we've just learned. (Also, hopefully you know what bases are. If you don't: [look here](https://artofproblemsolving.com/wiki/index.php/Base_numbers))

Part (a) is just asking for the exponent of $9$ in $9!$. We can't use the formula from before because $9$ isn't a prime. However, we can use the formula with the number $3$, because $3$ is prime and a $9$ is just made of two $3$s. 

We get that the exponent of $3$ in the prime factorization of $9!$ is $4$. Each pair of $3$s makes a $9$, so two $9$s can be made and the answer is $\boxed{2}$. (Note that if there were five $3$s instead of four, the answer would still be the same.)

I tried to explain part (b) during the lecture, but the explanation was kind of bad and relied on number theory concepts that I hadn't covered at that point. So, it's been left as an exercise to the reader. (The answer is 7, if you want to check afterwards)

# Modular arithmetic

Modular arithmetic is a way to formalize a lot of number theory into a rigid framework (particularly with stuff dealing with remainders). 

I didn't explain this during the lecture (which was very stupid of me), but I'll offer an analogy to modular arithmetic now that might help people get the idea.

Consider a clock where the 12 at the top is replaced with a 0. Imagine what happens as time passes. The hour hand is pointed to 10; one hour later, it's pointed to 11. But the next hour, it "loops back" to 0, instead of going to 12 (which isn't even on the clock).

You might realize that $10$ hours after midnight, it's 10 o'clock. But $10+12=22$ hours after midnight is also 10 o'clock. $22+12=34$ hours after midnight is *also* 10 o'clock.

Since the times repeat every $12$ hours, we call this system *mod 12*. In this system, $10, 22$, and $34$ are all the same thing. We use the following notation to denote this:

$$ 10 \equiv 22 \equiv 34 \pmod {12} $$

The triple line is referred to as *congruence*.

From this, you can probably see why the following fact is true: *If two numbers are congruent mod $n$, then their difference is divisible by $n$.*

Another fact: *If $b$ is the remainder when $a$ is divided by $n$, then $a \equiv b \pmod n$.*

These two approaches to looking at modular arithmetic can solve many problems.

## Some operations you can do

Many operations in modular arithmetic work the same as they do in regular arithmetic. For example, you can still add, subtract, and multiply on both sides of equations:

$$ a \equiv b \pmod n \implies a + k \equiv b + k \pmod n $$
$$ a \equiv b \pmod n \implies a - k \equiv b - k \pmod n $$
$$ a \equiv b \pmod n \implies ak \equiv bk \pmod n $$

**VERY IMPORTANT NOTE: THIS DOES NOT APPLY TO DIVISION. DIVISION IS WEIRD IN MODULAR ARITHMETIC.**

You can also add, subtract, and multiply different equations: (only multiplication is shown, for concision)

$$ a \equiv b \pmod n \qquad \text{and} \qquad c \equiv d \pmod n \implies ac \equiv bd \pmod n $$

This is extremely useful as it allows us to "mod out" before doing calculations. For example, if I was asked to calculate the remainder when $131\cdot 292$ was divided by $9$, I wouldn't have to multiply it out then calculate the remainder. I could "mod out" by $9$ first by calculating the remainder when $131$ is divided by $9$, then doing the same to $292$, then multiplying those two remainders together to get the answer. (Well, not exactly, but the resulting number is easy to get a remainder out of.)

More information on this can be found [here](https://artofproblemsolving.com/wiki/index.php/Modular_arithmetic/Introduction).

## Proving remainder rules

Let's prove the remainder rule for $9$. If you've done Number Sense, you might remember that the remainder of a number when divided by $9$ is the same as the remainder of the sum of its digits. Let's prove that.

Consider a number like $5432$. This can be written as

$$ 5\cdot10^3 + 4\cdot10^2 + 3\cdot10^1 + 2\cdot10^0. $$

Taking everything mod $9$, we get that

$$ 5\cdot10^3 + 4\cdot10^2 + 3\cdot10^1 + 2\cdot10^0 \equiv 5\cdot1^3 + 4\cdot1^2 + 3\cdot1^1 + 2\cdot1^0 \pmod 9. $$

(Keep in mind that exponentiation is just repeated multiplication. This is why I'm able to "mod out" of the bases. Modding out of the exponents is not allowed.)

But $1$ to the power of anything is $1$, and multiplying by $1$ doesn't do anything! So indeed, any number is congruent to the sum of its digits mod $9$.

The proof for the remainder rule for $11$ is left as an exercise to the reader. (If you do this problem, remember that negative numbers are fair game in modular arithmetic!)

## [2020 AIME II/10](https://artofproblemsolving.com/wiki/index.php/2020_AIME_II_Problems/Problem_10)

This is a tricky problem which I got wrong in contest, but I still think it's cool because it demands nothing more than an understanding of modular arithmetic. The problem statement is in the link above.

If you've done Number Sense before, you might recall that

$$ 1^3+2^3+3^3+\cdots+n^3 = \frac{n^2(n+1)^2}{4}. $$

So basically, the problem can be reduced to this: Find all $n$ such that

$$ \frac{n^2(n+1)^2}{4} \equiv 17 \pmod {n+5} $$

A key thing to note here is that $n \equiv -5 \pmod {n+5}$. (Can you see why this is true?) Similarly, $n+1 \equiv -4 \pmod {n+5}$.

### Wrong Approach 1

Because of the congruences listed above, we can just substitute the corresponding values in:

$$ \frac{(-5)^2(-4)^2}{4} \equiv 17 \pmod {n+5} $$
$$ \frac{400}{4} \equiv 17 \pmod {n+5} $$
$$ 100 \equiv 17 \pmod {n+5} $$
$$ 83 \equiv 0 \pmod {n+5} $$

So the remainder when $83$ is divided by $n+5$ is $0$. This means $n+5$ is a factor of $83$. The possible values of $n+5$ are $1$ and $83$, but only $83$ yields a positive value of $n$. That positive value is $\boxed{78}$.

Why is this approach wrong? Well, we can't jump from that second equation to the third equation, because division isn't well-defined in modular arithmetic. Let's try something different:

### Wrong Approach 2

$$ \frac{400}{4} \equiv 17 \pmod {n+5} $$

Instead of simplifying the left side, which isn't allowed, we can multiply by $4$.

$$ 400 \equiv 68 \pmod {n+5} $$
$$ 332 \equiv 0 \pmod {n+5} $$

Possible values of $n+5$ are $1,83,166,$ and $332.$ This yields $\boxed{78,161,327}$ as solutions.

The reason why this is wrong is more subtle than the previous. Remember in Algebra 2 (or 1, I forgot) when you had extraneous solutions to some problems involving square roots and you had to plug things back in to weed them out? The same situation happened here. When we multiplied by $4$, our steps were not reversible (you can't just divide to reverse your steps, because division isn't well-defined!). So we'll have to check each of these numbers individually.

### Final Checking + the correct answer

Let's check if $78$ actually works. $1^3+2^3+3^3+\cdots+78^3$ is equal to

$$ \frac{78\cdot78\cdot79\cdot79}{4} = 39\cdot39\cdot79\cdot79. $$

(I'm able to divide here without consequences because we haven't entered the realm of modular arithmetic yet, so division is still allowed.)

Now we can do our modding out:

$$ 39\cdot39\cdot79\cdot79 \equiv 39\cdot39\cdot-4\cdot-4 \pmod {83}. $$

After some multiplication, we get:

$$ (-156)^2 \equiv 10^2 \equiv 17 \pmod {83}, $$

so $78$ does actually yield a remainder of $17$.

The computation for the other two numbers is extremely boring, so I will skip it. In the end, the numbers that work are $\boxed{78, 161}$. (The actual answer on the AIME would be $78+161=239.$)

This was the end of the lecture! Please don't hesitate to DM me on Discord (ew_combinatorics#0746) if you have questions.

*also i might have accidentally included a bit too much information in the lecture, as you can see from the length of the blog. oops*
