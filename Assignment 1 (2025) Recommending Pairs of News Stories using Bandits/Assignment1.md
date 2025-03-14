
Title: Assignment 1 (2025): Recommending Pairs of News Stories using Bandits
Description

You are running a web site that shows current news articles to a user visiting your website. To keep things tractable, we'll assume a very simple setup where:

  There are K = 5 "Fresh" news articles  to choose from
  The recommender must choose TWO (2) out of these to show to a visiting user
  It places one item on the top of the page and one on the bottom

We'll consider the following environment:


------------------------ Scenario Environment -----------------------

 

- Assume the recommender places item i on top and j on the bottom of the web page, then the user chooses items as follows:

- It clicks item i with probability pi (and ignores content j).

- If item i is not clicked (1-pi), then she clicks item j with probability pj.

- In other words, there can be at most one click (per user), either for item i or for item j, while with probability (1-pi)(1-pj) no item is clicked.

- You are not allowed to show the same item in both positions.

- In your code, you should pick p0,p1,p2,p3 randomly and uniformly in the interval [0.0, 0.7] with random.seed(the last two digits of your student ID)

 

--------------------------- Algorithm Design ----------------------------

 

TASK: Your task is to implement an algorithm decides which article to show on the top of the page and which on the bottom, in order to maximize the number of expected clicks over an horizon T.

 

-- Subtask 1 (for T = 1000, T = 10000): Implement UCB and compare its accumulated rewards to that of Explore-then-Exploit.

-- Subtask 2 (for T = 1000, T = 10000): Derive the (instance-dependent) theoretical regret of UCB for this problem.

-- Subtask 3 (for T = 1000, T = 10000): Demonstrate that the achieved regret for your UCB implementation is indeed upper-bounded by the theoretical curve.
