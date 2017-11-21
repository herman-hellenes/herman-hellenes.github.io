---
layout: post
title: "A short note on trigonometry"
date: 2017-11-21
comments: true
---

Hi there, I hope you have a great day. I have been thinking of this for quite some time; we quickly forget what we have learned. For people learning a lot of new stuff and skills, of course this happens. However, the other day I had to quickly read up on Derivative Pricing and Quantitative Risk Management, which I haven't payd too much attention to in a while. Luckily I had ready great notes from my university courses and slides I've done at work, so the task was not too bad. Therefore, I've decided to try to recap important stuff I know now and then, to keep it rather fresh in mind.

First off, I start all the way back to high school. I realized; if someone asked me "What is Cosine and why should i care?", I would have to think a bit to get a good and precise answer. So now I try to do a repetition of the key concepts of trigonometry, assuming we have all learned and used this extensivly, but need a quick recap of the highlights. Disclaimer: Wikipedia has some great articles on the subject, and I have been using them to a great extent, both phrases and figures.  

### Why does trigonometry matters?
Might for many people seem like a stupid question, but it is still essensial. Wikipedia says "Trigonometry (from Greek trigōnon, "triangle" and metron, "measure") is a branch of mathematics that studies relationships involving lengths and angles of triangles."

Well, that is for sure right. But the applications are far more broad than just to fool around with a single triangle, which we usually do in high school. Funny enough, trigonometry is a key tool used to describe nature. It sounds obious that trigonometry is usefull when constructing a building, however there are so many natural motions that also can be described with these trigonometric functions. We describe light and physical waves with trigonometric functions, and even matter in quantum physics, as well as more practical oriented engineering. A simple, and important, example is describing the movement of a ball attached to a spring.

### Let's start with the "beginning" - Pythagoras
Trigonometry starts back with Pythagoras. His theorem says that the square of the hypotenuse is equal to the sum of the squares of the other two sides. So first, how did he come up with this? One way to prove it, there are many, is the proof of rearrangement. This is shown below in the animation, and is indeed a intuitive presentation. 

![center](/figs/trigonometry/Pythagoras-proof-anim.svg)

## Recalling trigonometric functions 
Now, we get the above, but how was this sine, cosine stuff again? We are talking about trigonometric functions; functions of an angle. They all relate the angles of a triangle to the lengths of its sides. What many recall, is that you had a task to calculate one side of a triagle, where an angle the length of another side is known. This is a very practical problem, which shows up in all kinds of scenarios. But what we usually did, is that we looked up the formulas for sine, cosine and so on, perhaps did some algebra, and we got to the solution! The trigonometric functions can be defined in several ways, where each definition brings along its own intuition. We will walk through them straight away.

### Right-angled triangle definitions
For any right-angeled triangle, the trigonometric functions are some ratio of the lenghts in the triangle. That's it! See the table below for the definitions.

![center](/figs/trigonometry/trigonometric_functions.png)



### Unit circle definitions
This is a bit more interesting approach if you'd ask me. The unit circle give a whole new intuition, that will be important also for grasping complex numbers. You could recall the definition by looking at the figure below.

![center](/figs/trigonometry/418px-Sinus_und_Kosinus_am_Einheitskreis_1.svg.png)

The unit circle has radius equal to one, thereof the name, and is centered at the origin. If we look closely at the right-angled triangle definitions, they only make sience for angles between 0 and {{sfrac|{{pi}}|2}} radians. However, the unit circle definition extends the definitions of the trigonometric functions to all positive and negative arguments! 

The equation for the unit circle is simply
: <math>x^2 + y^2 = 1.</math>

What is now cool, is that the hypotenus is always equal to one; it is just the radius of the circle! So the definitions of sine and cosine metioned above gives simply that sin(theta) = x and cos(theta)=y, making them the coordinates on the circle surface.

Further, for angles greater than 2π or less than −2π, we simply continues to rotate around the circle; sine and cosine are thus periodic functions with period 2π:
{\displaystyle {\begin{aligned}\sin \theta &=\sin \left(\theta +2\pi k\right)\,,\\\cos \theta &=\cos \left(\theta +2\pi k\right)\,,\end{aligned}}} {\displaystyle {\begin{aligned}\sin \theta &=\sin \left(\theta +2\pi k\right)\,,\\\cos \theta &=\cos \left(\theta +2\pi k\right)\,,\end{aligned}}}
for any angle θ and any integer k. 

### Series definitions
Trigonometric functions are analytic functions. These can be approximated to a k-times differentiable function around a given point by a k-th order Taylor polynomial. The statement of the most basic version of Taylor's theorem, when having one real variable, is as follows:

![center](/figs/trigonometry/taylors_theorem.png)

The proof of this can be found [here](https://en.wikipedia.org/wiki/Taylor%27s_theorem#Proof_for_Taylor.27s_theorem_in_one_real_variable), which is actually quite a simple exercise leveraging L'Hopital's rule.

Ok, back to the trigonometric functions. Let's start with sine. First, we need the following results

d/dx sin(x) = cos(x)
d/dx cos(x) = -sin(x)

I will not give the proof here, but is easily walked through [here](https://www.khanacademy.org/math/ap-calculus-ab/ab-derivative-rules/ab-diff-sin-cos/a/proving-the-derivatives-of-sinx-and-cosx). It consists basically with some limits tricks, nothing very tricky.
Now we can apply Taylor's theorem on sin(x), expanding around zero (in this special case its also referred to as a Maclaurin series).
In order to get this series on a nice little form, we have to check if this converges. To do this, we can use the Lagrange form of the remainder, which is obtained during the standard proofs of Taylor's Theorem. The trick here is that the k'th remainder term is always bounded in absolute value by x^(k+1) / (k+1)!  because the successive derivatives are always just a sins or cos (with some sign). It's easy to see that for any x, as k approaches infinity, that this error term goes to 0. Thus the expansion does converge to sin⁡(x) and we get 

![center](/figs/trigonometry/taylor_sine.png)


Since cosine is the derivative (with negative sign) of sine, we easily get the result for cosine as well. 




#### Relationship to exponential function and complex numbers
It can be shown from the series definitions that the sine and cosine functions are respectively the imaginary and real parts of the exponential function of a purely imaginary argument. Euler's formula states that for any real number x
{\displaystyle e^{ix}=\cos x+i\sin x,} {\displaystyle e^{ix}=\cos x+i\sin x,}

Here i is the imaginary unit. This is a crucial result used in mathematics, physics and engineering. Richard Feynman has called this formula for "our jewel" and "the most remarkable formula in mathematics". But how do we get our heads around this? So the formula is saying that the function e^(iφ) is a unit complex number, meaning that it traces out the unit circle in the complex plane as φ ranges through the real numbers. Here φ is the angle that a line connecting the origin with a point on the unit circle makes with the positive real axis, measured counterclockwise and in radians.

![center](/figs/trigonometry/512px-Euler's_formula.svg.png)

So, in the same fashion as showed above in the unit circle definition, now a point in the complex plane can be represented by a complex number written in cartesian coordinates. Euler's formula provides a means of conversion between cartesian coordinates and polar coordinates. The polar form simplifies the mathematics when used in multiplication or powers of complex numbers. Any complex number z = x + iy, and its complex conjugate, z = x − iy, can be written as

![center](/figs/trigonometry/euler_4.png)


The proof of this starts with the power series of the exponential, followed by the results we showed above:
![center](/figs/trigonometry/euler_formula_step1.png)

![center](/figs/trigonometry/eulers_formula_step2.png)

So we can represent our beloved sine and cosine as

![center](/figs/trigonometry/eulers_formula_3.png)


## So again, why the heck do we care? 
There are so many fundamental use cases for trigonometric functions. As stated, the obious ones are for constructing buildings and other rather practical usages.

Since both the sine and cosine functions satisfy the differential equation {\displaystyle y''=-y\,.} {\displaystyle y''=-y\,.}, the functions fit well to describe a harmonic oscillator. And harmonic oscillators are all around us; in instruments, waves in the sea, light, elemetary particles. Trigonometric functions thus prove to be useful in the study of general periodic functions, which is used in all of physics to some extent.

As well, even though we want to describe a non-period function, we can leverage trogonometric functions. For instance we use Fourier series in signal processing. We can use a combination of sine and cosine waves to construct basically whatever sound we want, as the figure below illustrates

![center](/figs/trigonometry/Sawtooth_Fourier_Animation.gif)

Futher, the role trigonometic functions play in complex numbers are very useful. In quantum mechanics for example, the complex Hilbert spaces provide the context for a mathematical formulation that is convenient and most standard. In the theory of relativity, some formulas for the metric on spacetime become simpler if one takes the time component of the spacetime continuum to be imaginary. As well can the treatment of resistors, capacitors, and inductors be unified by introducing imaginary, frequency-dependent resistances for the latter two and combining all three in a single complex number called the impedance. And all this is the "tip of the iceberg".


Alright, hope that this was a repetition was fun, rediscovering the beauty of trigonometric functions. So long, cheers!


