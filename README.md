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

Case 1: You lose all first n bets, then the loss you will be gone through will beW = -(1+2+22+23 …... + 2n-1)

Case 2: You win at the nth bet-
 W = -(1+2+22+23 …... + 2n-2) + 2n-1
   = -(2n-1-1) + 2n-1
   = 1
 
So, you can see in this case, either we are going bankrupt (probability of which is very less)
or we are winning 1$. You must have got an intuition that we don't intend to play the game
with Martingale strategy from the start but we use Martingale to cover our losses after loss.
