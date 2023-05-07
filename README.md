Download Link: https://assignmentchef.com/product/solved-ie523-homework-5-how-much-would-you-pay-to-play-this-card-game
<br>
This programming exercise is meant to get you thinking about recursive algorithms for pricing options and other financial instruments. We will use a card-game to motivate the algorithm development. The problem statement is as follows:

I shuffle a deck of cards (with an equal number of <strong>red </strong>and <strong>black </strong>cards) and start dealing them face up.

After any card you can say “<strong>stop</strong>”, at which point I pay you $1 for every <strong>red </strong>card dealt and you pay me $1 for every <strong>black </strong>card dealt.

What is your optimal strategy, and how much would you pay to play this game?

You are going to write a C++ program, which uses recursion, that takes as command-line input the number of cards in the deck, and comes up with the <em>no-arbitrage price</em><a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> for this game.

<h1>Hints</h1>

<ol>

 <li>The no-arbitrage price is at least zero. Because, you can wait till all cards are dealt (and there is the same number of <strong>red </strong>and <strong>black </strong>cards dealt; and you owe nothing).</li>

 <li>You should ask for another card only if the expected value of continuing to play is greater than the amount of money already won by you. Otherwise, you should say “<strong>stop</strong>.”</li>

 <li>If value(#red cards left, #black cards left) is a function that computes the value of the game to you at any point, then</li>

</ol>

value(#<strong>Red cards left</strong>, #<strong>Black cards left</strong>)) =

max{(Prob of <strong>Red Card </strong>drawn) × value(#<strong>Red cards left-1</strong>, #<strong>Black cards left</strong>))


(Prob of <strong>Black Card </strong>drawn) × value(#<strong>Red cards left</strong>, #<strong>Black cards left – 1</strong>))<em>,</em>

(#<strong>Black cards left </strong>– #<strong>Red cards left</strong>) (1)

(??<strong>Why</strong>??)

<ol start="4">

 <li>Think of a recursive implementation (after presenting an appropriate justification) for equation 1 shown above.

  <ul>

   <li>A naive implementation of the recursion will run into run-time problems (cf. figure 1) when the size of the deck exceeds 35.</li>

   <li>Look up the method of <a href="https://en.wikipedia.org/wiki/Memoization">memoization</a> to come up with a faster implementation of the recursion, which can handle large card deck size with ease (cf. figure 2). Or, you could just pay attention when I cover this in class <em>^</em>¨ .</li>

  </ul></li>

</ol>

Here is what I want from you for this programming assignment

<ol>

 <li>C++ code with appropriate Class definitions that takes the size of the deck as input and returns the arbitrage-free price for playing the game. Your implementation should be able to handle a deck with 52 cards, at least.</li>

</ol>

<h1>References</h1>

Figure 1: Sample output. Notice the growth in running-time as the #cards in the deck is increased. We have think of something to overcome this issue. We want to be able to handle decks of size 52 or higher! See sample output in figure

2.

Figure 2: Sample output of an implementation that can handle cases where the #cards in the deck is large. See sample output in figure 1 for a comparison of run-times.

<a href="#_ftnref1" name="_ftn1">[1]</a> <em>Arbitrage </em>occurs when you can make a profit that is in excess of the <em>risk-free rate of return</em>, which is zero for this problem.

You have an <em>arbitrage opportunity </em>if you can create a portfolio of zero value today, but this portfolio has a positive value in the future with a positive probability, and a negative value in the future with zero-probability.

The “<em>no-arbitrage principle</em>” suggests that there are no arbitrage opportunities in any market. This “<em>there is no free-lunch</em>” assumption is the corner-stone of classical finance theory (cf. section 3.2, [<strong>?</strong>]).