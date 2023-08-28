---
layout: post
title: Learning some more logarithms
---

<div class="message">
This post was originally inspired by <a href="https://two-wrongs.com/learning-some-logarithms.html">learning some logarithms</a> by kqr. Just like his post it's about the excitement of discovery, and I hope to present some of the knowledge that I have gathered in an approachable way. Some parts are quite math-heavy, but they are not meant to be a formally rigid study of the topics at hand. Rather their purpose is to be insightful and practical.
</div>

I have become fascinated by the ability to calculate logarithmic functions in one's head. To me, logarithms have always felt like a black box that couldn't be conquered. They are a fundamental building block of mathematics, yet every time I saw a logarithmic equation, I was quick to grab my calculator instead of solving the equation by hand. Over the last half year, I have spent some time improving my understanding of logarithms and learning how to compute the results of logarithmic equations by hand. Here is how I did it.

# Why learn this?

To me, the ability of computing logarithms purely by hand on paper is greatly desirable. The number of new concepts we can hold in [working memory](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two) at any point in time is limited, so it makes sense to internalize as many conceptual building blocks as possible. With a good intuition for logarithmic expressions, you'll be infinitely more comfortable dealing with equations involving logarithms and you'll be able to deal with a level of complexity that would have been unthinkable to you before. Also they are going to be less daunting or distracting to you when they appear in some other context.

On another note, I think there is a lot to say in favor of the aesthetic beauty of performing computationally complex operations without any tools except for systematic analytic thought.

