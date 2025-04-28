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
Course outline <a name="defi"></a></h1>
</p>

---


# Course outline
### Session 1: Binomial model for option pricing
### Session 2: 

---
layout: intro
---
## Session $1$:  Binomial Model and Option Pricing
<br />
<br />

*Fayçal Drissi*

*Saïd Business School, University of Oxford*

--- 

# Overview
<br />

### The binomial model

* 1
* 2

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

AMERICAN OPTIONS 

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

---
layout: intro
---
## Session $2$:  Pricing Principles and the Absence of Arbitrage
<br />
<br />

*Fayçal Drissi*

*Saïd Business School, University of Oxford*

---

## Outline


---

## Session 1 

* What is a sample space ?

* What is a filtration ?

* XXX

---

## A more general binomial model

* Transaction dates $\mathcal T=\{0, 1, 2, \dots, n\}$

* Sample space $\Omega =$ $\{$Sequences of $H$ and $L$ of length $n+1\}$

* $\mathcal F$ is the sigma algebra of all subsets of $\Omega$

* Dynamics of the stock price and the money account
$$
S_{t+1} = \begin{cases}
u\,S_t \text{ with probability p} \\
d\,S_t \text{ with probability 1-p} \\
\end{cases}
\quad\qquad 
B_{t+1} = (1+r)\,B_t 
$$

![session21](./images/session21.png){style="transform: translate(10%, 0%); width: 700px"}


---

## Expectations and condition expectations

* Assume $n=1$ and we are at time $0$. What is the expectation of $S_{1}$ under the physical measure ? 

* Assume we change probability measures to risk-neutral ($\tilde p$). What is the expectation of $S_{1}$ under the risk-neutral measure ? 

* Assume $n=1$ and we are at time $0$. What is the expectation of $S_{2}$ under the physical measure ?

* What is the expectation of $S_2$ conditional on $S_1 = 1$ ?

![session21](./images/session21.png){style="transform: translate(10%, 0%); width: 700px"}

---

## Some definitions


* **Definition**: $(S_t)_{t=0,\dots,n}$ is a sequence of random variables on a probability space $(\Omega, \mathcal F, \mathbb P)$. We call $(S_t)_t$ a *stochastic process*.

* We define $\mathcal G_t$ as the sigma algebra (information set) generated by $S$ up to time $t.$

* We call the sequence $(\mathcal G_t)_t$ the *filtration* generated by $S_t.$

* Conditional on $\mathcal G_t$, we know the value of $X_t.$

* Conditional on $\mathcal G_t$, we don't know the value of $X_{t+1}.$ But we can estimate $\mathbb E[X_{t+1} \mid \mathcal G_t]$ which is the expectation of $X_{t+1}$ conditional on the information we have up to time $t$.

* **Definition**: Let $\mathcal G'_t \subset \mathcal G_t$ be a *coarser* information set. We call $\mathbb E[X_t \mid \mathcal G'_t]$ the *conditional expectation* of $X_t$ condition on $\mathcal G'_t$

* **Remark**: $\mathbb E[X_{t+1} \mid \mathcal G'_t]$ is $\mathcal G'_t$-measurable

---

## Some definitions


* **Definition**: Two stochastic processes are independent if they generated different information sets.

* If two stochastic processes $X$ and $Y$ are independent, then 
$$
\mathbb E[X \times Y] = \mathbb E[X] \times \mathbb E[ Y]
$$


---

## Some definitions


* **Exercise**: Assume $n > 2$ in the binomiam model.  Prove that 
$$
\mathbb E[S_2 \mid \sigma(S_1)] = S_1 \, (p\, u + (1-p)\,d)
$$
where $\sigma(S_1) = \mathcal G_1$

* **Exercise**: Assume $n > 2$ in the binomial model.  Prove that 
$$
\begin{split}
\mathbb E[S_2 \mid \sigma(S_1)] & =  \mathbb E[\frac{S_2}{S_1} S_1 \mid \sigma(S_1)]  \\
& =   \mathbb E[ S_1 \mid \sigma(S_1)] \times \mathbb E[\frac{S_2}{S_1}\mid \sigma(S_1)]  \\
& = S_1 \, (p\, u + (1-p)\,d)
\end{split}
$$
where we used that $S_1$ is independent from $S_2/S_1$

---

## Some definitions

* **Property** For any $\mathcal H \in \mathcal G$, we have
$$
\mathbb E[\mathbb E [X \mid \mathcal G] \mid \mathcal H]= \mathbb E[X \mid \mathcal H] 
$$

* **Exercise**: Compute $E[S_{t+k} \mid \mathcal G_{t}]$ 

$$
\begin{split}
\mathbb E[S_{t+k}\mid \mathcal G_t] = & \mathbb E\left[\mathbb E[S_{t+k}\mid \mathcal G_{t+k-1}] \mid \mathcal G_t\right]\\
= & \mathbb E\left[S_{t+k-1} \, (p\, u + (1-p)\,d) \mid \mathcal G_t\right]
\\
= & \cdots \cdots \cdots \\
= & \mathbb E\left[S_{t} \, (p\, u + (1-p)\,d)^t \mid \mathcal G_t\right]

\end{split}
$$

---

## Adapted process and martingales

* **Definition**: A filtered probability space $(\Omega, \mathcal G, (\mathcal G_i)_i, \mathbb P)$ is a probability space $(\Omega, \mathcal G, \mathbb P)$ with a filtration.

* **Definition**: A stochastic process $X$ on a filtered probability space is adapted if every $X_t$ is $G_t$-measurable.
  * This means the best estimate of the future value of $X$ is the current value of $X$.

* **Definition**: An adapted process $X$ is *martingale* if for any $t \in\mathcal T$, we have
$$
\mathbb E[X_{t+1} \mid \mathcal G_t] = X_t
$$
or more generally, for any $s>t$, we have
$
\mathbb E[X_{s} \mid \mathcal G_t] = X_t
$


---

## Adapted process and martingales


* **Exercise**: in the $n-$period binomial model, using the filtration generated by $S$, we found
$$
\mathbb E[S_t \mid \mathcal G_{t-1}] = S_{t-1} (p\,u + (1-p)\,d)
$$
Find $p$ so the stock price is a martingale !

---

## Adapted process and martingales


* **Exercise**: If $X$ and $Y$ are two martingales on $\mathcal T$ such that $X_n = Y_n$; Show that $X_t = Y_t$ for each $t \in \{0,1,\dots,n\}$


  * We prove it by recursion. For $t=n-1$, we have
  $$
  \begin{split}
  X_{n-1} = \mathbb E[X_{n} | \mathcal F_{n-1} ] 
  \end{split}
  $$
  * However, we know that $X_{n} = Y_{n}$
  * Thus, 
  $$
  \begin{split}
  X_{n-1} & = \mathbb E[X_{n} | \mathcal F_{n-1} ] \\
  & = \mathbb E[Y_{n} | \mathcal F_{n-1} ] \\
  & =  Y_{n-1}
  \end{split}
  $$
  * We can continue by recursion.


---

##  Risk Neutral Probability Measure and Martingales

* **Reminder session 1**:
![binomialO4](./images/binomialO4.png){style="transform: translate(30%, 0%); width: 500px"}
* We defined a new probability measure $\tilde P$ that assigns a probability 
$$
\tilde p = \frac{R-d}{u-d}
$$
to the *up state* and $1-\tilde p$ to the *down state*, and where the price of the option was the discounted expected payoff.

$$
C(t) =\frac{1}{1+r}\left[\tilde p C^u+(1-\tilde p) C^d\right] = \mathbb E[ \frac{1}{1+r} C(t+1)].
$$

* $B(t+1) = 1+r$ is the $t+1$-price of a bond, whose price at $t$ is $B(t) = 1$.

* We also showed that the $S(t)/B(t) = \mathbb E[ S(t+1)/B(t+1) ].$

* Basically, we showed that, **under the risk-neutral measure**, the discounted prices of the option and the stock are martingales. 

---

##  Risk Neutral Probability Measure and Martingales

* More generally, in our binomial model with $t\in\{1,\dots,n\}$, we consider the stochastic process $(S_t/B_t)_t$:
$$
S_t / B_t = S_t / (1+r)^t
$$

* We can show that a binomial risk-neutral probability measure $\tilde P$ is obtained by defining the binomial probability
$$
\tilde p = \frac{1+r-d}{u-d}
$$

* **Exercise**: prove it that $S_t / B_t$ is a martingale under $\tilde P$.

---

##  Risk Neutral Probability Measure and Martingales

* **Exercise**: prove it (that $S_t / B_t$ is a martingale under $\tilde P$)

* We need to show 
$$
\tilde{\mathbb E}\left[S_{t+1}/B_{t+1} \mid \mathcal G_t \right] = S_{t}/B_{t}
$$

* First, $B_t = (1+r)^t$ is deterministic, thus
$$
\begin{split}
\tilde{\mathbb E}\left[S_{t+1}/B_{t+1} \mid \mathcal G_t \right] = \tilde{\mathbb E}\left[\frac{S_{t+1}}{S_t} \frac{S_t}{B_{t+1}}  \mid \mathcal G_t \right]=\frac{S_t}{B_{t+1}} \,\tilde{\mathbb E}\left[\frac{S_{t+1}}{S_t}   \mid \mathcal G_t \right]
\\
\end{split}
$$

* Under the risk-neutral measure above, we know that
$$
\tilde{\mathbb E}[S_{t+1}/S_t\mid \mathcal G_t] = \tilde{\mathbb E}[S_{t+1}\mid \mathcal G_t]/S_t = \tilde p \, u + (1-\tilde p)\,d = 1 + r
$$

* We conclude
$$
\begin{split}
\tilde{\mathbb E}\left[S_{t+1}/B_{t+1} \mid \mathcal G_t \right] =  \frac{S_t}{B_{t+1}} \,(1+r) = S_t / B_t
\\
\end{split}
$$

---

## Self-financing Strategies, Risk Neutral Probability Measure and Martingales

* **Definition** Self-financed portfolio $\Pi$: rebalanced at any time using only past capital gains/
  * Let $\Delta_t$ be the amount invested at time $t$ in a stock $S_t$
  * A self-financed portfolio invests the remainder $\Pi_t - \Delta_t\,S_t$ in the bank account
  * The value of the portfolio $\Pi$ at $t+1$ is
  $$
  \Pi_{t+1} = \Delta_t S_{t+1} + (\Pi_t - \Delta_t\,S_t)\,(1+r)
  $$

* **Exercise**: show that the discounted self-financed portfolio value process $(\Pi_t/B_t)$ is a martingale under $\tilde P$.

---

## Self-financing, Martingales, and Pricing

* Self-financed portfolios can be used to **hedge** derivatives.
  * If we can fully replicate a contingent claim by means of a self-financed
portfolio we can fully eliminate the risk related to the random payoff

* Consider a *European derivative* with maturity $T$ and payoff $V_T$.
  * It is headgeable is there exists a self-financed portfolio process such that $\Pi_T = V_T$
  * We just need to be able to replicate the payoff !
  * That's what we did in Session $1$

* If the derivative is **hedgeable**, absence of arbitrage 
implies that its price is the value of the hedging portfolio

---

## Risk-neutral valuation formula

* Let $V_T$ be the payoff of a European derivative.

* The risk-neutral valuation formula is
$$
V_t = \frac{B_t}{B_T}\,\tilde{\mathbb E}[V_T \mid \mathcal G_t] = \frac{1}{(1+r)^T-t}\,\tilde{\mathbb E}[V_T \mid \mathcal G_t]
$$

* **Theorem**: A risk-neutral probability measure  exists *if and only if* there are no arbitrage opportunities

* **Definition**: The market is **complete** if every contingent claim is hedgeable


---
layout: end
---
Thank you !

[faycaldrissi.com](https://www.faycaldrissi.com/)

---
layout: intro
---
## Session $3$: Introduction to Stochastic Processes
<br />
<br />

*Fayçal Drissi*

*Saïd Business School, University of Oxford*


---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Stochastic Processes <a name="defi"></a></h1>
</p>

---

## Stochastic Processes: from discrete to continuous


* In discrete-time, we have dates $t\in\{0,\dots,T\}$ 
  * A stochastic process $X$ at time $t$ is $X_t$
  * The change in value of $X$ between $t$ and $t-1$ is $\Delta X_t = X_t - X_{t-1}$
  * The change in value of $X$ between $0$ and $t$ is the sum of changes through the path:
  $$
  X_t - X_0 = \sum_{s=1}^t \Delta X_s
  $$

---

## Stochastic Processes: from discrete to continuous


* In continuous-time, time lives in an interval $[0, T]$.
  * A stochastic process at time $t$ is $X_t$
  * $dX_s$ is the infinitesimal change of $X$ at time $s$
  * The change in value of $X$ between $t$ and $t-1$ is 
  $$X_t - X_0 = \int_{t-1}^{t} dX_s$$
  * In particular, $X_t = \int_0^t dX_s$

---

## Filtration, adapted processes, and martingales

* The concepts of filtration, adapted processes, and martingales extend in a natural way to continuous-time stochastic processes.

  * $(\mathcal G_{t})_{t\in[0, T]}$ is a filtration if for all $t<s$, we have $\mathcal G_{t}\subset\mathcal G_{s}$

  * A stochasic process is adapted to a filtration if at $t\in[0, T]$, the random variable $X_t$ is $\mathcal G_t$-measurable.

  * An adapted process is a martingale if for any $t,s\in[0, T]$ such that $s>t$, the martingale condition is satisfied :
  $$
  X_t = \mathbb E[X_s \mid \mathcal G_t] 
  $$

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Brownian Motion <a name="defi"></a></h1>
</p>

---

## Brownian motions (Wiener processes): definition

* Discrete-time
  * Assume $(Y_t)_{t\in\{0,\dots,T\}}$ is a sequence iid normal variables $\mathcal N(0, 1)$
  * The stochastic process $W_t$ is a discrete-time Brownian motion if
    * $W_0 = 0$
    * $W_t = \sum_{i=1}^t Y_i$
  * **Remark**: $Z_t \sim \mathcal N(0, t)$

---

## Brownian motions (Wiener processes): definition

* Discrete-time
  * Assume $(Y_t)_{t\in\{0,\dots,T\}}$ is a sequence iid normal variables $\mathcal N(0, 1)$
  * The stochastic process $W_t$ is a discrete-time Brownian motion if
    * $W_0 = 0$
    * $W_t = \sum_{i=1}^t Y_i$
  * **Remark**: $Z_t \sim \mathcal N(0, t)$
* Continuous-time:
  * The stochastic process $W_t$ is a discrete-time Brownian motion if
    * $W_0 = 0$
    * Increments are independent, i.e., for $r<s\le t<u$:
    $$
    W(u)-W(t) \quad\text{and}\quad W(s)-W(t) \text{ are inpdendent random variables}
    $$
    * Increments are normally distributed: 
    for an $s>t$
    $$
    W_s - W_t \sim \mathcal N(0, s-t)
    $$
  

---

## Brownian motions (Wiener processes): properties

* Distriution of $W_t$ is $\mathcal N(0,t)$

* **Exercise**: Show that $W$ is a **martingale**. 
  * Let $s>t$, we want to show $\mathbb E[W_s \mid \mathcal G_t] =  W_t$
  $$
    \mathbb E[W_s \mid \mathcal G_t] = \mathbb E[W_s - W_t + W_t \mid \mathcal G_t] = \mathbb E[W_s - W_t \mid \mathcal G_t] + W_t = W_t
  $$

* **Exercise**: Show that $W_t^2 - t$ is a martingale
$$
\begin{split}
\mathbb E(W_s^2|\mathcal{G}_t)&=\mathbb E((W_s-W_t+W_t)^2|\mathcal{G}_t)\\&=\mathbb E((W_s-W_t)^2|G_t)+\mathbb E(W_t^2|G_t)+\mathbb E(2(W_s-W_t)W_t|G_t)\\&=\mathbb E((W_s-W_t)^2)+W_t^2+2W_t\mathbb E(W_s-W_t|G_t)\\&=(s-t)+W_t^2+2W_t\mathbb E(W_s-W_t)\\&=(s-t)+W_t^2
\end{split}
$$



---

## Brownian motions (Wiener processes): properties

* **Exercise**: show that $\exp\left(\sigma W_t - \sigma^2 t/2\right)$ is a martingale. **Hint**: for a Gassian random variable $X$ with mean zero and variance $\xi^2$, the moment generating function is
  $$
  \mathbb E[\exp(X_t)] = \exp(\xi^2/2)
  $$
  * We want to show, for $s>t$, that
  $$E[\mathbb \exp\left(\sigma W_s - \sigma^2 s/2\right) \mid \mathcal G_t] = \exp\left(\sigma W_t - \sigma^2 t/2\right)$$ 
  * We show this with the usual trick: break down the path of $W$, and use the properties of Brownian motion
  $$
  \begin{split}
  \mathbb E[\mathbb \exp\left(\sigma W_s - \sigma^2 s/2\right) \mid \mathcal G_t] =  
  & \mathbb E[\exp\left(\sigma (W_s-W_t+W_t) - \sigma^2 s/2\right) \mid \mathcal G_t] \\
  = &\exp\left( - \sigma^2 s/2\right)\mathbb E[\exp\left(\sigma \, W_t\right)\exp\left(\sigma (W_s-W_t)\right) \mid \mathcal G_t] \\
  = &\exp\left( - \sigma^2 s/2\right)\mathbb E[\exp\left(\sigma \, W_t\right) \mid \mathcal G_t]\mathbb E[\exp\left(\sigma (W_s-W_t)\right) \mid \mathcal G_t] \\
  = & \exp\left(\sigma W_t -\sigma^2 s/2\right) \exp\left( \sigma^2 (s-t)/2\right)\\
  = & \exp\left(\sigma W_t - \sigma^2 t/2\right)
  \end{split}
  $$

---

## Brownian motions (Wiener processes): properties

* **Exercise**:  For $s>t$, compute $Cov(Z_t, Z_s)$

$$
\begin{split}
Cov(Z_t, Z_s) = & \mathbb E[Z_t Z_s] - \mathbb E[Z_t]\mathbb E[Z_s] \\
= & \mathbb E[Z_t (Z_s - Z_t + Z_t)] \\
= & \mathbb E[Z_t (Z_s - Z_t)] + \mathbb E[Z_t^2]\\
= & \mathbb E[Z_t]\mathbb E[Z_s - Z_t] + \mathbb E[Z_t^2]\\
= & t
\end{split}
$$


---

## History of Brownian motions

* **1827**: named after the Scottish botanist Robert Brown, who described the phenomenon  while looking through a microscope at pollen in water
* **1900**: French mathematician Louis Bachelier modeled the stochastic process now called Brownian motion in his doctoral thesis: The Theory of Speculation (under Henri Poincaré)
* **1905**:  theoretical physicist Albert Einstein published a paper where he modeled the motion of the pollen particles as being moved by individual water molecules
* **Recently**: it is at the core of most financial models, whether we consider
stocks, interest rates or currencies

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Ito Process <a name="defi"></a></h1>
</p>

---

## Stock prices in continuous-time: the Ito process
* Let $W_t$ be a Brownian motion over $[0, T]$, and let $\mathcal G_t$ be the filtration generated by $W_t$
* Let $S_t$ denote the stock price. The **dynamics** of the price are
  $$
  dS_t = \mu\,dt + \sigma\,dW_t
  $$
  * $\mu\in\mathbb R$ is the **drift**
  * $\sigma>0$ is the **volatility**
* Let $B_t$ denote the bond price. The **dynamics** are
  $$
  dB_t = r\,dt
  $$
  * $r>0$ is the **risk-free rate**


---

## Stock prices in continuous-time: the Ito process

* We can simulate Brownian motions ...
  * We **discretise** the dynamics
$$
  dS_t = \mu\,dt + \sigma\,dW_t
$$

* With/without drift 
![brownianmunon0](./images/brownianmunon0.png){style="transform: translate(20%, 0%); width: 600px"}

---

## Stock prices in continuous-time: the Ito process

* We can simulate Brownian motions ...
  * We **discretise** the dynamics
$$
  dS_t = \mu\,dt + \sigma\,dW_t
$$

* with more/less volatility
![brownianmu0](./images/brownianmu0.png){style="transform: translate(20%, 0%); width: 600px"}

---

## Stock prices in continuous-time: the Ito process

* We can estimate from real data with a simple OLS regression
  * We **discretise** the dynamics
$$
  dS_t = \mu\,dt + \sigma\,dW_t
$$

-- PLOT --

* This is the physical measure

---

## Geometric Brownian Motion and Ito Process

* We also use the Geometric Brownian Motion (GBM) with dynamics (SDE)
  $$
    dS_t = \mu\,S_t\,dt + \sigma\,S_t\,dW_t
  $$
  * $\mu$ is a *percentage* drift
  * $\sigma$ is a *percentage* volatility

* The geometric bank account: $dB_t =r \, B_t \,dt \implies B_t =\exp(r\,t)$

* The GBM is a special case of an Ito process
$$
dX_t = \mu(t,X_t)\,dt + \sigma(t,X_t)\,dW_t
$$
for well-behaved (we will see later) functions $\mu$ and $\sigma$.

* Integrating, we get an equivalent representation of the SDE
$$
S_t = S_0 + \int_0^t \mu(u,X_u)\,du + \int_0^t \sigma(u,X_u)\,S_u\,dW_u
$$

---

## Ito Process

* Ito processes and Ito calculus: named after Kiyoshi It\^o (1915 - 2008, University of Kyoto)

* Ito extended the methods of calculus to stochastic processes such as Brownian motion
* Ito calculus has important applications in mathematical finance and stochastic differential equations


---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Stochastic Integral <a name="defi"></a></h1>
</p>

---

## Stochastic integrals: motivation

* The Geometric Brownian Motion (GBM) follows the SDE
$$
  dS_t = \mu\,S_t\,dt + \sigma\,S_t\,dW_t
$$


* Naive solution: 
  * notice that 
  $$d\log(S_t) = \mu\,dt + \sigma\,dW_t$$ 
  * so
  $$
  \log(S_t) = \log(S_0) + \mu\,t + \sigma\,W_t \implies S_t = S_0\,\exp(\mu\,t + \sigma\,W_t)
  $$

* That is **wrong** !! The true solution to the SDE is 
$$
S_t = S_0 \, \exp\left(\left(\mu-\sigma^2/2\right)\,t + \sigma\,W_t\right)
$$

* Where does the extra term comes from ? Ito's lemma.


---

## Stochastic integrals: motivation

* Let $\Pi$ be a self-financed portfolio that invests $\Delta_t$ units in the stock at time $t$.

* The dynamics of $\Pi$ are
$$
\begin{split}
d\Pi_t &= \Delta_t\, dS_t + (\Pi_t - \Delta_t S_t)\, dB_t
\end{split}
$$



* When the stock dynamics are GBM
$$
dS_t/S_t = \mu\,dt + \sigma\,dW_t
$$
then the self-financed portfolio has dynamics modelled by the SDE
$$
\begin{split}
d\Pi_t &=\Delta_t\, (\mu - r)\,S_t\,dt+\sigma\,\Delta_t\,S_t\,dW_t  +r\,\Pi_t\, dt
\end{split}
$$

* To compute the variation $\Pi_T - \Pi_0$ of the portfolio value, we need the stochastic integral
$$
\begin{split}
\Pi_T - \Pi_0 &=\int_0^T \Delta_t\, (\mu - r)\,S_t\,dt+\sigma\,\int_0^T\Delta_t\,S_t\,dW_t  +r\,\int_0^T\Pi_t\, dt
\end{split}
$$

---

# The stochastic integral

* We need to study the *stochastic integral*
$$
\int_0^t S_u\,dW_u
$$
* When a function F is differentiable, we can define the Lebesgue integral 
$$
\int_0^t \Delta_s\,dF(s) = \int_0^t \Delta_s\,F'(s) ds
$$
* This does not apply to Brownian motions, because Brownian paths are *not differentiable* at any point.
* To see this: imagine a particle moving around on some trajectory
  * Its trajectory being continuous means that as you slow time down, the particle stays closer and closer to where it was (no big jumps)
  * Its trajectory being differentiable means that as you slow time down, the particle doesn't just stay near where it was, it moves more and more in a straight line: not the case for a Brownian motion

---

# The stochastic integral

* We need to define integrals with respect to Brownian motions

* Let $\mathcal T = \{t_0, t_1, \dots, t_n\}$ be a partition of the time interval $[0, T]$, i.e.,
$$
0=t_0<t_1<\dots<t_n=T
$$

* Assume $\Delta_t$ is a *simple process*, i.e., a piecewise constant process over each subinterval $[t_i, t_{i+1})$     
![simpleProcess](./images/simpleProcess.png){style="transform: translate(60%, 0%); width: 400px"}

---

# The stochastic integral

![simpleProcess2](./images/simpleProcess2.png){style="transform: translate(120%, 0%); width: 250px"}

* Think of the Brownian $W_t$ as the price of an asset. 
* Think of the dates  $\mathcal T = \{t_0, t_1, \dots, t_n\}$ as trading or rebalancing dates.
* Think of $\{\Delta(t_0),\Delta(t_1),\dots,\Delta(t_n)\}$ as the position in the asset at each date.
  * At time $t\in[t_0, t_1)$, the gain from trading the strategy $\Delta$ is $I_t = \Delta_{t_0} (W_t - W_{t_0})$
  * at time $t\in[t_1, t_2)$:   $\quad \quad\quad  I_t = \Delta_{t_0} (W_t - W_{t_0})+\Delta(t_1) (W_t - W_{t_1})$
  * at time $t\in[t_{k}, t_{k+1})$: $\quad \quad I_t =\sum_{j=0}^{k-1} \Delta_{t_j} (W_{t_{j+1}} - W_{t_j})+\Delta_{t_{k}} (W_t - W_{t_{k+1}})$
* The stochastic integral can be seen as the gain from holding the positions $\Delta_t$ in the stock 
$$I_t = \int_0^t \Delta_s \, dW_s = \sum_{j=0}^{k-1} \Delta_{t_j} (W_{t_{j+1}} - W_{t_j})$$

---

# The stochastic integral is a martingale

* **Theorem 1: The stochastic integral I_t is a martingale**
  * Exercise: prove it when $I_{t_k} = \sum_{j=0}^{k-1} \Delta_{t_j} (W_{t_{j+1}} - W_{t_j})$
  $$
  \begin{split}
  \mathbb E[I_{t_{k+1}}\mid \mathcal G_{t_{k}}] = \mathbb E[I_{t_{k}} + \Delta_{t_k} (W_{t_{k+1}} - W_{t_k}) \mid \mathcal G_{t_{k}}] = I_{t_{k}}.
  \end{split}
  $$
  * Since $I_t$ is a martingale, and $I_0=0$, then $\mathbb E_0[I_t] = 0$

---

# Ito's isometry

* **Theorem 2: Ito's isometry:**
$$
\mathbb E[I_t^2] = \mathbb E\left[\int_0^t \Delta_u^2 \, du\right]= \int_0^t \mathbb E\left[\Delta_u^2\right] \, du
$$

* **Exercise**: prove it in the case of the simple piecewise-constant process


---

# Ito's isometry
* To prove it, we write
$$
\begin{split}
\mathbb E[I_{t_k}^2] = & \mathbb E\left[\left(\sum_{j=0}^{k-1} \Delta_{t_j} (W_{t_{j+1}} - W_{t_j}) \right)^2\right]\\ 
\end{split}
$$
* By definition, if $k\ne \kappa$, then $(W_{t_{k+1}} - W_{t_k})$ and $(W_{t_{\kappa+1}} - W_{t_\kappa})$ are independent with mean zero
* Thus 
$$\mathbb E[(W_{t_{k+1}} - W_{t_k})(W_{t_{\kappa+1}} - W_{t_\kappa})] = 0$$
* Moreover, we know that for all $k$, 
$$\mathbb E\left[(W_{t_{k+1}} - W_{t_k})^2\right] = (t_{k+1}-t_k)$$  
* We conclude 
$$
\begin{split}
\mathbb E[I_{t_k}^2] = & \mathbb E\left[\sum_{j=0}^{k-1} \Delta_{t_j}^2 (W_{t_{j+1}} - W_{t_j})^2 \right]\\ 
\end{split}
$$

---

# The stochastic integral in the general case

* We can define the stochastic integral $\int_0^t \Delta_t dW_t$ for any general integrand $\Delta_t$
* $\Delta_t$ can have vary continuously and also jump..
* In order to guarantee the existence of the stochastic integral, we only require the process $\Delta_t$ to be square integrable, i.e., we require that 
$$
\mathbb E\left[\int_0^t \Delta_s^2\, ds\right] < \infty
$$

* The class of square integrable processes is denote $\mathcal L^2$ and is almost always used.

* To prove the theorems above for any process $\Delta_t$
  * First, we approximate $\Delta_t$ with a simple process $\Delta_t^n$, i.e., $\lim_{n\rightarrow\infty}\left|\Delta_t^n-\Delta_t\right|=0$
  * The stochastic integral for $\Delta_t$ is 
  $$\int_0^t\Delta_s\,dW_s = \lim_{n\rightarrow\infty}\int_0^t\Delta^n_s\,dW_s$$

---

# The stochastic integral: properties

* **Continuity**: the paths of the stochastic integral $\int_0^t\Delta_s\,dW_s$ are continuous in $t$

* **Adaptivity**: $I_t$ is $\mathcal G_t$-measurable

* **Linearity**: 
$$
\int_0^t(\Delta_s+\Gamma_s)\,dW_s = \int_0^t\Delta_s\,dW_s+\int_0^t\Gamma_s\,dW_s
$$

* **Martingality**
$$
\mathbb E[I_t] = 0
$$

* **Ito Isometry**
$$
\mathbb E[I_t^2] = \int_0^t \Delta_t^2\,dt
$$



---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Ito's Lemma <a name="defi"></a></h1>
</p>

---

# Ito's Lemma

* We introduce a differential calculus for differentiable functions of
stochastic integrals
* The main tool of Ito's calculus is **Ito's lemma**
* We need to differentiate functions of the type:
$
t \mapsto f(W_t)
$
for some twice continuous differentiable function $f$. 
* For instance $f(t, x) = x^2$. What are the dynamics of $f(t, W_t)$, or $W_t^2$ ?
* If we use the chain rule from ordinary calculus we write 
$$
dW_t^2 / dt = 2\,W_t\,dW_t/dt \implies dW_t^2 = 2 \, W_t \,dW_t
$$
or in integral form: $W_t^2 = 2\,\int_0^t W_t dW_t$
* There are inconsistencies
  * This implies that $W_t^2$ is differentiable: we know it's not
  * The RHS is a martingale, and $W_t^2$ is not ($W_t^2 - t$ is a martingale)
* There is an extra term due to **nonzero quadratic variation** of the Brownian motion !!

---

# Ito's Lemma: derivation

* Before deriving Ito's lemma, let's recall some properties 
$$
\begin{split}
\mathbb E[\Delta W] =&  0\\ 
\mathbb E[(\Delta W)^2] =&  \Delta t \\ 
\end{split}
$$

* Intuition: $(\Delta W)^2$ goes to zero as fast as $\Delta t$ when $\Delta t \rightarrow 0$ 

* Now, assume $f$ is twice differentiable scalar function, its Taylor expansion in $t$ is
$$
\begin{split}
\frac{\Delta f(t)}{dt}dt
&= f(t+dt, x) - f(t,x) = \frac{\partial f}{\partial t}\,dt + \frac{1}{2}\frac{\partial^2 f}{\partial t^2}\,(dt)^2 + \cdots \\
\frac{\Delta f(x)}{dx}dx
&= f(t, x+dx) - f(t,x) = \frac{\partial f}{\partial x}\,dx + \frac{1}{2}\frac{\partial^2 f}{\partial x^2}\,(dx)^2 + \cdots
\end{split}
$$

---

# Ito's Lemma: derivation

* By definition of partial derivative:
$$
f_t(t, x) = \lim_{dt\rightarrow 0} \frac{f(t+dt, x) - f(t,x)}{dt}, \quad f_x(t, x) = \lim_{dx\rightarrow 0} \frac{f(t, x+dx) - f(t,x)}{dx}
$$

* By definition (total derivative)
$$
df(t, x) = f_t(t, x) dt + f_x(t, x) dx
$$

* Substituting $x=B_t$, we have 
$$
\begin{split}
df = \lim_{dB_t \to 0 \atop dt \to 0} \;
&  \frac{\partial f}{\partial t}\,dt
 + \frac{\partial f}{\partial x} dB_t + \frac{1}{2} \left[
       \frac{\partial^2 f}{\partial t^2}\,{\left(dt\right)}^2
     + \frac{\partial^2 f}{\partial x^2} {\left(dB_t\right)}^2 
\right] + \cdots.
\end{split}
$$

* In the limit, the terms $dt^2$ and $dt\,dB_t$ go to zero faster than $dt$. However, the term $dB_t^2$ goes to zero as fast as $dt$ (quadratic variation)
$$
\begin{split}
df = \frac{\partial f}{\partial t}\,dt
 + \frac{\partial f}{\partial x} dB_t + \frac{1}{2} \left[\frac{\partial^2 f}{\partial x^2} dt 
\right] + O(dt^2).
\end{split}
$$

---

# Ito's Lemma

Let $f(t, x)$ be a function for which the partial derivatives $f_t(t,x)$, $f_x(t,x)$, and  $f_{xx}(t,x)$ are defined and continuous, and let $W_t$ be a Brownian motion. Then, the dynamics of $f(t, W_t)$ are defined by the SDE
$$
df(t, W_t) = \left(f_t(t, W_t)+ \frac12 f_{xx}(t, W_t) \right)\,dt + f_x(t, W_t)\,dW_t 
$$

* In integral form:
$$
f(t, W_t) = f(0, W_0) + \int_0^t (f_t(s, W_s)+\frac12 f_{xx}(s, W_s))\,ds + \int_0^t f_x(s, W_s)\,dW_s
$$

---

# Ito's Lemma: mnemonic device

We can use simple mnemonic device to Ito's lemma

1. For a function $f(t, W_t)$, we first use the rules of calculus to write the Taylor differential 
$$
df(t, W_t) = f_t(t, W_t) dt + f_x(t, W_t) dW_t + \frac12 f_{tt}(t, W_t) (dt)^2 + \frac12 f_{xx}(t, W_t) (dW_t)^2 + f_{tx}(t, W_t)\, dt\, dW_t
$$

2. Use the multiplication rule

![ItoTable](./images/ItoTable.png){style="transform: translate(180%, 0%); width: 200px"}


$$
df(t, W_t) = f_t(t, W_t) dt + f_x(t, W_t) dW_t + \frac12 f_{xx}(t, W_t) dt
$$


---

# Ito's Lemma

* We can extent Ito's formula to Ito processes of the form
$$
dX_t = \mu(t,X_t)\,dt + \sigma(t,X_t)\,dW_t
$$

* We use the same mnemonic device :
  1. We use normal calculus
  $$
  df(t, X_t) = f_t(t, X_t) dt + f_x(t, X_t) dX_t + \frac12 f_{tt}(t, X_t) (dt)^2 + \frac12 f_{xx}(t, X_t) (dX_t)^2 + f_{tx}(t, W_t)\, dt\, dX_t
  $$

  2. All the terms but $(dX_t)^2$ are zero. The term $(dX_t)^2$ can be written as  (using the multiplication table above)
  $$\mu(t,X_t)^2\,dt^2 + \sigma(t,X_t)^2\,dW_t^2 + 2\,\mu(t,X_t)\,\sigma(t,X_t)\,dt \,dW_t = \sigma(t,X_t)^2\,dt$$

  3. We obtain 
  $$
  df(t, X_t) = \left(f_t(t, X_t) + f_x(t, X_t)\, \mu(t,X_t) + \frac12 f_{xx}(t, X_t) \sigma(t,X_t)^2 \right)dt + f_x(t, X_t) dW_t 
  $$


---

# Ito's Lemma for Geometric Brownian Motion

* Recall the GBM
$$
  dS_t = \mu\,S_t\,dt + \sigma\,S_t\,dW_t
$$

* Consider the function 
$$ 
f(S_t) = \log(S_t)
$$

* Using Ito's Lemma, prove that
$$
S_t = S_0 \, \exp\left(\left(\mu-\sigma^2/2\right)\,t + \sigma\,W_t\right)
$$


---

# Ito's Lemma: exercise

* Recall the GBM
$$
  dS_t = \mu\,S_t\,dt + \sigma\,S_t\,dW_t
$$

* Consider the function 
$$ 
X_t = f(S_t) = S_t^2
$$

* Write the dynamics of $X_t$

---

# Ito's Lemma: exercise

* Let $Y_t$ be the GBPUSD exchange rate (number of USD per GBP)

* We assume the dynamics
$$
dY_t = \mu^Y \, Y_t \, dt + \sigma^Y\,Y_t\,dW_t
$$

* Let $U_t = 1/Y_t$ be the USDGBP exchange rate. Write the dynamics of $U$.

* Express $U_t$ as a function of $U_0$, $t$, and $W_t$. 

* Compute the expectation of $U_t$.

---
layout: end
---
Thank you !

[faycaldrissi.com](https://www.faycaldrissi.com/)

---
layout: intro
---
## Session $4$: The Black-Scholes Model
<br />
<br />

*Fayçal Drissi*

*Saïd Business School, University of Oxford*

---

# Outline

1. Some famous Ito processes
2. The Black-Scholes PDE
3. Multi-dimensional Ito's Lemma

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Some Ito processes <a name="defi"></a></h1>
</p>

---

# Stochastic drift

* Traders sometimes use (adapted) stochastic signals $\alpha_t$ that drive prices
$$
dS_t = \alpha_t \, dt + \sigma\,dW_t
$$

* Example: the imbalance of a limit order book
![imbalance](./images/imbalance2.png){style="transform: translate(180%, 0%); width: 200px"}

---

# Stochastic drift

$$
dS_t = \alpha_t \, dt + \sigma\,dW_t
$$

* Asset prices transition through a number of **regimes**: momentum, mean reversion, and random walks.

![aaplyahoo](./images/aapl_yahoo.png){style="transform: translate(70%, 0%); width: 400px"}

---

# Stochastic drift

$$
dS_t = \alpha_t \, dt + \sigma\,dW_t
$$

* The regimes are observed at different time scales (low, medium, and high frequency).

![aapl_intraday](./images/aapl_intraday.png){style="transform: translate(70%, 0%); width: 400px"}

---

# Stochastic drift

* Assume that a trader buys an asset at speed $\nu_t\,dt$ and that each dollar bought causes the price to move by $\eta$, then a trader would consider the dynamics
$$
dS_t = \eta\,\nu_t\,dt + \sigma\,dW_t
$$

![impact](./images/impact.png){style="transform: translate(70%, 0%); width: 400px"}


---

# Correlated prices

* Some assets are fundamentally correlated because they share the same sources of risk
$$
dS_t = \mu\,dt + \sigma\,dW_t,\quad dP_t = m\,dt + s\,dB_t,
$$
  * The joint distribution of $W_t$ and $B_t$ is $\mathcal N\left(\begin{pmatrix}
0 \\
0 
\end{pmatrix}, t
\begin{pmatrix}
1 & \rho \\
\rho & 1
\end{pmatrix}\right)$

![bnpgle](./images/bnpgle.png){style="transform: translate(20%, 0%); width: 700px"}

---

# Time-dependent volatility

* Volatility has seasonality: less intense at the end than at the start of the day
$$
dS_t = \mu\,dt + \sigma(t)\,dW_t
$$

![volatility_Ushaped](./images/volatility_Ushaped.png){style="transform: translate(70%, 0%); width: 350px"}

* Volatility can also be stochastic (and observable)
$$
dS_t = \mu\,dt + \sigma_t\,dW_t
$$

---
layout: two-cols-header
---

# Mean-reverting processes: Ornstein–Uhlenbeck

* The SDE for an OU process is (or a Viscek model)
  $$
  dS_t = -\theta\,(S_t - \overline S)\,dt + \sigma\,dW_t
  $$
  * $\overline S$: long term mean level
  * $\theta$: speed of mean-reversion
::left::
![OU1](./images/OU1.png){style="transform: translate(0%, 0%); width: 450px"}
::right::
![OU2](./images/OU2.png){style="transform: translate(0%, 0%); width: 450px"}


---

# Mean-reverting processes: Ornstein–Uhlenbeck
#### Solving the Ornstein-Uhlenbeck SDE with Itô's Lemma

* Step 1: the OU process follows:
$
dS_t = -\theta\,(S_t - \overline S)\,dt + \sigma\,dW_t
$
* Step 2: Introduce a transformation (to eliminate the mean-reverting drift)
$$
Y_t = e^{\theta\, t} S_t
$$
* Step 3: Apply Itô's Lemma to $Y_t$
$$
\begin{split}
dY_t = e^{\theta t} dS_t + \theta e^{\theta t} S_t \, dt & = e^{\theta t} \left[ \theta(\overline S - S_t) \, dt + \sigma \, dW_t \right] + \theta e^{\theta t} S_t \, dt \\
& = \theta \overline S e^{\theta t} \, dt + \sigma e^{\theta t} \, dW_t
\end{split}
$$
* Step 4: Integrate from  $0$ to $t$ (note that $Y_0 = X_0$.)
$$
Y_t = Y_0 + \theta \overline S \int_0^t e^{\theta s} \, ds + \sigma \int_0^t e^{\theta s} \, dW_s
$$


---

# Mean-reverting processes: Ornstein–Uhlenbeck
#### Solving the Ornstein-Uhlenbeck SDE with Itô's Lemma
$$
Y_t = Y_0 + \theta \overline S \int_0^t e^{\theta s} \, ds + \sigma \int_0^t e^{\theta s} \, dW_s
$$

* Step 5: Solve for $S_t$ Since $Y_t = e^{\theta t} X_t$, we find:
$$
S_t = e^{-\theta t} \left( S_0 + \theta \overline S \int_0^t e^{\theta s} \, ds + \sigma \int_0^t e^{\theta s} \, dW_s \right)
$$
Using
$$
\int_0^t e^{\theta s} \, ds = \frac{e^{\theta t} - 1}{\theta},
$$
the final solution becomes:
$$
S_t = S_0\,e^{-\theta t} + \overline S(1-e^{-\theta t}) + \sigma\, \int_0^t e^{-\theta (t-s)} \, dW_s
$$

---

# Mean-reverting processes: Ornstein–Uhlenbeck
#### Solving the Ornstein-Uhlenbeck SDE with Itô's Lemma

* The final solution becomes:
$$
S_t = S_0\,e^{-\theta t} + \overline S(1-e^{-\theta t}) + \sigma\, \int_0^t e^{-\theta (t-s)} \, dW_s
$$
* What is the mean and variance of $S_t$ ?
  * Mean
  $$
  \mathbb{E}[S_t] = S_0\,e^{-\theta t} + \overline S(1-e^{-\theta t})
  $$
  * Variance (the variance comes only from the stochastic integral: Ito's isometry)
$$
\text{Var}(X_t) = \sigma^2 e^{-2\theta t} \, \text{Var}\left( \int_0^t e^{\theta s} \, dW_s \right)
$$
By Itô's isometry:
$
\text{Var}(X_t) =  \sigma^2 e^{-2\theta t} \mathbb{E}\left[ \left( \int_0^t e^{\theta s} \, dW_s \right)^2 \right] =  \sigma^2 e^{-2\theta t}\int_0^t e^{2\theta s} \, ds= \frac{\sigma^2}{2\theta} \left( 1 - e^{-2\theta t} \right)
$

---

# Mean-reverting processes: Ornstein–Uhlenbeck

* OU processes are more appropriate for Foreign Exchange and Bond markets

* Assume two identical options written on a stock and one on EURJPY:
  * Which one is more expensive ?


---

# Cox–Ingersoll–Ross (CIR) model for interest rates

* The CIR process follows the SDE:
$
\quad\quad dR_t = \theta (\mu - R_t) \, dt + \sigma \sqrt{R_t} \, dW_t
$
* **Mean Reversion**: The process reverts to the long-term mean $\mu$ at a rate $\theta$
* **Level-Dependent Volatility**: The volatility of the process depends on the level of $R_t$, proportional to $\sqrt{R_t}$. As $R_t$ approaches zero, the volatility decreases and only the deterministic term drives the dynamics
* **Non-Negativity**: The process is never negative if $\theta > 0$, $\mu > 0$, and $\sigma > 0$. 
  * It never touches zero if $2\theta\mu>\sigma^2$
  * the CIR model is suitable for modeling processes like interest rates
![rates1](./images/rates1.png){style="transform: translate(70%, 0%); width: 380px"}

---

# Cox–Ingersoll–Ross (CIR) model for interest rates

#### Solving the CIR SDE with Itô's Lemma

* Step 1: The CIR process follows:
$
dR_t = \theta (\mu - R_t) \, dt + \sigma \sqrt{R_t} \, dW_t
$
* Step 2: Introduce the transformation:
$
Y_t = e^{\theta t} R_t
$
* Step 3: Apply Itô’s Lemma to $Y_t$:
$$
dY_t = e^{\theta t} dR_t + \theta e^{\theta t} R_t \, dt
$$
Simplifying:
$$
dY_t = \theta \mu e^{\theta t} \, dt + \sigma e^{\theta t} \sqrt{R_t} \, dW_t
$$



---

# Cox–Ingersoll–Ross (CIR) model for interest rates

#### Solving the CIR SDE with Itô's Lemma


* Step 4: Integrate from $0$ to $t$ (note that $Y_0 = e^{\theta 0} R_0 = R_0$):
$$
Y_t = Y_0 + \int_0^t \theta \mu e^{\theta s} \, ds + \int_0^t \sigma e^{\theta s} \sqrt{R_s} \, dW_s
$$
* Step 5: Solve for $R_t$. Since $Y_t = e^{\theta t} R_t$, we obtain:
$$
R_t = e^{-\theta t} \left( Y_0 + \int_0^t \theta \mu e^{\theta s} \, ds + \int_0^t \sigma e^{\theta s} \sqrt{R_s} \, dW_s \right)
$$

Using $Y_0 = R_0$, the final solution becomes:
$$
R_t = R_0 e^{-\theta t} + \mu \left( 1 - e^{-\theta t} \right) + \sigma \int_0^t e^{-\theta (t-s)} \sqrt{R_s} \, dW_s
$$

---

# Cox–Ingersoll–Ross (CIR) model for interest rates
#### Mean and Variance of $R_t$

* **Mean**: The mean of $R_t$ is given by:
$$
\mathbb{E}[R_t] = R_0 e^{-\theta t} + \mu \left( 1 - e^{-\theta t} \right)
$$

* **Variance**: The variance of $R_t$ is derived from the stochastic integral. Using Itô's isometry:
$$
\begin{split}
\text{Var}(R_{t})=&\sigma^{2}\,e^{-2\theta\,t}\text{Var}\left(\int_{0}^{t}e^{\theta s}\sqrt{R_{s}}\,dW_{s}\right)\\=&\sigma^{2}\,e^{-2\theta\,t}\mathbb{E}\left[\int_{0}^{t}e^{2\,\theta s}R_{s}\,ds\right]\\=&\sigma^{2}\,e^{-2\theta\,t}\int_{0}^{t}e^{2\,\theta s}\left(R_{0}e^{-\theta s}+\mu\left(1-e^{-\theta s}\right)\right)\,ds\\=&R_{0}\frac{\sigma^{2}}{\theta}\,\left(e^{-\theta\,t}-e^{-2\theta\,t}\right)+\frac{\mu\,\sigma^{2}}{2\,\theta}\,\left(1-e^{-\theta\,t}\right)^{2}
\end{split}
$$

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Black-Scholes model <a name="defi"></a></h1>
</p>

---


# The Black-Scholes model: history

* Only Nobel Prize (1997) for Mathematical Finance (for Robert Mertin and Myron Scholes. Fischer Black died in 1995 so he was ineligible)
* Based on Louis Bachelier and Paul Samuelson work
* Simple model but at the core of all pricing models, and trillions of dollars traded each year

---

# The Black-Scholes model

* Assume an asset's price follows GBM dynamics
$$
dS_t = \mu\,S_t\,dt + \sigma\,S_t\,dW_t
$$

* We want to price a European-style option with payoff $V(S_T, T)$
  * The payoff depends on the terminal time $T$ and the value of the asset price $S_T$ at this terminal time.
  * If we can replicated the dynamics of the option price with thoses of a self-financed portfolio, then both investment options have the same price.


---

# The Black-Scholes model

* Denote by $V_t = V(t, S_t)$ the price of the derivative at time $t \in[0, T]$

* Use Ito to derive the dynamics of the price of the derivative
$$
\begin{split}
dV_t & = V_t(t, S_t) \, dt + V_s(t, S_t)\,dS_t + \frac12 \, V_{SS}(t, S_t)(dS_t)^2 \\
& = \left[V_t(t, S_t) + \mu\,S_t\,V_s(t, S_t) + \frac12 \sigma^2\,S_t^2\,V_{SS}(t, S_t)  \right]\,dt + \sigma \, S_t \, V_s(t, S_t)\,dW_t
\end{split}
$$

---

# The Black-Scholes model

* Now assume a general self-financed portfolio $\Pi_t$ which holds
  * $\Delta_t$ units of the stock at time $t$
  * invests the rest $\Pi_t - \Delta_t\,S_t$ in a money markets account yielding a constant interest rate $r$
* The dynamics of the self-financed portfolio are
$$
\begin{split}
d\Pi_t&  = \Delta_t \, dS_t + r\,(X_t - \Delta_t\,S_t)dt \\
& = \Delta_t \, (\mu\,S_t\,dt + \sigma\,S_t\,dW_t) + r\,(X_t - \Delta_t\,S_t)dt \\
& = r\,\Pi_t\,dt + \Delta_t(\mu-r)S_t\,dt + \Delta_t\,\sigma\,S_t\,dW_t
\end{split}
$$
* Breakdown of the portfolio dynamics
  * $r\,\Pi_t\,dt:$ average risk-free return $r$ on the portfolio
  * $\Delta_t(\mu-r)S_t\,dt:$ a risk premium $\mu-r$ for investing in the stock, i.e., buying or selling $\Delta_t$ units.
  * $\Delta_t\,\sigma\,S_t\,dW_t:$ volatility term proportional to the size of the stock investment.
* **Exercise**: what is the variance of $\Pi_t$

---

# The Black-Scholes model

* Our goal is to replicate (hedge) the European derivative. We want
$$
\Pi_t = V(t, S_t) \text{ for all } t \in[0,T]
$$

* The dynamics of the option price are
$$
d\Pi_t = \left[r\,\Pi_t + \Delta_t(\mu-r)S_t \right]\,dt + \Delta_t\,\sigma\,S_t\,dW_t
$$

* The dynamics of the self-financed portfolio are
$$
dV_t = \left[V_t(t, S_t) + \mu\,S_t\,V_s(t, S_t) + \frac12\sigma^2\,S_t^2\, V_{SS}(t, S_t)  \right]\,dt + \sigma \, S_t \, V_s(t, S_t)\,dW_t
$$


---

# The Black-Scholes model

* The dynamics are
$$
\begin{cases}
d\Pi_t & = \left[r\,\Pi_t + \Delta_t(\mu-r)S_t \right]\,dt + \Delta_t\,\sigma\,S_t\,dW_t \\
dV_t & = \left[V_t(t, S_t) + \mu\,S_t\,V_s(t, S_t) + \frac12 \sigma^2\,S_t^2\,V_{SS}(t, S_t)  \right]\,dt + \sigma \, S_t \, V_s(t, S_t)\,dW_t
\end{cases}
$$

* To eliminate risk, we need 
$$
\boxed{\Delta_t = V_s(t, S_t)}
$$

* This is called delta-heding ! 

* The sensitivity of price options to time, price, volatility, etc are called Greeks.
  * $V_s(t, S_t)$ is called the Delta of the option
  * $V_{ss}(t, S_t)$ is called the Gamma of the option
  * $V_{t}(t, S_t)$ is called the Theta of the option

--- 


# The Black-Scholes model

* The dynamics are
$$
\begin{cases}
d\Pi_t & = \left[r\,\Pi_t + \Delta_t(\mu-r)S_t \right]\,dt + \Delta_t\,\sigma\,S_t\,dW_t \\
dV_t & = \left[V_t(t, S_t) + \mu\,S_t\,V_s(t, S_t) + \frac12 \sigma^2\,S_t^2\,V_{SS}(t, S_t)  \right]\,dt + \sigma \, S_t \, V_s(t, S_t)\,dW_t
\end{cases}
$$

* We insert the delta-hedging formula into the dynamics, and we obtain the **Black-Scholes PDE**
$$
\boxed{V_t(t, S_t) + r\,S_t\,V_s(t, S_t) + \frac12 \sigma^2\,S_t^2\,V_{SS}(t, S_t) = r\,V(t, S_t)}
$$
for all $t\in[0, T]$, subject to boundary condition
$$
V_T = V(T, S_T)
$$


--- 

# Solving the Black-Scholes model 

* Let's solve the Black-Scholes model for a European Call with strike $K$
$$
V(S_T, T) = (S_T - K)^+
$$

* The option's price is 
$$
V_t = S_t \, \mathcal N(d_1) - K \,\exp(-r(T-t))\,\mathcal N(d_2)
$$
where
$$
d_1 = \frac{\log(S_t/K) + (r+\sigma^2/2)(T-t)}{\sigma\sqrt{T-t}}, \quad \text{and } \quad d_2 =  d_1 - \sigma\sqrt{T-t}
$$

* $\mathcal N$ is the standard normal distribution's CDF: 
$$\mathcal N(x) = \frac{1}{\sqrt{2\,\pi}}\int_{-\infty}^x e^{-y^2/2}\,dy.$$

---

# Solving the Black-Scholes model 

* Use the following change of variables
$$
\begin{split}
\tau & = T - t \\
x & = \log(S_t/K) + (r - \sigma^2/2)\tau \\
u(\tau, x)&  = V(t, S_t)\,e^{r(T-t)}
\end{split}
$$

* The Black-Scholes PDE reduces to a *Heat Equation* with initial condition $u(0,x)=K\,(e^{x^+} - 1)$
$$
\partial_t u = \sigma^2\, \partial_{xx}u / 2,
$$


* This has solution 
$$
u(\tau, x) = \frac{1}{\sigma\sqrt{2\,\pi\,\tau}}\int_{-\infty}^\infty u(0,y)\,e^{-\frac{(x-y)^2}{2\sigma^2\tau}}dy
$$
* With some manipulations, we arrive at the solution.
* We will prove this when we do risk-neutral pricing !

--- 

# Black-Scholes model: Observations

* The solution does not depend on the expected return $\mu$ !
  * Drift can be replaced by the risk-free rate through a mathematical construct called risk-neutral probability pricing. 
  * Why can we get away with that without introducing errors? The reason lies in the ability to setup a hedge portfolio, thus the market will not compensate us for the drift above and beyond the risk free rate under risk-neutral probability pricing.

* to make it even simpler think of a call with a zero strike on the underlying. How would you price such a call? Well, you would price it like the stock (up to a correction for the risk free interest rate)! Here the same question could be asked: Shouldn't it be priced higher with the underlying having higher drift? The answer is no, because this is already included in the price of the underlying! You would kind of double count this effect.

With "real" options the reason is the same, the only thing that changes is that you have to adapt the proportion of the stock when the price of the underlying changes. But the original reasoning stays the same: The drift does not enter into the price of the derivative because it is already included in the price of the underlying.

--- 

# Black-Scholes model: Observations

$$
\boxed{V_t(t, S_t) + r\,S_t\,V_s(t, S_t) + \frac12 V_{SS}(t, S_t) = r\,V(t, S_t)}
$$

* How general is the B\&S equation above ? 
  * we assumed no arbitrage
  * we assumed ability to borrow and lend any amount, even fractional, of cash at the risk-free rate $r$
  * we assumed ability to buy and sell any amount, even fractional, of the stock
  * we assumed no frictions when buying and selling
  * we assumed short-selling without costs

* Can we price any type of European option?

--- 

# Black-Scholes model: Observations

$$
\boxed{V_t(t, S_t) + r\,S_t\,V_s(t, S_t) + \frac12 V_{SS}(t, S_t) = r\,V(t, S_t)}
$$


* Can we price an American option ? 
  * An american option can be exercised at any point in time during $[0, T]$


* Is it realistic to assume continuous hedging ?


---

# Black-Scholes model with dividends

* Assume a stock pays a dividend yield $q_t$ continuously. The dynamics of the stock become:
$$
dS_t = (\mu - q)\,S_t\,dt + \sigma\,S_t\,dW_t
$$

* **Exercise**: derive the Black-Scholes formula for a dividend-paying option

--- 

# Ito formula for multiple processes

* Two-dimensional Ito Formula
  * Let $V(t, x, y)$ be a function twice-differentiable in $x$ and $y$
  * Let $\partial_tV$, $\partial_xV$, $\partial_{xx}V$, $\partial_yV$, $\partial_{yy}V$, $\partial_{xy}V$ denote the partial derivatives

  * **Theorem** Let $X_t$ and $Y_t$ be two Ito processes. Ito's formula implies that
    $$
    \begin{split}
    dV(t, X_t, Y_t) = & \partial_t V_t\,dt + \partial_x V\,dX_t + \partial_y V\,dY_t \\
    & + \frac12 \partial_{xx}V d<X,X>_t + \frac12 \partial_{yy}V d<Y,Y>_t + \partial_{xy}V d<X,Y>_t
    \end{split}
    $$
    * where $d<\cdot,\cdot>_t$ is the quadratic covariation (multiplication rule)
    ![ItoTable](./images/ItoTable.png){style="transform: translate(180%, 0%); width: 200px"}
    * When $W$ and $Z$ are two Brownians with correlation $\rho$, then  $d<Z,W>_t = \rho\,dt$


--- 

# Ito formula for multiple processes

* **Corollary:** Let $X_t$ and $Y_t$ be two Ito processes. Then  (prove it)
$$
d(X_t Y_t) = X_t dY_t + Y_t dX_t + d<X,Y>_t
$$

* **Exercise**: derive the Black-Scholes PDE for a European option paying $V(T,X_T,Y_T)$ at time $T$ where 
$$
\begin{cases}
dX_t/X_t = \mu^X\,dt + \sigma^X dW_t \\
dY_t/Y_t = \mu^Y\,dt + \sigma^Y dZ_t
\end{cases}
$$
where $W$ and $Z$ are Brownian motions with correlation $\rho$
  * Step 1: write the dynamics of the option price $V_t$
  * Step 2: write the dynamics of a self-financed portfolio that invests $\Delta_t^X$ and $\Delta_t^Y$ in the stocks $X$ and $Y$.
  * Step 3: Use a replication argument to find the hedging strategy
  * Step 4: Obtain the B&S PDE

---
layout: end
---
Thank you !

[faycaldrissi.com](https://www.faycaldrissi.com/)

---
layout: intro
---

## Session $5$: Risk-Neutral pricing in continuous-time
<br />
<br />

*Fayçal Drissi*

*Saïd Business School, University of Oxford*


---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Reminer: Risk-neutrak Valuation in a Binomial Setup <a name="defi"></a></h1>
</p>

---

## Pricing in a binomial setup

* Two states of the world with probabilities $p$ and $1 − p$
* There is a bond that pays a constant interest rate $r$.
* The payoff at time $T$ of a call option is $\max\{S(T) - K, 0 \}$. Let $C(t)$ be the price at time $t.$ 
![binomialO2](./images/binomialO2.png){style="transform: translate(10%, 0%); width: 700px"}
* To price the call, we set a portfolio $\Pi(t)$ with $B$ pounds in the bond and $\Delta$ units of the asset $S$
$$
\Pi^u(t+1) = B\, (1+ r) + \Delta\,u\,S= C^u \text{  and  } \Pi^d(t+1) = B\, (1+ r) + \Delta\,d\,S = C^d
$$
* By **no-abitrage**, the portfolio at time $t$ has the same value as the call and we write ($R=1+r$)
$$
C(t) = \Pi(t) = \Delta S+B  =\frac{C^u-C^d}{u S-d S} S+\frac{-d C^u+u C^d}{R(u-d)} =\frac{1}{R}\left[\frac{R-d}{u-d} C^u+\frac{u-R}{u-d} C^d\right] .
$$

---

## Risk-Neutral valuation in a binomial setup

* **Remark:** the price $C(t)$ of the option does not depend on the binomial probability $p$
* If we define a new probability measure $\tilde P$ that assigns $\tilde p$ to *up state* and $1-\tilde p$ to *down state*
$$
\tilde p = \frac{R-d}{u-d}
$$
* Under this risk-neutral probability measure, the price is the discounted expected payoff
$$
C(t) =\frac{1}{R}\left[\tilde p C^u+(1-\tilde p) C^d\right] .
$$
* Under this measure, the discounted price $C(t)/B(t)$ is a martingale, i.e., 
$$C(t) =\mathbb E\left[\frac{B(T)}{B(t)} C(T) \mid \mathcal F_t\right]$$
* Can we do this in continuous time ? yes.

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Reminer: Risk-neutral Valuation in continuous-time <a name="defi"></a></h1>
</p>

---

## Risk-Neutral Valuation

* A derivative's price is the risk-neutral expectation of the payoff, discounted at the risk-free rate
* We need a method to contruct this risk-neutral measure
* The main tool to construct a risk-neutral measure $\tilde P$ is *Girsanov theorem*

<br>

---

## Girsanov theorem
Let $W_t$ be a Brownian motion on a probability space $(\Omega,\mathcal{G},P)$ and let $\Theta_t$ be an adapted process. Define a measure $\tilde{P}$ on $(\Omega,\mathcal{G})$ where for all $A\in\mathcal G$
$$
\tilde{P}(A) = \int_A Z_t dP = \int_A \exp\left(-\int_0^t\Theta_u dW_u - \frac{1}{2}\int_0^t \Theta^2_u du\right) dP
$$
It follows that 
  * $\tilde P$ is a probability measure equivalent to $P$ (they agree on null sets)
  * The process $\tilde W_t = W_t +\int_0^t\Theta_u du$ is a Brownian motion under $\tilde{P}$.

* Another way of writing the change of measure is that for any adapted process $X_t$, we can write the expectation under $\tilde{\mathbb P}$ from the expectation under $\mathbb P$. For $s\le t$:
$$
\mathbb{E}_{\widetilde{\mathbb{P}}}[X_t \mid \mathcal{F}_s] = \frac{1}{Z_s} \, \mathbb{E}_{\mathbb{P}}[Z_t \,X_t \mid \mathcal{F}_s]
$$
or 
$
\mathbb{E}_{\widetilde{\mathbb{P}}}[X_t] =  \mathbb{E}_{\mathbb{P}}[Z_t \,X_t]
$

---

## Risk-Neutral Valuation
* $Z_t = \exp\left(-\int_0^t\Theta_u dW_u - \frac{1}{2}\int_0^t \Theta^2_u du\right)$ is called the *Radon-nikodym derivative* and 
* It is usually denoted by ${d\tilde{P}}/{dP}$
* **Exercise**: Show that $Z_t$ is a martingale under $P$
Of course! Here’s a clean markdown slide for Slidev, using double dollar signs for equations, and clear layout:
  * Apply Itô's Lemma to $Z_t$
  $$
  dZ_t = -\Theta_t Z_t \, dW_t
  $$
  * The stochastic integral is a martingale

---

## Risk-Neutral Valuation

* **Exercise**: Show that $Z_t\,\tilde{W}_t$ is a martingale under $P$.
  * Start from the definition of conditional expectation under the new measure:
  $$
  \mathbb{E}_{\widetilde{\mathbb{P}}}[\widetilde{W}_t \mid \mathcal{F}_s] = \frac{1}{Z_s} \, \mathbb{E}_{\mathbb{P}}[Z_t \widetilde{W}_t \mid \mathcal{F}_s]
  $$

  * Compute the product $Z_t \widetilde{W}_t$ using Itô's formula:
  $$
  d(Z_t \widetilde{W}_t) = \widetilde{W}_t \, dZ_t + Z_t \, d\widetilde{W}_t + d\langle Z, \widetilde{W} \rangle_t
  $$
  Substituting $dZ_t = -\Theta_t Z_t \, dW_t$ and $d\widetilde{W}_t = dW_t + \Theta_t \, dt$, and using $d\langle Z, \widetilde{W} \rangle_t = -\Theta_t\, Z_t \, dt$:
  $$
  d(Z_t \widetilde{W}_t) = Z_t \, dW_t
  $$
  * Therefore, $Z_t \widetilde{W}_t$ is a martingale under $\mathbb{P}$.

---

## Risk-Neutral Valuation

* **Exercise**: Show that $\tilde{W}_t$ is a martingale under $\tilde P$.
  * Start from $Z_t \widetilde{W}_t$ being a martingale under $\mathbb{P}$

  * Taking expectation:
  $
  \mathbb{E}_{\mathbb{P}}[Z_t \widetilde{W}_t \mid \mathcal{F}_s] = Z_s \widetilde{W}_s
  \implies
  \mathbb{E}_{\widetilde{\mathbb{P}}}[\widetilde{W}_t \mid \mathcal{F}_s] = \widetilde{W}_s
  $
  * Conclusion: $(\widetilde{W}_t)_{t \geq 0}$ is a martingale under $\widetilde{\mathbb{P}}$
  * It is a Brownian motion under $\mathbb P$


---

## Risk-Neutral Valuation: how to 

* Assume $\mathbb P$ is the physical (actual) probability measure and consider a GBM stock price process 
$$
dS_t = \mu \, S_t \, dt + \sigma \, S_t\,dW_t
$$

* Suppose there is a risk-free interest rate process $R_t$:

* **Step 1**: Write the dynamics of the bond price
$
dB_t = R\,B_t\,dt \implies 
B_t = \exp(R\,t)
$

* **Step 2**: write the dynamics of the discounted price process:
$$
d(\frac{S_t}{B_t}) = \frac{1}{B_t}dS_t - S_t\,\frac{dB_t}{B_t^2} = \frac{S_t}{B_t}\,\left(-R\,dt + \mu \, dt + \sigma\,dW_t \right)=\sigma\frac{S_t}{B_t}(\frac{\mu-R}{\sigma}dt+dW_t)
$$

* **Step 3**: we know $B_t/S_t$ is a martingale under the risk-neutral measure $\tilde{\mathbb P}$. So the drift of the dynamics of $S_t/B_t$ under $\tilde{\mathbb P}$ is zero. So we define a new Brownian $\tilde W$ under $\tilde P$: 
$$d\tilde W_t = \frac{\mu-R}{\sigma}+dW_t \implies d(\frac{S_t}{B_t}) = \sigma \frac{S_t}{B_t} d\tilde W_t$$

$\frac{\mu-R}{\sigma}$ is called the market price of risk

---

## Risk-Neutral Valuation: how to 

* More precisely, we define $\tilde{\mathbb P}$ using Girsanov theorem with the market price of risk 
$$
\Theta_t = \Theta = \frac{\mu-R}{\sigma}
$$

* We know by the theorem that 
$$
\tilde W_t = W_t +\Theta t 
$$
is a Brownian motion under $\tilde{\mathbb P}$.

* Therefore, we call $\tilde{\mathbb P}$ the risk-neutral measure

* Under this measure, the dynamics of the price are
$$
dS_t = R\,S_t\,dt + \sigma \,S_t\,d\tilde W_t
$$

* **Remark**: The change from ${\mathbb P}$ to $\tilde{\mathbb P}$ changes the mean but not the volatility !


---

## Risk-Neutral Valuation: how to - 2

* Otherwise, to find the change of measure, we can proceed as follows:
  * **Step 1**: we know that under the risk-neutral probabiliy measure $\tilde{\mathbb P}$, **the drift of the stock price is the short rate** (when the stock does not pay dividends !),  so
  $$
  dS_t = r\,S_t\,dt + \sigma\,S_t\,d\tilde{W}_t
  $$

  * **Step 2**: we know that the price dynamics under the physical measure are
  $$
  dS_t = r\,S_t\,dt + \sigma\,S_t\,d{W}_t
  $$
  So it's easy to see that we need 
  $$
  d\tilde{W}_t = dW_t + \frac{\mu - r}{\sigma}dt
  $$



---

## Risk-Neutral Valuation
### Exercise

* Assume a stochastic (adapted) rate $R_t$ and define
$$
dB_t = R_t \, B_t \, dt \implies B_t = \exp\left(\int_0^t R_s\,ds\right)
$$

* Assume a stochastic (adapted) volatility $\sigma_t$ and the price dynamics
$$
dS_t = \mu_t \, S_t \, dt + \sigma_t \,S_t\,dW_t
$$

* Write the dynamics of $S$ under the risk-neutral measure, and define explicitly the new Brownian.

---


## Self-financed portfolio under the risk-neutral measure

* Assume an agent who holds a self-financed portfolio $\Pi_t$ with $\Delta_t$ shares of stock at time $t$. Assume a risk-free rate $R$

* The dynamics of the portfolio are 
$$
d\Pi_t = \Delta_t dS_t + (\Pi_t - \Delta_t\,S_t)\,R\,dt 
$$

* Under the risk-neutral measure, the dynamics of $S$ are $dS_t/S_t = R\,dt + \sigma\,d\tilde{W}_t$.

* So the dynamics of the self-financed portfolio are
$$
d\Pi_t = \Pi_t \,R\,dt  + \sigma\,\Delta_t S_t d\tilde{W}_t
$$

* Define the **discount process** $\quad D_t = 1/B_t \implies D_t = \exp(-R\,t) \quad \text{and} \quad dD_t = -R\,D_t \,dt$
* The dynamics of the discounted self-financed portfolio are
$$
d\frac{\Pi_t}{B_t}=d({\Pi_t}{D_t}) = D_t (\Pi_t \,R\,dt  + \sigma\,\Delta_t S_t d\tilde{W}_t) - \Pi_t \,D_t\, R\,dt = \sigma\,D_t \,\Delta_t S_t d\tilde{W}_t
$$

* **Lemma: Every self-financed portfolio is a martingale** under the risk-neutral probability !

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Pricing under the risk-neutral measure </h1>
</p>

---

## Pricing under the risk-neutral measure

* Let $V_T$ be the payoff of a derivative security at time $T$.
  * We assume any type of path-dependent payoff (asian options !)

* We assume that there is a (possibly stochastic) interest rate $R_t$ and we define the discount process
$$
dD_t = -R_t\,D_t\,dt
$$

* Our goal is to find the initial capital $X_0 = V_0$ and the process $\Delta_t$ such that we hedge a short position in the derivative, i.e., such that we replicate the payoff with a self-financed portfolio
$$
\Pi_T = V_T.
$$

---

## Pricing under the risk-neutral measure

* We know from before that $D_t\,\Pi_t$ is martingale, so
$$
D_t \, \Pi_t = \tilde{\mathbb E}\left[D_T \, \Pi_T \mid \mathcal G_t\right]
$$

* Using the definition of $D_t$, we obtain the risk-neutral pricing formula for the continuous-time model:
$$
V_t = \tilde{\mathbb E}\left[\frac{D_T}{D_t} \, \Pi_T \mid \mathcal G_t\right]= \tilde{\mathbb E}\left[e^{-\int_t^T R_s \,ds} \, \Pi_T \mid \mathcal G_t\right], \quad\text{for all t }\in[0,T] 
$$

* We have assumed that a hedging portfolio $\Pi$ exists !

---

## Beyond this

* We can show (using the martingale representation theorem) that if the volatility is not zero and that the filtration is generated by the Brownian, that all derivatives with measurable payoff can be hedged.

* **First funadmental theorem of asset pricing**: if a market model has a risk-neutral probability measure, then it does not admit arbitrage

* Definition: a market model is complete if every derivative security can be hedged

* **Second fundamental theorem of asset pricing**: Consider a market model that has a risk-neutral probability measure. This model is complete if and only if the risk-neutral probability measure is unique


---

## Pricing a call option on dividend-paying stock

* We showed that discounted stock prices are martingales under $\tilde{\mathbb P}$

* This is true when the stock does not pay dividends !

* For the value of a portfolio investing in a *dividend paying stock* to be a martingale, the discounted value of the stock with dividends reinvested must be a martingale!

* Consider a stock that pays dividends continuously at a rate $q\ge0$

* The model for the stock price is
$$
dS_t = \mu\,S_t\,dt - q\,S_t\,dt + \sigma\,S_t\,dW_t
$$


---

## Pricing a call option on dividend-paying stock

* Agents who hold the stock receive both capital gains and dividends. The dynamics of a self-financed portfolio is
$$
\begin{split}
d\Pi_t & = \Delta_t\,dS_t + \Delta_t\,q\,dt  + (\Pi_t-\Delta_t\,S_t)\,R\,dt \\
& = R\,\Pi_t\,dt + \Delta_t\,S_t\,\sigma(\Theta\,dt + dW_t)
\end{split}
$$
where $\Theta = \frac{\mu-R}{\sigma}$ is the usual market price of risk

* We use Girsanov theorem to define $\tilde{\mathbb P}$ under which $d\tilde W_t=dW_t +\Theta dt$ is a Brownian

* Under this measure, the discounted portfolio is a martingale ! (exercise: verify)

* We can use the risk-neutral pricing formula exactly as before ! 

* The only difference is that in dividend case, the stock price dynamics under the risk-neutral measure are
$$
dS_t = (R-q)\,S_t\,dt + \sigma\,S_t\,d\tilde W_t
$$

* The solution is .... $S_t = S_0 e^{\sigma\,\tilde W_t + (r-q-\sigma^2/2)t}$ 

---

## Pricing a call option on dividend-paying stock

* The risk-neutral pricing formula gives us
$$
V_t = \tilde{\mathbb E}[e^{-r(T-t)}(S_T - K)^+ \mid \mathcal G_t]
$$
we can price a call on a dividend-paying stock

* Solution: 
$$
V(t, S_t) = S_t \, e^{-q(T-t)}\mathcal N(d_1) - Ke^{-r(T-t)}\mathcal N(d_2)
$$
where 
$$
d_1=\frac{\ln{\frac{S_t}{K}}+\left(r-a+\frac{\sigma^2}{2}\right)(T-t)}{\sigma\sqrt{T-t}}, \qquad d_2=d_1-\sigma\sqrt{T-t}
$$


---

## Pricing a call option on dividend-paying stock (Proof - 1)

* Step 1: Stock price dynamics under $\tilde{\mathbb{P}}$

When the stock pays a continuous dividend yield $q$, its dynamics under $\tilde{\mathbb{P}}$ are:
$$
dS_t = (r - q) S_t \, dt + \sigma S_t \, d\tilde W_t
$$

* Step 2: Solution by Itô calculus:
$$
S_T = S_t \exp\left( (r - q - \frac{1}{2}\sigma^2)(T-t) + \sigma (\tilde W_T - \tilde W_t) \right)
$$

* Step 3: Taking logarithm:
$$
\log S_T \sim \mathcal{N}\left( \log S_t + (r-q-\frac{1}{2}\sigma^2)(T-t), \, \sigma^2(T-t) \right)
$$

* Step 4: Define:
$$
d_1 = \frac{\log(S_t/K) + (r-q+\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}}, \quad d_2 = d_1 - \sigma\sqrt{T-t}
$$

---

## Pricing a call option on dividend-paying stock (Proof - 2)

* Step 5: 
$$
\mathbb{E}[(S_T - K)^+ \mid \mathcal{G}_t] = \mathbb{E}^{\mathbb{Q}}[S_T \mathbf{1}_{S_T > K}] - K \tilde{\mathbb P}[S_T > K]
$$

* Step 6:
$$
\begin{split}
\tilde{\mathbb P}[S_T > K] & = \tilde{\mathbb P}[\log(S_T/S_t) > \log(K/S_t)] \\
&  = \tilde{\mathbb P}[(r - q - \frac{1}{2}\sigma^2)(T-t) + \sigma (\tilde W_T - \tilde W_t) > \log(K/S_t)] \\
&= \tilde{\mathbb P}[-\frac{\tilde W_T - \tilde W_t}{\sqrt{T-t}} > d_2] \\
& = \mathcal N(d_2) 
\end{split}
$$


---

## Pricing a call option on dividend-paying stock (Proof - 3)

* Step 7: 
$$
\begin{split}
\tilde{\mathbb E}[S_T \mathbf{1}_{S_T > K}] & = \int_t^T \mathbf{1}_{S_T > K}\,S_T  =S_t \exp\left( (r - q - \frac{1}{2}\sigma^2)(T-t)\right)  \int_{S_T > K} \exp\left(\sigma (\tilde W_T - \tilde W_t) \right) d\tilde P
\end{split}
$$
we know that $\tilde W_T - \tilde W_t \sim \mathcal N (0, \sqrt{T-t})$ and 
$
S_T > K \implies \tilde W_T - \tilde W_t > -d_2 \, \sqrt{T-t}. 
$
So, using the PDF of a normal distribution
$$
\int_{-d_2 \, \sqrt{T-t}}^{\infty} \exp\left(\sigma (\tilde W_T - \tilde W_t) \right) d\tilde P = \frac{1}{\sqrt{2\,\pi\,(T-t)}}\int_{-d_2 \, \sqrt{T-t}}^{\infty} \exp\left(\sigma \,z - \frac{z^2}{2(T-t)}  \right) dz
$$
Thus
$$
\begin{split}
\tilde{\mathbb E}[S_T \mathbf{1}_{S_T > K}] &  = S_t\,e^{(r-q)(T-t)}\frac{1}{\sqrt{2\,\pi\,(T-t)}}\int_{-d_2 \, \sqrt{T-t}}^{\infty} \exp\left(-\frac12 \left(\frac{z-\sigma(T-t)}{\sqrt{T-t}}\right)^2 \right) dz \\
& = S_t\,e^{(r-q)(T-t)}\mathcal N(d_2 + \sigma \sqrt{T-t}) \\
& = S_t\,e^{(r-q)(T-t)}\mathcal N(d_1) \\
\implies V(t, S_t) & = S_t\,e^{-q(T-t)}\mathcal N(d_2) - K\,e^{-r(T-t)}\mathcal N(d_1)
\end{split}
$$

---

<br /><br /><br /><br /><br /><br />
<p style="text-align: center;"><h1>
Feynman-Kac </h1>
</p>

---

## Feynman-Kac

* When $q=0$, the price is 
$
V(t, S_t)  = S_t\,\mathcal N(d_2) - K\,e^{-r(T-t)}\mathcal N(d_1)
$
* We obtained the same result when pricing using the Black-Scholes PDE
* This is normal ! both objects are equivalent: this is the Feynmanc-Kac representation theorem. <br><br>

### Theorem
Consider the general Ito process with SDE
$$
dX_t = \mu(t, X_t)\,dt  + \sigma(t, X_t)\,dW_t
$$
Define the function 
$$
f(t, x) = \mathbb E[e^{-r(T-t)}h(X_T)\mid \mathcal F_t]
$$
then $f(t,x)$ satisfies the PDE, with terminal condition $f(T,x) = h(x)$,
$$
\partial_t f(t, x) + \mu(t, X_t)\partial_x f(t, x) + \frac12 \sigma(t, X_t)^2\partial_{xx} f(t, x) = r\,f(t,x)
$$

---

# Pricing a Put with Feynman-Kac

---

# Exercise: Pricing a Forward with Feynman-Kac


---

# Exercise: Call-Put parity

---
layout: end
---
Thank you !

[faycaldrissi.com](https://www.faycaldrissi.com/)

---