---
layout: post
title: Computing logarithms manually
---

I have become fascinated by the ability to reason about and calculate the results of logarithmic functions in one's head. To me, logarithms have always felt like a black box that couldn't be conquered. They are a fundamental building block of mathematics, yet every time I saw a logarithmic equation, I was tempted to grab my calculator or to look up how to solve the example at hand. Over the past half year, I've spent some time improving my understanding of logarithms and learning how to compute the results of logarithmic equations by hand. Here is what I've found!

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

The fact that [exponentiation is not commutative](https://en.wikipedia.org/wiki/Commutative_property#Division,_subtraction,_and_exponentiation) means that it has **two different inverse operations: the nth-root and the logarithm**. Understanding this is very important. There is nothing special about a binary operation having two different inverse functions. After all, if we have binary operation [represented as a function] $c = a \circ b$ we want to be able to both get $a$ from $c$ and $b$ and $b$ from $c$ and $a$ [^4]. For commutative operations like addition and multiplication, getting either $a$ or $b$ just happens to involve the same operation.

If way say that $x = b^n$, then the nth-root is defined as $b = \sqrt[n]{x}$. A sentence that describes what's happening here declaratively might so as follows: "the nth-root of a number x yields the base b, such that b to the power of n is equal to x". This can also be phrased as a question were the result value of the nth-root is seen as the answer to that question: "what's be base b such that b to the power of n is equal to x?".

Given the two variables of the exponentiation $x$ and $n$, the roots yields the third one $b$. Accordingly, the logarithm, which is just the other inverse function for powers, yields the other parameter $n$ from $x$ and $b$: $log_b(x) = n$. The fitting questing would be: "what's the exponent n of b such that b to the power of n is equal to x?". As you can see, the question describing the operation has exactly the same structure with a different sequence. The part that's hard to think here is the "such that" part of the question. We basically have to think in reverse to answer the it. That's the difficulty of inverse functions.

I'd also like to share a figure that helped me improve my understanding of the relationship between the three functions.

![Relationship between powers, roots and logarithms]({{ '/public/figures/relationship-power-root-logarithm.png' | absolute_path}})

It stems from a German mathematics textbook from 1997 called Handbuch Mathematik [^5] which translates to <i>Handbook Mathematics</i>. The caption reads <i>Relationship between power, root and logarithm or between value of power, base and exponent</i>. I added the context about this figure's origin to make this part more memorable because this triangular relationship is key. [This answer](https://math.stackexchange.com/a/165225) on Stack Exchange builds on the same idea to suggest an alternative notation for powers, roots and logarithms that emphasizes this relationship.

# Definition of logarithms

As described above, given the result of an exponentiation $y = b^x$ and the base $b$, $x$ is called the logarithm of $y$ to the base $b$ which is written as $x = log_b(y)$ [^6]. This definition provides us with the following identities:

$$x = b^{log_b(x)} = log_b({b^x})$$

. Both of these are very important. Ideally, you'd want them to come to mind every time you're looking to solve an equation involving logarithms. While they're often given as the very basics, their *reverseness* makes them difficult to think about.

---

[^1]: This is about how difficult the calculation feels and how long it takes to carry out, not about how hard it would theoretically be, given you knew all possible algorithms, tricks and exceptions.

[^2]: For example, if you want to remember something long term, [spaced repetition](https://ncase.me/remember/) is a [much better strategy](https://gwern.net/spaced-repetition) than drilling it very intensely for a relatively short amount of time. This seems to be a common problem (or misconception) about project based learning, too. Without repetition, it's easy to forget concepts that were used only once during a single project. It also applies to learning for exams and is likely a key factor in why students don't feel motivated to  learn purely for an exam. I've found that the experience of learning during either a project or for an exam can be made much more rewarding by putting in a small amount of extra work in repeating the content a few times so that you can recall it long-term.

[^3]: https://www.sciencedirect.com/topics/mathematics/inverse-operation is a starting point. Just like Knuth, it has a lot of interesting stuff to say about logarithms.
