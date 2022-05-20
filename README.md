# Quant Club Whitepaper - MARTINGALES
By,
Anushka Srivastava and 
ShreeKrishna Chate

## INTRODUCTION

Have you ever considered it possible having a gambling technique that you can establish is
always a winner, a fair game, and yet might bankrupt you at the same time? The martingale
theory and betting strategy essentially demonstrates this.

The martingale probability theory is a mathematical representation of a fair game, in which
there is equal chance of winning or losing. It's a process in which today's events serve as the
best predictor of what will happen tomorrow. Originally, a martingale was a class of betting
strategies. Despite the fact that they are commonly recognized to lead to bankruptcy, they
are still widely used.

When the Martingale Strategy is used, the transaction size is doubled every time a loss
occurs. A common situation for the technique is to try to trade a result that has a 50%
chance of occurring. We also call this strategy a zero-expectation scenario. Here we are
doubling our stake each time we lose, so we say our multiplier is 2. You can use 3 or other
numbers as well as your multiplier.

Let us consider example of gambling:

Given, 

1. You are doubling the stake every time you lose.
1. You will stop playing the game if you win.
1. You are starting the game with 1$.

Calculate the profit (or loss) that the gambler will face after nth bet.
Solution:

Case 1: You lose all first n bets, then the loss you will be gone through will be <br/>
W = -(1+2+22+23 …... + 2n-1)

Case 2: You win at the nth bet- <br/>
 W = -(1+2+22+23 …... + 2n-2) + 2n-1 <br/>
   = -(2n-1-1) + 2n-1 <br/>
   = 1
 
So, you can see in this case, either we are going bankrupt (probability of which is very less)
or we are winning 1$. You must have got an intuition that we don't intend to play the game
with Martingale strategy from the start but we use Martingale to cover our losses after loss.

## FILTRATION

Now that you have gotten a basic idea of a martingale, the next step is to define it
mathematically. To do that, it is crucial to understand the concept of filtration.

A filtration is an increasing sequence of σ - algebras on a measurable probability space.
Filtrations represent the information about an experiment that has been revealed up to a
certain time t. a σ-algebra (also σ-field) on a set X is a collection Σ of subsets of X,
is closed under complement, and is closed under countable unions and countable intersections.

Looking at an example for a better understanding:

Consider an experiment where a coin is tossed 3 times in 3 seconds.

The sample space for our experiment will be a set of all the possible outcomes -<br/>
Ω = {HHH, HHT, HTH, HTT, THH, THT, TTH, TTT}

As the sample space is finite, we will take the σ - algebra, F (set of all the events possible),
as the power set of Ω -<br/>
F = 2Ω

Now starting with time t = 0,

The coin has not been tossed yet. So, we have no extra information available to us. All we
know is our sample space for the experiment. Given an outcome w, the only events from the
σ - algebra that has been revealed to us (i.e., which we know have surely occurred or not)
are Ω and φ. This is because we already know whether w will belong in Ω or not.

Making a set of all the events that have been revealed,<br/>
F0 = {φ, Ω}

We can see that F0 itself is a σ - algebra. This will be the first σ - algebra of our filtration.

At time t = 1,

The coin has been tossed once, and we have learnt some more information about the
experiment. This extra information helps us reveal two new events (apart from Ω and φ).

The event of the first toss is a head,<br/>
AH = {HHH, HHT, HTH, HTT}<br/>
And the event of the first toss is a tail,<br/>
AT = {THH, THT, TTH, TTT}

That is, given an outcome w, we will already know whether the first toss was an H or T, thus
revealing the events AH and AT.

The set of all the events that have been revealed will now be,<br/>
F1 = {φ, Ω, AH, AT}

Notice that F1 is a σ - algebra. This will be the next σ - algebra of our filtration.

Similarly, at time t = 2,

The coin has now been tossed twice. The new information will reveal many new events.
Some of them are,<br/>
the event of the first two tosses is a head,<br/>
AHH = {HHH, HHT}<br/>
the event of the first toss is a head and the second is a tail,<br/>
AHT = {HTH, HTT}<br/>
and so on.

Note that the unions and complements of the revealed events will also be revealed.

The set of all the events that have been revealed will now be,<br/>
F2 = {φ, Ω, AH, AT, AHH, AHT, ATH, ATT, ACHH, ACHT, ACTH, ACTT, AHH U AHT, ATH U ATT, AHT U ATH, AHH U ATT}

Notice that F2 is a σ - algebra. This will be the next σ - algebra of our filtration.

Finally, at time t = 3,

The experiment is complete. For any outcome w, we now have information about all tosses.
This means all the events in the σ - algebra have been revealed.

The set of all the events that have been revealed will now be,<br/>
F3 = F

We can observe that these σ - algebras, F0, F1, F2, and F3 are such that,<br/>
F0 ⊂ F1 ⊂ F2 ⊂ F3 = F

This family of σ - algebras, {Fn} 0 ≤ n ≤ 3, can be called a filtration.

Now that we have a clear understanding of filtrations, let us give a more formal definition:
Given a probability space (Ω, F, P) and some T > 0,<br/>
For 0 ≤ t ≤ T there exists a σ - algebra, F(t) such that<br/>
F(t) ⊂ F<br/>
and for some 0 ≤ s, t ≤ T and s ≤ t, the σ - algebras F(s) and F(t) are such that<br/>
F(s) ⊆ F(t).

Then the family of σ-algebras → {F(t)} 0 ≤ t ≤ T is called a filtration that is associated with the
probability space (Ω, F, P).

## MARTINGALES

You may have picked up a bit on Martingales in the introduction part. However, once
we've covered filtration, we can move on to the important aspect of Martingales,
which includes the basic mathematics underlying it and its applications. 

Martingales is a stochastic process (sequence of random variables) in which the
conditional expectation of the next value in the sequence, regardless of all previous
values, is equal to the current value of the sequence.

To offer a simple illustration, imagine tossing a coin in a sequence: if it comes up
head, you get one dollar; if it comes up tail, you lose one dollar. Let's say you have
$5 after 100 such tosses. As a result, your expected value after the 101st coin is $5.
Isn't it straightforward? This is the core concept of Martingales; we should grasp the
basic mathematics underlying it to have delve more into it. 

1. Say, {Fn}n≥0 is an increasing sequence of σ−algebras (filtration) in a probability
space (Ω, F, P). Let X0, X1, X2 …. Xn is an adapted sequence (Xn ∈ Fn) of integrable
real valued random variable such that E(Xn+1) < ∞, the sequence X0, X1, X2 …. Xn is
said to be a Martingale relative to the filtration {Fn}n≥0 if <br/>
 E (Xn+1 |Fn) = Xn (Martingale condition)
 
1. We have, <br/>
 E(Xn+1|Fn) = Xn. <br/>
 E(Xn+k|Fn) = E((Xn+k|Fn+k-1)|Fn) (Using Tower’s property)<br/>
 = E(Xn+k-1|Fn) (Using Martingale)<br/>
.<br/>
.<br/>
.<br/>
 = E(Xn+1|Fn)<br/>
 = Xn 
 
1.  The expectation of next value in sequence to be equal to current value, there are
several types of martingales sequences, the most basic one is sums of independent,
mean zero random variables. Let Y1, Y2... be such a series; then with following
conditions,<br/>
 E(Yi) = 0<br/>
 Fn = σ (Y1, Y2, Y3…. Yn)<br/>
the partial sums sequence:<br/>
 Xn = Y1 + Y2 + Y3… Yn<br/>
is a martingale in comparison to the natural filtering caused by the variables Yn. The
linearity and stability features, as well as the independence law for conditional
expectation, make this easy to verify:<br/>
 E (Xn+1 |Fn) = E (Xn +Yn+1 |Fn)<br/>
 = E (Xn |Fn) + E (Yn+1 |Fn) (Linearity)<br/>
 = Xn +E(Yn+1)<br/>
 = Xn.
 
Example:

We went through a 3-coin toss example in the filtration part, now let's do the same
thing in Martingales. If we apply the random variables and probability terms to the
three coin-toss examples, we get Xn, which is the total amount won/lost in n bets.

The profit/loss on the nth bet is represented by Yn. Fn is a collection of values that
may be obtained via the use of n bets. So, if we have been given a Fn that has led us
to an Xn value, we may claim that our value X will not change after one more bet
since the Yn+1 expectation will be zero owing to fair toss.

Now, once we have done the basic mathematics of the martingales we can move
towards the applications of Martingales in stock market.

## WHY MARTINGALE IN STOCK MARKET?

1. According to the Efficient Market Hypothesis, beating the market on a riskadjusted basis is impossible since the market should only react to fresh information.
As a result, trading cannot be done in such a way that you never gain or lose with a
positive probability.
1. In the fundamental theorem of finance, the acceptable probability is known as
risk-neutral probability, which is a measure of equivalent Martingale.

This is bit hard to understand if you are new to the stock world, but there is very
simple meaning behind this i.e., This suggests that, regardless of how much money
a firm is losing at the time, an investor should not give up, but rather keep investing
in the hope that perseverance will eventually pay off. Before using the martingales in
real world one should be aware of its risk. The majority of investors do not employ
martingales as their primary investment strategy, but rather combine it with other
momentum techniques and then use it.

## APPLICATIONS OF MARTINGALES IN STOCK MARKET

1. Most investors do not strictly follow the Martingale method since it is not the
greatest way to invest, but every investor indirectly utilises the Martingale approach
to lower the average price of the stocks he owns down if he learns that the stock
price is going to rise in a short period of time.

1. Martingale trading is a common forex trading method. The fact that currencies,
unlike equities, seldom fall to zero, is one of the reasons why the martingale
technique is so popular in the currency market. Although businesses may readily go
bankrupt, most countries do so on their own volition. A currency's value will fluctuate

## IMPLEMENTATION OF MARTINGALES

Let us see what we have,

Initially the investor will buy one stock. The primary premise behind using
Martingales to generate an idea for this stock is that if the current day's stock price is
less than 1.5% lower than the previous day's, the investor should double his
investment at the end of the day. Investment will rise, and investors might be able to
profit from the market even if there are fewer victories


Dataset: <br/>
Apple data containing for date and price (closing) for the time interval 6/3/2019 to
31/12/2019

Simple Martingale strategy: <br/>
Signal is a indication of action to the investor if he has buy, hold. If current day’s
price is 1.5% greater than previous day’s close then +1, if current day’s price is 1.5%
less than previous day’s close then -1, Otherwise 0.

Quantity is number of shares the investor own on the day.

Invested money is total money invested from the starting date to till date.

Returns are returns on the given date and returns_in_per are returns on the given
date in percentage.

Cumulative returns is net returns from the starting date to till date, cumulative returns
in percentage is total returns from starting date to till date in percentage.

In the final file given below you can see, the cumulative returns in percentage for the
period of 6 months is 9.57 for total invested money 312360.7804$. 
