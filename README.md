java c
Rations
This is a regular task. You must submit a PDF, which can be produced using the LATEX template on Moodle, exported from a word processor, hand-written or any other method.
There are n towns in a line. A traveller starts at town 1 and wants to reach town n. It takes a week to travel from any town to the next.
In each town except the last, there is a market where you can buy rations. In the market of town i, you can buy a week’s worth of rations for ci dollars. Furthermore, you can buy several weeks’ rations for later consumption. Here is an example with 6 towns, showing the optimal number of rations to buy at each town:

Before the traveller sets off on their trip, they learned of the cost of buying rations from each town. They are asking for help in calculating the minimum cost to travel from town 1 to town n. In the first week of travel, you will always have to use rations bought in the first town. However, the second week’s rations can be bought from the first or second town, and so on.
(a) In the kth week, which town’s rations should you eat?
(b) Hence, design an O(n) algorithm which finds the minimum total cost for all rations bought.
(c) Prove the correctness of this algorithm using the greedy stays ahead method. The metric for “ahead” should be the amount spent on the first k weeks’ rations.
Rubric.
(a) Describe a property of the towns ration’s that you should eat in the kth week, and argue why this is correcct.
(b) Describe an O(n) algorithm that determines the smallest possible cost to travel from town 1 to town n. Briefly justify that your algorithm runs in O(n) time.
(c) Prove that the algorithm minimises the cost of travelling the first k weeks for all k, by induction, and address whether the algorithm is correct.
Expected response length: about a paragraph each for (a) and (b), and no more than a page for (c).
Notes.
(a代 写RationsSQL
代做程序编程语言) The cheapest so far; so the cheapest town up until town k.
(b) Correct solutions will track the “cheapest so far”.
(c) Greedy’s spend in the first k weeks was already no worse than the alternative, and then we spent the least possible in week k+1, so term-by-term it’s still no worse than the alternative.
Sample Solution.
(a) We should eat the cheapest town’s rations prior to town k, as these are the cheapest acces-sible rations, and any other ration will have the overall cost be no better.
(b) The idea is that for each week, we use the cheapest rations available of all the towns before that point. We can calculate this in one sweep: we keep track of the current total cost, and the cheapest cost of all the towns we have seen. At each town, we update the cheapest cost if the current one is less, then add the cheapest cost to the total cost. This is clearly O(n), as we perform. one sweep of the array.
(c) For the base case, travelling the first week always costs exactly the price of rations in the first town, so the greedy strategy is as good as any alternative (indeed, there is no alternative).
Let Gk be the minimum cost of the first k weeks of rations using the greedy strategy, and likewise Ak using an (arbitary) alternative selection. Then we know Gk ≤ Ak by the induction hypothesis, and we seek to prove that Gk+1 ≤ Ak+1 also.
Now, the greedy strategy’s spend in week k + 1 is the minimum cost of rations from any of the first k + 1 towns, so

The alternative must buy for week k + 1 from one of the first k + 1 towns, so
Ak+1 = Ak + cj
for some 1 ≤ j ≤ k + 1. But then

as required.
Therefore the greedy spends less than any alternative after any number of weeks, by induc-tion. This includes after n − 1 weeks, i.e. for the whole journey, so the greedy minimises the total spend.







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
