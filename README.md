# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

--------------------------------------------------------------------------------

Using Slide 34 from the sorting powerpoint, we have 3 possible options, the two end quarters of the array being bad, and the middle half being good.  We can check all possible combinations to see what the odds are that we get a bad pivot and see overall what the chances are for getting a good one as a result.

Starting out; lets let Left be the bottom quarter of the array, Right be the top quarter, and Middle be the middle half (abbreviated to L, R, and M respectively as writing out left, right, and middle started getting tedious).  

Now starting with only the left and right, since they have a higher chance of being bad than the middle, we get:  LLL, LLR, LRL, RLL, RRR, RRL, RLR, LRR

Since each L or R have a 1/4 chance of being bad we get a $\frac{1}{4^3} = \frac{1}{64}$ * 8 for each possible combo = $\frac{8}{64}$ $\approx$ = 12.5% of a bad pivot.

Now we have to take combinations of left, right, and middle because even though middle is good almost for sure, the introduction of left and right will lower the chances of a good pivot

So possible combinations are: LLM, LML, MLL, RRM, RMR, MRR

This will have a difference chance however since each of those will be $\frac{1}{4^2}*\frac{1}{2}$ = $\frac{1}{32}$, two bad options and one good option. Next $\frac{1}{32}$ * 6 for six possible combos and we get $\frac{6}{32}$ $\approx$ 18.75% chance for a bad pivot.

Adding these together we get 12.5 + 18.75 = 31.25% for a bad pivot total using this method, which means subracting from 100, we get 100 - 31.25 = 68.75% chance for a good pivot which are pretty good odds all things considered.


So far I really only needed the slides for this exercise, it was fairly straight forward probability.

I will say however that I did take a brief gander at a couple other repositories to see if anyone had more streamlined ways to go about it.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice

