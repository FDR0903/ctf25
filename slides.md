---
layout: cover
class: text-center
title: CTF 2025
theme: academic
titleTemplate: '%s'
favicon: ./images/defiicon.png
author: Fayçal Drissi
themeConfig:
  paginationX: disabled
  paginationY: disabled
  paginationPagesDisabled: [1]
fonts:
  local: Montserrat, Roboto Mono, Roboto Slab # local fonts are used for legal reasons for deployment to https://slidev-theme-academic.alexeble.de and only set up for the example project, remove this line for your project to automatically have fonts imported from Google

mdc: true
---

# Continuous-Time Finance
<br />

## Lecture notes
<br />

### *Fayçal Drissi*
[website](https://www.faycaldrissi.com/)

<br />

####  *Saïd Business School, University of Oxford*

#### Trinity Term 2025 

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Why Continuous-Time Finance ? <a name="defi"></a></h1>
</p>


---

# Why Continuous-Time Finance ?

* Events in real world happen in discrete-time

* Quickly changing chain of events may be described in term of a continuous mechanism

* Example: stock prices evolve almost continuously. Think of limit order books

* Continuous-time models are tractable when it comes to describe the behaviour of complex derivatives
  * A derivative is a contract whose value is dependent upon one or more underlying assets

---

# The Derivatives market

![derivativessize](./images/derivativessize.png){style="transform: translate(20%, 0%); width: 600px"}

---

# Goals of this course

* Introduce continuous-time models

* Applications for pricing derivatives on Equities and Interest rates


# How

* (Basic) review of probabilioty theory

* Introduction to stochastic calculus

* Introduction of the main pricing principles

* We start by a simple discrete-time model

---


# Course outline
### Session 1: Binomial model for option pricing
### Session 2: Pricing Principles and the Absence of Arbitrage
### Session 3: Introduction to Stochastic Processes
### Session 4: The Black-Scholes Model
### Session 5: Risk-Neutral Pricing in Continuous-Time
### Session 6: Pricing in practice
### Session 7: ...
### Session 8: ...

---


# Format

* Each lecture will consist of a set of slides shared before the class

* Exercises will be solved during class: bring pen and paper (or iPad and pencil)

* Problem sets will be regularly distributed and selected problems solved in class

* Check Canvas for info, slides, exercises and solutions!

* Office hours on demand: faycal.drissi@gmail.com

---


# Assessment

* Final $2-$hours examination at the end of the term

* 4 questions

* Preparation: exercises during class, problem sets, and past exams

---
layout: intro
---
## Session $1$:  Binomial Model and Option Pricing
<br />
<br />

*Fayçal Drissi*

*Saïd Business School, University of Oxford*

--- 

# Risk and Return

* Assume there are two states of the world.

* Every day, there is either a sunny or a rainy day with probability $p=1/2$ and $1-p=1/2$.

* There is an ice-cream company (IC) whose stock price is trading at $50$ and an umbrella company (U) whose stock price is also trading at $50$.

* If it is a sunny day the IC company’s stock increases to $100$ otherwise it drops to zero. The U company has opposite dynamics.


![ICandU](./images/ICandU.png){style="transform: translate(10%, -5%); width: 700px"}

--- 

# Risk and Return
<br /><br /><br />

* If you have $1$ GBP to invest, how much would you put on IC and/or U ?

![ICandU](./images/ICandU.png){style="transform: translate(10%, -5%); width: 700px"}

--- 


# Risk and Return
<br /><br /><br />

* Suppose now that the probability of raining is p = 9/10. How would you change your strategy?

![ICandU](./images/ICandU.png){style="transform: translate(10%, -5%); width: 700px"}


--- 

# Risk and Return
<br /><br /><br />

* Assume that there is a bond in this economy that pays an interest of $r$. How much "above" $r$ would you expect to make on your investment strategy?


![ICandU](./images/ICandU.png){style="transform: translate(10%, -5%); width: 700px"}

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Binomial Setup <a name="defi"></a></h1>
</p>

---

## First example: a simple economy with three assets

* Two dates: $t$ and $t+1$

* Two assets are traded at prices $S_1(t)$ and $S_2(t)$ at time $t$

* At $t+1$, there are two states of nature that occur with probability $p$ and $1-p$

* Asset $1$ pays $S^1(t+1) = 1$ in state one and $S^1(t+1) = 1$ in state two. We denote the payoff (1, 1). 

* Asset $2$ has payoff $(0, 3)$.

![S1S2](./images/S1S2.png){style="transform: translate(10%, -0%); width: 700px"}

---

## First example: a simple economy with three assets

* Assume we know $S_1(t)$ and $S_2(t)$.
* **Problem**: There is a third asset paying $(2, 3)$. Can calculate its price $S_3$ at time $t$.

![S1S2S3](./images/S1S2S3.png){style="transform: translate(0%, 0%); width: 900px"}

---

## First example: a simple economy with three assets

* **Solution**: 
  * We set a portfolio with value $\Pi(t)$ at time $t$ consisting of $\alpha_1$ units of Asset $1$ and $\alpha_2$ of Asset $2$
  * We set the portfolio weights  $\alpha_1$ and $\alpha_2$ such that the portfolio **replicates** Asset $3$ at time $t+1$
    $$\Pi(t+1) = \alpha_1\,S^1(t+1)+\alpha_1\,S^2(t+1)$$
  * By **no-arbitrage**, 
  $$\Pi(t) = S_3(t)$$
  

![S1S2S3](./images/S1S2S3.png){style="transform: translate(20%, -5%); width: 600px"}

---

## First example: a simple economy with three assets

* **Replication argument**
  * We set $\alpha_1$ and $\alpha_2$ such that 
  $$
  \begin{cases}
  \Pi(t+1) = 2 = \alpha_1 \times 1 + \alpha_2 \times 0 \quad \text{in state one}   \\
  \Pi(t+1) = 3 = \alpha_1 \times 1 + \alpha_2 \times 3 \quad \text{in state two}
  \end{cases}
  $$
  ![S1S2S3](./images/S1S2S3.png){style="transform: translate(30%, 0%); width: 500px"}
  * We find that 
  $$\alpha_1 = 2 \quad \text{and} \quad \alpha_2 = 1/3$$
  * By **no-abitrage**: 
  $$S_3(t) = 2\,S_1(t)+S_2(t)/3$$
  

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Pricing Options in a Binomial Setup <a name="defi"></a></h1>
</p>

---

## The market

* Starting time $t$, ending time $T$
* Two states of the world with probabilities $p$ and $1 − p$
* Starting value of the stock price: $S$
* In the *up state*, with probability $p$, the price becomes $u\,S$ where $u$ is a constant
* In the *down state*, with probability $1-p$, the price becomes $d\,S$ where $u$ is a constant
* There is a bond that pays a constant interest rate $r$.


![binomialO1](./images/binomialO1.png){style="transform: translate(10%, 20%); width: 700px"}

---


## The call option

* **Definition**: A European Call option with strike price $K$ and maturity $T$ is the right to buy, at time $T$, the underlying stock for the price $K$. 

* What is the payoff of the option as a function of $S$ ?


---


## The call option

* **Definition**: A European Call option with strike price $K$ and maturity $T$ is the right to buy, at time $T$, the underlying stock for the price $K$. 
![binomialO2](./images/binomial02.png){style="transform: translate(10%, 0%); width: 700px"}

* The payoff at time $T$ is $\max\{S(T) - K, 0 \}$. Let $C(t)$ be the price of the option at time $t.$ 
* In the *up state*, the payoff of the call is 
$$
C^u = \max\{u\, S - K, 0\}
$$
* In the *down state*, the payoff of the call is 
$$
C^d = \max\{d\, S - K, 0\}
$$

---

## The call option

* The payoff of a long position in a call option with strike $K=100$ : 

![call](./images/call.png){style="transform: translate(40%, 0%); width: 500px"}

* When do we buy a call option ?

---

## The put option

* **Definition**: A European Put option with strike price $K$ and maturity $T$ is the right to sell, at time $T$, the underlying stock for the price $K$
* The payoff at time $T$ is $\max\{K - S_T\}$
* The payoff of a long position in a put option with strike $K=100$ (when do we buy a put ?)

![put](./images/put.png){style="transform: translate(40%, 0%); width: 500px"}

---

## The call option

* How do we price the call in our binomial model, i.e., how do we find $C(t)$ ?

![binomialO2](./images/binomial02.png){style="transform: translate(10%, 0%); width: 700px"}

---

## The call option

* To price the call, we replicate its payoff with the bond and the underlying asset S

* At time $t$, we set a portfolio $\Pi(t)$ with $B$ pounds in the bond and $\Delta$ units of the asset $S$, such that 
$$
\Pi^u(t+1) = C^u \text{  and  } \Pi^d(t+1) = C^d
$$


![binomialO3](./images/binomial03.png){style="transform: translate(0%, 20%); width: 800px"}


---

## The call option

* The price of the portfolio at time $t$ is
$$
\Pi(t) = B + \Delta\,S.
$$

* We choose $\Delta$ and $B$ such that
$$
\begin{cases}
\Pi^u(t+1) = B\, (1+ r) + \Delta\,u\,S = C^u \\
\Pi^d(t+1) = B\, (1+ r) + \Delta\,d\,S = C^d
\end{cases}
$$

---

## The call option

* The price of the portfolio at time $t$ is
$$
\Pi(t) = B + \Delta\,S.
$$

* We choose $\Delta$ and $B$ such that
$$
\begin{cases}
\Pi^u(t+1) = B\, (1+ r) + \Delta\,u\,S = C^u \\
\Pi^d(t+1) = B\, (1+ r) + \Delta\,d\,S = C^d
\end{cases}
$$


* In matrix form we solve the system
$$
{\left[\begin{array}{ll}
u S & 1+r \\
d S & 1+r
\end{array}\right]\left[\begin{array}{c}
\Delta \\
B
\end{array}\right]=\left[\begin{array}{c}
C^u \\
C^d
\end{array}\right]}
$$

* Therefore
$$
{\left[\begin{array}{c}
\Delta \\
B
\end{array}\right]=\frac{1}{(1+r)(u S-d S)}\left[\begin{array}{cc}
1+r & -(1+r) \\
-d S & u S
\end{array}\right]\left[\begin{array}{c}
C^u \\
C^d
\end{array}\right]}
$$

---

## The call option

* We find
$$
\Delta=\frac{C^u-C^d}{u S-d S}, \quad \text { and } \quad B=\frac{-d C^u+u C^d}{(1+r)(u-d)}
$$

* By **no-abitrage**, the portfolio at time $t$ has the same value as the call and we write ($R=1+r$)
$$
C(t) = \Delta S+B  =\frac{C^u-C^d}{u S-d S} S+\frac{-d C^u+u C^d}{R(u-d)} =\frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d} C^d\right] .
$$


---

## Example of option strategies: a covered call option

* In a covered call strategy, an investor buys the stock and sells a call option on the stock
* The payoff is
$$
- \max\{S_T - K\} + (S_T - S_0)
$$
![coveredcall](./images/coveredcall.png){style="transform: translate(55%, 0%); width: 400px"}
* You are a banker and you want to buy a covered call option from your broker. Assume $S_0=K$ and that all payments are at time $T$, what's the price according to our binomial model ?

---

## Example of option strategies: a covered call option

* In the case of covered call, the payoff in the up and down states is
$$ 
\begin{cases}
\tilde C^u = \max\{u\,S-K, 0\} + u\,S - S_0= C^u + u\,S - S_0 \\
\tilde C^d = \max\{d\,S-K, 0\} + d\,S - S_0= C^d + d\,S - S_0,
\end{cases}
$$

* The price is 
$$
\begin{split}
P(t)& =\frac{1}{R}\left[\frac{R-d}{u-d} \tilde C^u+\frac{u-R}{u-d}  \tilde C^d\right]\\
& =\frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d}  C^d - \frac{R-d+u-R}{u-d}S_0 + \frac{(R-d)u+(u-R)d}{u-d}S \right]\\
& = \frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d}  C^d - S_0 + R\,S \right]\\
& =  S - S_0/R +  \frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d}  C^d \right]
\end{split}
$$
* We can price any strategy that combines stocks and call/puts! : Straddle, Call spread, Put spread, Protective Collar ...

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Risk-Neutral Valuation <a name="defi"></a></h1>
</p>

---

## Risk-Neutral Valuation - Call option

* We found that the call option price is
$$
C(t) =\frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d} C^d\right] .
$$

* **Remark:** the price $C(t)$ of the option does not depend on the binomial probability $p.$

---

## Risk-Neutral Valuation - Call option

* We found that the call option price is
$
C(t) =\frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d} C^d\right] .
$

* **Remark:** the price $C(t)$ of the option does not depend on the binomial (physical) probability $p.$

* Define a new probability measure $\tilde P$ that assigns a probability 
$$
\tilde p = \frac{R-d}{u-d}
$$
to the *up state* and $1-\tilde p$ to the *down state*


* The price of the option is
$$
C(t) =\frac{1}{R}\left[\tilde p C^u+(1-\tilde p) C^d\right] .
$$

![binomialO4](./images/binomialO4.png){style="transform: translate(30%, 0%); width: 500px"}



---

## Risk-Neutral Valuation - Call option

![binomialO4](./images/binomialO4.png){style="transform: translate(14%, 0%); width: 600px"}

* Necessary condition for absence of arbitrage is $\tilde p \in (0, 1)$, which implies 
$$d < 1 + r < u$$

* In this case, the price of the option is the **discounted expectation** under the new **risk-adjusted probability measure**

$$
C(t) =\frac{1}{R}\left[\tilde p C^u+(1-\tilde p) C^d\right] = \frac{1}{1+r}\tilde{\mathbb E}[C(t+1)] 
$$

---

## Risk-Neutral Valuation

* Prices of assets depend on their risk
* Investors demand more profit for bearing more risk (risk-averse)
* Today's price of a claim realised in a future date, written on a risky asset, will generally differ from its expected value
* In a complete market with no arbitrage opportunities there is an alternative way to do this calculation: Instead of first taking the expectation and then adjusting for an investor's risk preference, one can adjust, once and for all, the probabilities of future outcomes such that they incorporate all investors' risk premia, and then take the expectation under this new probability distribution, the risk-neutral measure
* once the risk-neutral probabilities are found, every asset can be priced by simply taking the present value of its expected payoff. Note that if we used the actual real-world probabilities, every security would require a different adjustment (as they differ in riskiness). 
* fundamental theorem of asset pricing: the condition of no-arbitrage is equivalent to the existence of a risk-neutral measure

---

## Risk-Neutral Valuation

* **Exercise 1**: Under the risk-neutral measure, calculate the discounted expected value of the stock price, i.e.,
$$
\frac{1}{1+r}\,\tilde{\mathbb E}[S(t+1)]
$$

* What is the price of a European call with strike $K=0$ ?

* Would the price change if the probability $p$ or $u,d$ change ?

---

## Risk-Neutral Valuation

* Assume now that there are three dates ${0, 1, 2}$ and consider the following binomiam tree (where $u=1/d$)

![binomialO5](./images/binomialO5.png){style="transform: translate(20%, 0%); width: 600px"}

* **Exercise $2$**: Compute recursively the price of the European call option with strike $K$ and maturity $T = 2$

---

## Probability jargon: random variables and sample space

![binomialO5](./images/binomialO5.png){style="transform: translate(20%, 0%); width: 600px"}

* At time $0$, $S_1$ and $S_2$, the stock prices at times $1$ and $2$, are **random variables**.

* To describe the random behaviour of $S_1$ and $S_2$, we use the **sample space**

$$
\Omega = \{\text{LL},\text{LH},\text{HL},\text{HH}\}
$$
of all outcomes $\omega\in\Omega$ that can be realised

---

## Probability jargon: sigma algebra

* Let $\mathcal F$ be the family of all subsets of $\Omega$

* **Definition of sigma algebra**: a sigma algebra $\mathcal G \subset \mathcal F$ is a family of subsets of $\Omega$ such that:
  * $\emptyset \subset \mathcal G$
  * If $A \in \mathcal G$ then $A^C \subset \mathcal G$
  * If $(A_i)_{i} \in \mathcal G$ is a countable sequence in $\mathcal G$, then $\bigcup_i A_i \in \mathcal G$

* The couple $(\Omega, \mathcal G)$ is called a measurable space.

---

## Probability jargon: filtration

![binomialO5](./images/binomialO5.png){style="transform: translate(30%, 0%); width: 500px"}

* The information available to the trader at time $0$ can be modeled by the information set 
$$\mathcal G_0 = \{\emptyset, \Omega\}$$

* At time $1$, we can observe the outcome of time $1$. The information set gets larger: it is a sigma algebra generated by the price movement
$$
\mathcal G_1 = \{\emptyset, \Omega, \{HL, HH\}, \{LL, LH\} \}
$$

* At time $2$, we can observe more outcomes in more detail 
$\mathcal G_2 =\mathcal P(\Omega)$ (power set), i.e., it is the set of all subsets of $\Omega$, including $\Omega$ and the empty set.

---

## Probability jargon: filtration

![binomialO5](./images/binomialO5.png){style="transform: translate(30%, 0%); width: 500px"}

* The trader's information set is growing over time

$$\mathcal G_0 \subset \mathcal G_1 \subset \mathcal G_2$$

* **Definition : Filtration**
  * A fitlration is a sequence $(\mathcal G_i)_i$ of sigma algebras over $\Omega$ such that for all $i$
  $$
  \mathcal G_i \subset \mathcal G_{i+1}
  $$


---

## Some probability jargon: probability measure

* **Purpose**: assign probability to events in a consistent way
* **Definition**: a probability measure on $(\Omega, \mathcal G)$ is a function $\mathbb P: \mathcal G \mapsto [0, 1]$ such that 
  * $\mathbb P[\Omega] = 1$
  * (sigma additivity) For any disjoint sequence $(A_i)_i \subset \mathcal G$ such that $A_i \cap A_j = \emptyset$ :
  $$
  \mathbb P[\bigcup_i A_i] = \sum_i \mathbb P[ A_i]
  $$
* **Definition**: $(\Omega, \mathcal G, \mathbb P)$ is a probability space.

---

## Some probability jargon: random variables

* **Definition**: Let $X : \Omega \mapsto R$ be a measurable function. The sigma algebra 
$$\sigma(X) = \{X^{-1}(B) \text{ for all } B \subset \mathbb R  \}$$
is called the sigma algebra generated by $X$.

* **Definition**: $X$ is a random variable on $(\Omega, \mathcal G)$ if it is measurable with respect to $\mathcal G$, i.e., if $\sigma(X) \subset \mathcal G$

---

## Some probability jargon: random variables

* **Definition**: Let $X : \Omega \mapsto R$ be a measurable function. The sigma algebra 
$$\sigma(X) = \{X^{-1}(B) \text{ for all } B \subset \mathbb R  \}$$
is called the sigma algebra generated by $X$.

* **Definition**: $X$ is a random variable on $(\Omega, \mathcal G)$ if it is measurable with respect to $\mathcal G$, i.e., if $\sigma(X) \subset \mathcal G$

* **Example** 
  * $\sigma(S_1) = \mathcal G_1$
  * $S_1$ is $\mathcal G_1$ measurable
  * $S_2$ is not $\mathcal G_1$ measurable

![binomialO5](./images/binomialO5.png){style="transform: translate(60%, -90%); width: 500px"}


---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
American options <a name="defi"></a></h1>
</p>

---

## American options in the three-dates binomial model

* **Definition:** an *American* option can be exercised at any point in time during the life of the option
* **Definition:** a *Bermudean* option can be exercised at specific pre-arranged times

* To decide whether to exercise, at each time $t$, the holder of an american option compares 
  * the value of exercising the option at time $t$
  * and the value of keeping the option 

* So the price of the american option at each time $t$ is 
$$
\max\{\text{exercise value at t, option value between t and T}\}
$$

* We can price american options recursively

---

## American options in the three-dates binomial model

* Let $V(S_t)$ be the payoff of an option which is exercised at time $t$
  * For instance, for an american call option, $V(S_t) = \max\{S_t-K, 0\}$

* Assume a three-dates binomial model 

![binomialO5](./images/binomialO5.png){style="transform: translate(0%, 0%); width: 800px"}


---

## American options in the three-dates binomial model

We work backward:
  * At time $t=2$, the payoff is simply $V(S_2)$ for both American and European options. We know the payoffs for each possible value of the stock at time $t=2$

![americanbinomial1](./images/americanbinomial1.png){style="transform: translate(0%, 0%); width: 800px"}


---

## American options in the three-dates binomial model

We work backward:
  * At time $t=1$, the payoff of the American option is the maximum between the exercise value $V(S_1)$, and the discounted expected future payoff (at time $t=2$)

![americanbinomial2](./images/americanbinomial2.png){style="transform: translate(0%, 0%); width: 800px"}

---

## American options in the three-dates binomial model

We work backward:
  * At time $t=0$, the payoff of the American option is the maximum between the exercise value $V(S_0)$, and the discounted expected future payoff (at time $t=1$)

![americanbinomial3](./images/americanbinomial3.png){style="transform: translate(0%, 0%); width: 800px"}


---
layout: end
---
Thank you !

[faycaldrissi.com](https://www.faycaldrissi.com/)
