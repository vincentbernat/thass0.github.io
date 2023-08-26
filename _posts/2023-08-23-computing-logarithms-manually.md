---
layout: post
title: Learning some more logarithms
---

<div class="message">
This post was originally inspired by <a href="https://two-wrongs.com/learning-some-logarithms.html">learning some logarithms</a> by kqr. Just like his post it's about excitement and discovery, and I hope to present some of the knowledge I've gathered in an approachable way. Some parts get quite math-heavy, but they are not meant to be a formally rigid study of the topics at hand. Rather their purpose is to be practical and insightful.
</div>

I have become fascinated by the ability to calculate logarithmic functions in one's head. To me, logarithms have always felt like a black box that couldn't be conquered. They are a fundamental building block of mathematics, yet every time I saw a logarithmic equation, I was tempted to grab my calculator or to look up how to solve the example at hand. Over the past half year, I've spent some time improving my understanding of logarithms and learning how to compute the results of logarithmic equations by hand. Here is what I've found!

# Why learn this?

To me, the ability of computing logarithms in one's head or at least purely by hand on paper would be greatly desirable. The number of new concepts we can hold in [working memory](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two) at any point in time is limited, so it makes sense to internalize as many conceptual building blocks as possible. This will allow you to reduce the amount of time spent on thought that's not problem-centric. For example, you'll be much more comfortable dealing with complex logarithmic equations etc. if you have a good intuition for basic logarithms themselves.

On another note, I think there is a lot to say in favor of the aesthetic beauty of performing complex calculations without any tools except for systematic analytic thought.