Firstly, why is it that we don't all find logarithms to be intuitive? To answer this question, it was helpful to me to think of mathematical operations in terms of the *function* they compute and that function's *inverse* [^3]. For example, the addition $y = x + a$ yields the value $y$ from $x$ and $a$ and the inverse of the addition results in one of the arguments: $y - a = x$. You can find a table of different examples of this for numerous functions and the restrictions that apply [here on Wikipedia](https://en.wikipedia.org/wiki/Inverse_function#Standard_inverse_functions). You will notice, that at any level of complexity the inverse function is generally more difficult to compute in your head or by hand than the original. The inverse as a stand-alone function is usually a more abstract operation than it's counterpart that's even harder to grasp as the complexity of the base operation increases. For example, a subtraction is often harder to compute manually than an addition and a multiplication is usually harder than both addition and subtraction [^1].

For a long time, the limit of what I could realistically compute or better approximate in my head was square roots. This was likely due to the fact that in German high-school they make us memorize the square and thereby also the square root of all numbers between 0 and 20. Later, this became the starting point for teaching us about parabolas and later polynomials.

I can't recall whether I felt bored during those introductory classes, but I am certain many people disliked endlessly performing simple calculations applying the same operation over and over again. The method is somewhat boring, but it seems to me that memorizing a number of common function values and then drilling their relationships is useful in building a base from which to construct a deeper understanding and improved intuition. It's also essential to have memorized a few examples if you want to approximate the values of complex functions in a timely manner without using a calculator.

Earlier on, they used the same approach for addition, subtraction, multiplication, and division. The general idea was introduced first, and then it was drilled for a while to get a feel for it. This is definitely not the ultimate learning strategy, and better methods of internalizing concepts are used everywhere outside public schools [^2]. But it highlights the importance of getting to a place where one doesn't need to think about the basic operations anymore. They are just there in your head, right at your disposal.

For example, what's the square root of $17$? Not knowing how to algorithmically compute the best approximation of $\sqrt{17}$, we can make a pretty good *intuitive* guess by relying on our knowledge of square roots. We memorized that $\sqrt{16} = 4$, that the square of the next integer after $4$ is $5^2 = 25$ and that the function $f(x) = x^2$ is continuous. Based on this knowledge, we can quickly say that $\sqrt{17}$ must be somewhere in the lower part of the interval $[4, 5]$.

This gets us pretty far, but let's continue. To improve our guess without spending any time on (generally) random guesses, we can approximate $f(x)$ for $4 \leq x \leq 5$ as a linear function. Based on this, we can conclude that since $25 - 16 = 9$ and $\sqrt{25} - \sqrt{16} = 5 - 4 = 1$, $\sqrt{17} = \sqrt{16 + 1} \approx 4 + \frac{1}{9}$. All of these calculations can be easily performed in one's head or quickly be scribbled down on a piece of paper. The figure below illustrates what I have just explained. Again, note this doesn't involve any calculates that are difficult to perform manually.

![Figure 1: approximating square roots]({{ '/public/figures/example-approximate-square-root.png' | absolute_path }})

I hope that you see why this is so exciting! By pure memorization of a few example values and by internalizing the relationships of the operations we need by drilling them, it's possible to make very fast guesses about otherwise complex computations. To prove my point, let's find out how close we got. $4 + \frac{1}{9} \approx 4.111$ and $\sqrt{17} = 4.123$: our guess was off by only $0.012$. Imagine if you could approximate something like $log_{10}(64)$ just as quickly!


# Powers, roots and logarithms

There is [some confusion](https://math.stackexchange.com/questions/3693149/isnt-square-root-a-bit-like-log) as to what the relationship between powers, roots and logarithms is. Some common operations such as addition and multiplication are commutative, unlike exponentiation, which is not. Commutativity means that $a + b = b + a$ and $a \cdot b = b \cdot a$: we can exchange the sequence of the operands freely. That is not the case for powers. Generally, $a^b$ isn't the same as $b^a$ [^9]. We can show that exponentiation cannot be commutative by choosing an example that doesn't fulfill this property: $3^4 = 81 \neq 4^3 = 64$.

[TODO: Improve the following three paragraphs.]

The fact that [exponentiation is not commutative](https://en.wikipedia.org/wiki/Commutative_property#Division,_subtraction,_and_exponentiation) makes it possible to define: the nth-root and the logarithm. This may seem surprising since we're so used to commutative operations like addition and multiplication that have only a single inverse operation.

If way say that $x = b^n$, then the nth-root is defined as $b = \sqrt[n]{x}$. A sentence that describes what's happening here declaratively might go as follows: "the nth-root of a number x is the base b, such that b to the power of n is equal to x". This can also be phrased as a question were the result value of the nth-root is seen as the answer to that question: "what's be base b such that b to the power of n is equal to x?".

Given the two variables of the exponentiation $x$ and $n$, the roots yields the third one $b$. Accordingly, the logarithm, which is just the other inverse function for powers, yields the other parameter $n$ from $x$ and $b$: $log_b(x) = n$. The fitting questing would be: "what's the exponent n of b such that b to the power of n is equal to x?". As you can see, the question describing the operation has exactly the same structure with a different sequence. The part that's hard to think here is the "such that" part of the question. We basically have to think in reverse to answer the it. That's the difficulty of inverse functions.

I'd also like to share a figure that helped me improve my understanding of the relationship between the three functions.

![Relationship between powers, roots and logarithms]({{ '/public/figures/relationship-power-root-logarithm.png' | absolute_path}})

It stems from a German mathematics textbook from 1997 called Handbuch Mathematik [^5] which translates to <i>Handbook Mathematics</i>. The caption reads: "<i>Relationship between power, root and logarithm or between value of power, base and exponent</i>". This figure illustrates the *triangular relationship* between the three functions, which is key. The same idea is used in [this answer on Stack Exchange](https://math.stackexchange.com/a/165225) to suggest an alternative notation for powers, roots, and logarithms that emphasizes this relationship.

# Definition of logarithms

Say we have an exponentiation $x = b^y$ where $y$, $b$ and $x$ are real numbers with the additional constraint that $b$ must be positive and $b \neq 1$. Then, the logarithm of $x$ to the base $b$ [is defined as](https://www.alamo.edu/contentassets/3c031ab72f3d4dbda979bc9e66d11634/exponential/math1414-logarithmetic-functions.pdf "Definition of the logarithmic function as given by Crystal Hull")

$$log_b(x) = y ~~ \Leftrightarrow ~~ b^y = x\text{.}$$

In the exponentiation $x = b^y$, if we know $x$ and  $b$, the logarithm of $x$ to the base $b$ gives us the missing exponent. From this definition we get the following identities [^6]:

$$\text{(1)} ~~~ x = b^{log_b(x)} ~~~~~~ \text{(2)} ~~~ x = log_b({b^x})\text{.}$$

Both of these are crucial. Ideally, you'd want them to come to mind every time you're looking to solve a logarithmic equation. While they represent fundamental relationships of the logarithmic and exponential form, their *reverseness* makes them difficult to think about.

Let's start by digesting $x = b^{log_b(x)}$. To break up the equation, we'll name the logarithm in the exponent $a = log_b(x)$. This means that, $a$ is the exponent to the base $b$ such that $b^a = x$. With this step of indirection, it's easy to see why the equation must be true. Think of it like this: "Raise $b$ to the power $a$ of $b$, which fulfills the property that $b^a = x$.".

The second equation $x = log_b(b^x)$ is easier to understand. I like to ask myself the question: "What's the exponent $x$ to the base $b$, such that $b^x = b^x$? It's $x$!".

Based on this knowledge, we are also able to induce the values of a few logarithmic expressions. For example, what is the value of $log_a(a)$? Since $a = a^1$, we can rewrite this as $log_a(a^1)$ or equally $log_a(a^x)$ with $x = 1$. Now, it's obvious from the second identity that the answer is 1. The same approach of relying on the laws of exponents works for $log_a(1)$. Rewriting this the same way by substituting $a^0$ for $1$ gives us $log_a(a^0) = 0$.

[TODO: Continue improving language here.]

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

As mentioned above, logarithms were a huge breakthrough when they were first discovered, because they made complicated calculates relatively simple. In a time without machine computers, this was very valuable. The values of many different logarithmic expressions were calculated only once and then collected into so-called logarithm tables. After transforming the a calculation, you could look up the closest value in the table and you'd have a pretty good estimate.

<a title="agr, CC BY-SA 3.0 &lt;http://creativecommons.org/licenses/by-sa/3.0/&gt;, via Wikimedia Commons" href="https://commons.wikimedia.org/wiki/File:Abramowitz%26Stegun.page97.agr.jpg"><img width="1024" alt="Abramowitz&amp;Stegun.page97.agr" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Abramowitz%26Stegun.page97.agr.jpg/1024px-Abramowitz%26Stegun.page97.agr.jpg"></a>

It's not actually that long ago that so called mathematical tables like this existed. Computing logarithms is not difficult for a calculator but there are common operation that are. For example, this is a table of binomial coefficients $\binom{n}{k}$ from a stochastic textbook from 2007[^7].

![Table of binomial coefficients of different values in a modern textbook]({{ 'public/figures/binomial_coefficients_table.png' | absolute_url }})

Obviously, it would be a bit extreme to memorize so many numbers. It's not impossible and it will certainly improve the accuracy of your approximations, but it's not worth the time for most people. Therefore, we are going to reduce the set of values to memorize to the bare minimum.

We can change the base of any logarithm into a base we know if we know the value of the logarithm of the original base to the desired base. This means that we only have to memorize a range of logarithms to a single base, as well as some logarithms of other bases to that same base we've chosen. Here, I opted for base $10$ logarithms and conversions from the natural and binary logarithms since there are the most common. The range that we need to memorize is also quite restricted, because multiplications can be broken up into additions. That is, it's sufficient to know the values of $log_{10}(8)$ and $log_{10}(10)$ to compute $log_{10}(80)$ because

$$log_{10}(80) = log_{10}(10 \cdot 8) = log_{10}(10) + log_{10}(8) \text{.}$$

Depending on how hard you want to make it for yourself, you can also opt for different degrees of precision. As suggested by [kqr](https://two-wrongs.com/learning-some-logarithms.html), it's possible to get quite satisfactory results from only a single digit of precision. For completeness, I also added a higher-precision option for each value. It makes sense to memorize the higher-precision values for the logarithms that you'll just most often. This is why the base precision for $log_{10}(e)$ is slightly higher by default.


<!-- Markdown table source (good for making edits):
| logarithm      | base precision | base error | extra precision | extra precision error |
| $log_{10}(1)$  | 0              | /          | /               | /                     |
| $log_{10}(10)$ | 1              | /          | /               | /                     |
| $log_{10}(e)$  | 0.43           | 1.00 %     | 0.4343          | 0.00 %                |
| $log_{10}(2)$  | 0.30           | 0.34 %     | 0.3010          | 0.01 %                |
| $log_{10}(3)$  | 0.5            | 4.80 %     | 0.477           | 0.03 %                |
| $log_{10}(4)$  | 0.6            | 0.34 %     | 0.602           | 0.01 %                |
| $log_{10}(5)$  | 0.7            | 0.15 %     | 0.699           | 0.00 %                |
| $log_{10}(6)$  | 0.8            | 2.81 %     | 0.778           | 0.02 %                |
| $log_{10}(7)$  | 0.8            | 5.34 %     | 0.845           | 0.01 %                |
| $log_{10}(8)$  | 0.9            | 0.34 %     | 0.903           | 0.01 %                |
| $log_{10}(9)$  | 1.0            | 4.80 %     | 0.954           | 0.03 %                |
-->

<table>
  <tbody>
    <tr>
      <td>logarithm</td>
      <td>base precision</td>
      <td>base error</td>
      <td>extra precision</td>
      <td>extra precision error</td>
    </tr>
    <tr>
      <td>$log_{10}(1)$</td>
      <td class="good">0</td>
      <td>/</td>
      <td>/</td>
      <td>/</td>
    </tr>
    <tr>
      <td>$log_{10}(10)$</td>
      <td class="good">1</td>
      <td>/</td>
      <td>/</td>
      <td>/</td>
    </tr>
    <tr>
      <td>$log_{10}(e)$</td>
      <td>0.43</td>
      <td>1.00 %</td>
      <td class="good">0.4343</td>
      <td>0.00 %</td>
    </tr>
    <tr>
      <td>$log_{10}(2)$</td>
      <td>0.30</td>
      <td class="good">0.34 %</td>
      <td>0.3010</td>
      <td>0.01 %</td>
    </tr>
    <tr>
      <td>$log_{10}(3)$</td>
      <td>0.5</td>
      <td>4.80 %</td>
      <td class="good">0.477</td>
      <td>0.03 %</td>
    </tr>
    <tr>
      <td>$log_{10}(4)$</td>
      <td class="good">0.6</td>
      <td>0.34 %</td>
      <td>0.602</td>
      <td>0.01 %</td>
    </tr>
    <tr>
      <td>$log_{10}(5)$</td>
      <td class="good">0.7</td>
      <td>0.15 %</td>
      <td>0.699</td>
      <td>0.00 %</td>
    </tr>
    <tr>
      <td>$log_{10}(6)$</td>
      <td>0.8</td>
      <td>2.81 %</td>
      <td class="good">0.778</td>
      <td>0.02 %</td>
    </tr>
    <tr>
      <td>$log_{10}(7)$</td>
      <td>0.8</td>
      <td>5.34 %</td>
      <td class="good">0.845</td>
      <td>0.01 %</td>
    </tr>
    <tr>
      <td>$log_{10}(8)$</td>
      <td class="good">0.9</td>
      <td>0.34 %</td>
      <td>0.903</td>
      <td>0.01 %</td>
    </tr>
    <tr>
      <td>$log_{10}(9)$</td>
      <td>1.0</td>
      <td>4.80 %</td>
      <td class="good">0.954</td>
      <td>0.03 %</td>
    </tr>
  </tbody>
</table>

As you can see, there is a value with a sub 1 % error for each logarithmic expression (the one in green). Personally, I chose to memorize the following sequence of values. I find that they are relatively easy to remember because of their regularities. They also highlight a key characteristic of logarithmic grow, namely that the input value has to increase by some factor for the output value to increase by a constant amount[^8]. Also, as you can see above, some values are a bit imprecise.

<table>
  <tbody>
    <tr>
      <td colspan="2">$x$</td>
	  <td colspan="2">$e$</td>
      <td colspan="2">1</td>
      <td colspan="2">2</td>
      <td colspan="2">3</td>
      <td colspan="2">4</td>
      <td colspan="2">5</td>
      <td colspan="2">6</td>
      <td colspan="2">7</td>
      <td colspan="2">8</td>
      <td colspan="2">9</td>
      <td colspan="2">10</td>
    </tr>
    <tr>
      <td colspan="2">$log_{10}(x)$</td>
      <td colspan="2">0.4343</td>
      <td colspan="2">0.0</td>
      <td colspan="2">0.3</td>
      <td colspan="2">0.5</td>
      <td colspan="2">0.6</td>
      <td colspan="2">0.7</td>
      <td colspan="2">0.8</td>
      <td colspan="2">0.85</td>
      <td colspan="2">0.9</td>
      <td colspan="2">0.95</td>
      <td colspan="2">1.0</td>
    </tr>
	<tr class="gradient-row">
	  <td colspan="2" class="none"></td>
      <td colspan="3" class="none-into-first"></td>
	  <td colspan="2" class="first-into-second">$\underset{+0.3}{⤻}$</td>
      <td colspan="2" class="second-into-third">$\underset{+0.2}{⤻}$</td>
      <td colspan="2" class="third">$\underset{+0.1}{⤻}$</td>
      <td colspan="2" class="third">$\underset{+0.1}{⤻}$</td>
      <td colspan="2" class="third-into-fourth">$\underset{+0.1}{⤻}$</td>
      <td colspan="2" class="fourth">$\underset{+0.05}{⤻}$</td>
      <td colspan="2" class="fourth">$\underset{+0.05}{⤻}$</td>
      <td colspan="2" class="fourth">$\underset{+0.05}{⤻}$</td>
      <td colspan="2" class="fourth">$\underset{+0.05}{⤻}$</td>
    </tr>
  </tbody>
</table>

[TODO: Flashcards]

# The hard part

Now we've got most things covered. The last piece that's missing is getting all of this into your brain forever. The best way to start is to look up a bunch of exercises and simply work through them. For example, I found [this one](https://math.colorado.edu/math1300/resources/Exercises_LogarithmicFunction.pdf) early on.

I said at the beginning of this post that you'd learn how to quickly compute $log_{10}(64)$ by hand. Now that we've got a good idea of what we're dealing with, this shouldn't be too difficult.

Let's think: we need to break up $64$ into an expression made up of logarithms we know. This is not hard, for example  $64 = 8 \cdot 8$. The rest is easy:

$$log_{10}(64) = log_{10}(8 \cdot 8) = log_{10}(8) + log_{10}(8) \approx 0.9 + 0.9 = 1.8\text{.}$$

Just writing this, I am filled with a rush of excitement and awe. Now let's check, how close did we get this time? $log_10(64) = 1.8062$ which means we were off by only $0.0062$! We won't get this close for all numbers and some expressions might be more difficult than this too, but it's really staggering how easy this is.

[TODO: Add more examples and exercises here.]

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

[^7]: Biglke, A., Köhler, N., Kuschnerow, H., & Ledworuski, G. (2007). <cite>Mathematik: Analythische Geometrie Stochastik</cite> (2nd ed., Vol. 2). Cornelsen.

[^8]: Abelson, H., Sussman, G. J., & Sussman, J. (1996). <cite>Structure and Interpretation of Computer Programs</cite> (2nd ed.). Mit Press. 1.2.3 Orders of Growth

[^9]: In fact there are only [two distinct numbers n and m](https://keith-mcnulty.medium.com/only-one-pair-of-distinct-integers-satisfy-this-equation-76ea45469a96) that fulfill the requirement that $n^m = m^n$ which are $2^4 = 4^2 = 16$.

<!--  LocalWords:  frac Cornelsen Mit nd Sussman
 -->