First of all, why is it that we don't all find logarithms to be intuitive? To answer this question, it was helpful to me to think of mathematical operations in terms of the *function* they compute and that function's *inverse* [^3]. For example, the addition $y = x + a$ yields the value $y$ from $x$ and $a$ and the inverse of the addition results in one of the arguments: $y - a = x$. You can find a table of different examples of this for numerous functions and the restrictions that apply [here on Wikipedia](https://en.wikipedia.org/wiki/Inverse_function#Standard_inverse_functions). You will notice, that at any level of complexity the inverse function is generally more difficult to compute in your head or by hand than the original. The inverse as a stand-alone function is usually a more abstract operation than it's counterpart that's even harder to grasp as the complexity of the base operation increases. What I mean by this is that a subtraction is harder to calculate on your own than an addition and a multiplication is harder than both addition and subtraction [^1].

For me the limit of what I could realistically compute or approximate in my head was square roots. This was likely due to the fact that in German high-school they make us memorize the square and thereby also square root of all numbers between 0 and 20. This was the starting point for teaching us about parabolas and later polynomials.

I can't recall whether or not I felt bored during those introductory classes but I am certain many people disliked endlessly performing simple calculations applying the same operation over and over again. Nonetheless, it seems to me that while it's a somewhat boring method, memorizing a bunch of common values and then drilling their relationships is useful in building a base from which to construct a deeper understanding and improved intuition. It's also essential to have memorized a few example values if you want to approximate the values of complex functions in a timely manner without using a computer.

The same approach was used before that for addition, subtraction, multiplication and division. The general idea was introduced and then it was  drilled for a while to get a feel for it. This is definitely not the ultimate learning strategy and better methods of internalizing concepts are used everywhere outside of public schools [^2], but it highlights the importance of getting to a place where one doesn't need to think about the basic operations anymore. They are just there in your head, right at your disposal. The goal is to **minimize the amount of time spent on thought that's not central to the problem at hand**.

For example, what's the square root of $17$? Not knowing how to algorithmically compute the best approximation of $\sqrt{17}$, we can make a pretty good *intuitive* guess by relying on our knowledge of square roots. We memorized that $\sqrt{16} = 4$, that the square of the next integer after $4$ is $5^2 = 25$ and that the function $f(x) = x^2$ is continuous. Based on this knowledge we're instantly able to say that $\sqrt{17}$ must be somewhere in the lower part of the interval $[4, 5]$. This gets us most of the way there but let's continue. To improve our guess without doing any time-consuming trying-out, we can approximate $f(x)$ for $4 \leq x \leq 5$ as a linear function. Based on this, we can conclude that since $25 - 16 = 9$ and $\sqrt{25} - \sqrt{16} = 5 - 4 = 1$, $\sqrt{17} = \sqrt{16 + 1} \approx 4 + \frac{1}{9}$. All of these calculations can be easily performed in one's head or quickly be scribbled down on a piece of paper. The figure below illustrates what I have just explained. Again, note this doesn't involve any calculates that are difficult to perform manually.

![Figure 1: approximating square roots]({{ '/public/figures/example-approximate-square-root.png' | absolute_path }})

I hope that you see why this is so exciting! By pure memorization of a few example values and by internalizing the relationships of the operations we need by drilling them, it's possible to make very fast guesses about otherwise complex computations. To prove my point, let's find out how close we got. $4 + \frac{1}{9} \approx 4.111$ and $\sqrt{17} \approx 4.123$: our guess was off by only $0.012$. Imagine if you could approximate something like $log_{10}(64)$ just as quickly!


# Powers, roots and logarithms

There is [some confusion](https://math.stackexchange.com/questions/3693149/isnt-square-root-a-bit-like-log) as to what the relationship between powers, roots and logarithms is. The operations we use more often than exponentiation, that is addition and multiplication are both commutative. This means that $a + b = b + a$ and $a \cdot b = b \cdot a$: we can exchange the sequence of the operands freely. That is not the case for powers. Generally, $a^b$ doesn't necessary have to be the same as  $b^a$. In fact there are only [two distinct numbers n and m](https://keith-mcnulty.medium.com/only-one-pair-of-distinct-integers-satisfy-this-equation-76ea45469a96) that fulfill the requirement that $n^m = m^n$ which are $2^4 = 4^2 = 16$.

The fact that [exponentiation is not commutative](https://en.wikipedia.org/wiki/Commutative_property#Division,_subtraction,_and_exponentiation) leads to it having two inverse operations: the nth-root and the logarithm. This may seem surprising since we're so used to commutative operations like addition and multiplication that have only a single inverse operation.

If way say that $x = b^n$, then the nth-root is defined as $b = \sqrt[n]{x}$. A sentence that describes what's happening here declaratively might so as follows: "the nth-root of a number x yields the base b, such that b to the power of n is equal to x". This can also be phrased as a question were the result value of the nth-root is seen as the answer to that question: "what's be base b such that b to the power of n is equal to x?".

Given the two variables of the exponentiation $x$ and $n$, the roots yields the third one $b$. Accordingly, the logarithm, which is just the other inverse function for powers, yields the other parameter $n$ from $x$ and $b$: $log_b(x) = n$. The fitting questing would be: "what's the exponent n of b such that b to the power of n is equal to x?". As you can see, the question describing the operation has exactly the same structure with a different sequence. The part that's hard to think here is the "such that" part of the question. We basically have to think in reverse to answer the it. That's the difficulty of inverse functions.

I'd also like to share a figure that helped me improve my understanding of the relationship between the three functions.

![Relationship between powers, roots and logarithms]({{ '/public/figures/relationship-power-root-logarithm.png' | absolute_path}})

It stems from a German mathematics textbook from 1997 called Handbuch Mathematik [^5] which translates to <i>Handbook Mathematics</i>. The caption reads <i>Relationship between power, root and logarithm or between value of power, base and exponent</i>. I added the context about this figure's origin to make this part more memorable because this triangular relationship is key. [This answer](https://math.stackexchange.com/a/165225) on Stack Exchange builds on the same idea to suggest an alternative notation for powers, roots and logarithms that emphasizes this relationship.

# Definition of logarithms

Say we have an exponentiation $y = b^x$ where $y$, $b$ and $x$ are real numbers with the additional constraint that $b$ must be positive. If the values of $y$ and $b$ are known, the logarithm of $y$ to the base $b$ gives us the missing value $x$. It is written as $x = log_b(y)$. The following identities can be derived from this definition[^6]:

$$\text{(1)} ~~~ x = b^{log_b(x)} ~~~~~~ \text{(2)} ~~~ x = log_b({b^x})\text{.}$$

Both of these are very important. Ideally, you'd want them to come to mind every time you're looking to solve a logarithmic equation. While they represent the basic relationships of logarithms, their *reverseness* makes them difficult to think about already.

Let's start by digesting $x = b^{log_b(x)}$. To break up the equation, we'll name the logarithm in the exponent $a = log_b(x)$. This means that, $a$ is the exponent to the base $b$ such that $b^a = x$. With this step of indirection, it's easy to see why the equation must be true. It can be described a bit like this: "Raise $b$ to the power $a$ of $b$ that fulfills the property that $b^a = x$.".

The second equation $x = log_b(b^x)$ is even easier to understand. I like to ask myself the question: "What's the exponent $x$ to the base $b$, such that $b^x = b^x$? It's $x$!".

Based on this we are also able to induce the values of a few logarithmic expressions. For example what is the value of $log_a(a)$?
based on the laws of exponents, we can rewrite this as $log_a(a^1)$ or as $log_a(a^x)$ where $x = 1$. Now, it's obvious from the second identity that the answer is 1. The same approach works for $log_a(1)$. Rewriting this the same way by substituting $a^0$ for $1$ gives us $log_a(a^0) = 0$.

## Multiplication as addition

The following is another central identity which opens up a lot of possibilities for us when it comes to computing logarithms manually.

$$log_b(x \cdot y) = log_b(x) + log_b(y) ~~~~ \text{if}  ~ x > 0 \text{,} ~ y > 0$$

It's proof can be constructed from the two identities above and the rules of exponents. We start by using the first identity $x = b^{log_b(b)}$ from above to substitute $x$ and $y$ in the left side of the equation:

$$log_b(x \cdot y) = log_b(b^{log_b(x)} \cdot b^{log_b(y)})\text{.}$$

Using the rule of exponents which states that $x^a \cdot x^b = x^{a + b}$, we can simplify this into

$$log_b(b^{log_b(x)} \cdot b^{log_b(y)}) = log_b(b^{log_b(x) + log_b(y)}) \text{.}$$

Lastly the second identity $x = log_b({b^x})$ is applied.

$$log_b(b^{log_b(x) + log_b(y)}) = log_b(x) + log_b(y)$$

This equation was introduced in 1614 by John Napier and is famous because it allowed [reducing complex multiplications to simple additions](https://en.wikipedia.org/wiki/Mathematical_table#Tables_of_logarithms). Instead of performing the multiplication itself, people could simply look-up the values of $log_b(x)$ and $log_b(y)$ and then add them together. This is one of the techniques we'll be using later to solve logarithmic equations manually. Instead of looking up the values in a logarithm table, we'll memorize a few key ones.

## Division as subtraction

The laws of exponents also state that $x^a / x^b = x^{a - b}$. Hence, the equation above works for division, too:

$$log_b(x / y) = log_b(x) - log_b(y) ~~~~ \text{if} ~ x > 0 \text{,} ~ y > 0 \text{.}$$

## Exponentiation as multiplication

Based on the law of exponents which states that $(x^a)^b = x^{a \cdot b}$, we get this mind-boggling equation:

$$log_b(x^c) = c \cdot log_b(x) ~~~~ \text{if} ~ x > 0 \text{.}$$

This can be proven by initially defining an auxiliary variable $y = log_b(x)$, so that $b^y = x$. By substituting $b^y$ for $x$, we get $$log_b((b^y)^c)$$. Next, we apply the law of exponents:

$$log_b((b^y)^c) = log_b(b^{y \cdot c})\text{.}$$

Lastly, we again apply the second identity from the definition and the substitute the original definition of $y$:

$$log_b(b^{y \cdot c}) = y \cdot c = c \cdot log_b(x)\text{.}$$
nnn
## Change of basis

This is the last concept we need to get started calculating logarithms by hand. The ability to change a logarithmic expression's base I very valuable to us, because it means that we only need to memorize a set small of values with a single base. We're then able to convert between bases and
thereby solve expressions in a plethora of bases.

$$log_b(x) = \frac{log_a(x)}{log_a(b)} ~~~~ \text{if} ~ x > 0\text{,} ~ a > 0$$

Again, we'll start the proof by defining our variable $y = log_b(x)$ based on the first identity. It's important to recall that this is purely used to simplify subsequent equations and make them easy to grasp. With $y$ defined like this, we can perform the following transformations:

$$
\begin{align*}
  b^{log_b(x)} &= x & & | ~ y = log_b(x)\\
  b^y          &= x           &  & | ~ log_a\\
  log_a(b^y)   &= log_a(x)
\end{align*}
$$

We can further transform the left side of this equation using the *'exponentiation as multiplication'* identity.

$$
\begin{align*}
  log_a(b^y) = y \cdot log_a(b)   &= log_a(x)    &  & | ~ \div log_a(b)\\
  y &= \frac{log_a(x)}{log_a(b)}\\
  log_b(x) &= \frac{log_a(x)}{log_a(b)}
\end{align*}
$$

# Memorize a logarithm table

As mentioned above, logarithms were a huge breakthrough when they were first discovered, because they allowed to make complicated calculates relatively simple. In a time without machine computers  this was very valuable. The values of many different logarithmic expressions were calculated only once and then collected into so-called logarithm tables. After transforming the given calculation, you could look up the closest value in the table and you'd have a pretty good estimate.

<a title="agr, CC BY-SA 3.0 &lt;http://creativecommons.org/licenses/by-sa/3.0/&gt;, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:Abramowitz%26Stegun.page97.agr.jpg"><img width="1024" alt="Abramowitz&amp;Stegun.page97.agr" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Abramowitz%26Stegun.page97.agr.jpg/1024px-Abramowitz%26Stegun.page97.agr.jpg"></a>

It's not actually that long ago that so called mathematical tables like this existed. Computing logarithms is not difficult for a calculator but there are common operation that are. For example, this is a table of binomial coefficients $\binom{n}{k}$ from a stochastic textbook from 2007.

![Table of binomial coefficients of different values in a modern textbook]({{ 'public/figures/binomial_coefficients_table.png' | absolute_url }})

We are going to reduce the set of values to memorize to the bare minimum.

[Memorize table with $log_{10}(e)$ and $log_{10}(2)$]

---

# Maybe

- Example solving a min. $n$ for min. $P(X \geq k)$ given a $p$ task manually. Could be part of a number of case studies.

- Connection to roots: $x^{1/n}$.

---

[^1]: This is about how difficult the calculation feels and how long it takes to carry out, not about how hard it would theoretically be, given you knew all possible algorithms, tricks and exceptions.

[^2]: For example, if you want to remember something long term, [spaced repetition](https://ncase.me/remember/) is a [much better strategy](https://gwern.net/spaced-repetition) than drilling it very intensely for a relatively short amount of time. This seems to be a common problem (or misconception) about project based learning, too. Without repetition, it's easy to forget concepts that were used only once during a single project. It also applies to learning for exams and is likely a key factor in why students don't feel motivated to  learn purely for an exam. I've found that the experience of learning during either a project or for an exam can be made much more rewarding by putting in a small amount of extra work in repeating the content a few times so that you can recall it long-term.

[^3]: https://www.sciencedirect.com/topics/mathematics/inverse-operation is a starting point. Just like Knuth, it has a lot of interesting stuff to say about logarithms.

[^5]: Scholl, W., & Drews, R. (1997). <cite>Handbuch Mathematik</cite>. Falken.

[^6]: Knuth, E. (1997). <cite>The art of computer programming: Fundamental algorithms</cite> (3rd ed., Vol. 1). Addison Wesley Longman Publishing Co., Inc.

<!--  LocalWords:  frac
 -->
