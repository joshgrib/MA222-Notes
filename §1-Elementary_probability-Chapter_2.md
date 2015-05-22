#MA222 - Probability and Statistics for Engineers
"Probabilty and statistics aren't really my thing" - Andrei-Paul Grecianu, professor for the course

###Definitions
+ An **experiment** is any self-standing trial that can go multiple ways
+ The **sample space** of an experiment is the set of all possible answers
  + S(pick one marble, put it back) = {Red,Blue,Green}
  + S(pick one, then another) = {RR,RB,RG,BB,BR,BG,GG,GB,GR}
    + There is an order, one is first and one is second, so the order matters and reverse duplicates are allowed
  + S(pick two marbles) = {RR,BB,GG,RB,RG,BG}
    + There is no order, two are chosen at once, so only completely unique pairs count
+ An **event** is any possible outcome of an expieriment - this also includes combinations of outcomes
  + Events of (pick one, put it back) = {anything,R,B,G,~R,~B,~G,nothing}
    + ~R = not red
+ The **complement** of an event is the event containing all outcomes NOT in the event.We’ll call comp. A = A’
  + if P(A) = 0.02, P(A’) = 0.98

###Notation
  + Events A and B
  + A∪B is the event that either an outcome in A or one in B happens
  + A⋂B is the event that an outcome in both A and B happen

###Experiment: pick 2 marbles R,B,G. Event A is a red marble. Event B is a blue marble
  + Outcomes
    + A’ = BB,BG,GG
    + A∪B = RR,RB,RG,BB,BG
    + A⋂B = RB

###Theorem: Let A,B,C be events  -  De Morgan’s Laws
+ Part 1
  + (A∪B)’ = A’⋂B’
  + (A⋂B)’ = A’∪B’
+ Part 2
  + A∪(B⋂C) = (A∪B)⋂(A∪C)
  + A⋂(B∪C) = (A⋂B)∪(A⋂C)

###Experiment: {BB,BR,BG,RG,RR,GG}
*Drawing can make it more clear*

###Remark
+ An event can be identified with the subset of all possible outcomes that make it true. “∪,⋂” all correspond to the same operations in a set theory
+ We’re going to write “A⋂B” as “AB”

###More definitions
+ ɸ(phi) is the event that never happens
+ We will use S for the event that always happens
+ We say that event A,B are disjoint is AB=ɸ (i.e. they can never happen at the same time)
+ A probability P is a function that assigns a number to each possible event such that:
  + 0 <= P(A) for any event A
  + P(S) = 1
  + For any set X, if we have {Ai}ieX that are pair-wise disjoint, P(UieXAi) = ΣieX[P(Ai)]
    + The sum of all the pair-wise disjoint events is 1
+ The number P(A) represents the chance of an event happening out of 1
+ Generally, you can move things around in a basic algebraic way, if the sum all all events is 1, the sum of ⅘ of them is equal to 1 minus the other 5th, etc

###Summary of lecture
+ Some definitions
+ Set theory
+ Algebraic operations with sets
+ Notation-Andrei doesn’t care about notation too much but Gary might, he doesn't know
+ Other resources:
  + [Set Theory](http://www.solitaryroad.com/c725.html)
  + [MIT OCW](http://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/)

---------------Lecture 2 - 5/20/15----------------
§2.3 - Counting
Example - 20 marbles - 5 red, 3 green, 12 blue
Pick 1 at random - chance it’s blue?
Sample space {red, green, blue}
Technically true but not very useful
Next method - assume all marbles are numbered
S{1-5:red,6-8:green,9-20:blue}
All marbles are equally likely - P=0.5
12 distinct marbles make event B(blue) true
12*0.05 = 0.6 = P = =60%
Idea: describe the sample space as a finite set of equally probable outcomes - then set P(A)=|{outcomes that make A true}| / |{all possible outcomes}|
This definition requires countable outcomes
Definitions:
n! = 1*2*...*(n-1)*n
For this class, we’ll not use the terms in the book (permutation and combination) and Andrei “isn’t comfortable” using those definitions. So we’ll be using combinations for any finite collection of elements from a set, chosen according to various possible rules
Not ONLY does notation “not matter” apparently terminology is laid-back too… :/
Remarks: You can think of a combination as a string of k elements from a set with n elements is a string of length k and n possible letters
Combinations are call without repetition if the same elements cannot occur twice
Combinations are called with order if each string is equivalent to an re-arrangement of its letters
Theorem: Let S have m elements. The number of combinations of k elements of S is:
with order and repetitions: nk
with order, without repetitions: m! / (n-k)!
without order or repetitions: (n choose k) = n! / [n!(n-k)!]
without order, but with repetitions: ((n multiset k)) = ((n+k-1) choose (k-1)) = (n+k-1)! / n!(k-1)!
Proof: order, repetition, and k elements out of n
i) [n poss. letters][n poss. letters] … [n poss. letters] : string with k letters
n poss x n poss x … x n poss = nk, and since order count → all distinct
nk distinct combinations
ii) h elements out of n
[n poss. letters][n-1 poss. letters] … [(n-k+1) poss. letters] → n(n-1)...(n-k+1) different strings and order counts
all distinct
n(n-1)...(n-k+1) different combinations
iii) string of k letters with no repetitions
m! / (n-k)! possible strings
But each string is equivalent to all permutations of its letters
Each rearrangement is a combination of k letters out of k with order and no repetitions
by (ii) there are k! / (k-k)! rearrangements for each string - so each string has k! equivalent ones
number of non-equivalent strings = [n! / (n-k)!]*[1 / k!]
iv) instead of looking at it as a string think of it as n number x1,x2,...xn such that x1+x2+...+xn = k (xi represents the number of elements “i” in out combination)
Think of k circles with a bar after xi circles to visually represent our tally
we have k circles and n-1 bars
we have n+k-1 symbols, and out combination is entirely defined by our sequence
we
((n+k-1) choose k) different combinations
Example: Jar with: 5 red marbles, 3 green marbles, 12 blue marbles
i) we pick 5 marbles, what’s the chance of having all 3 colors? Again we assume marbles are numbered and otherwise distinct
# of possible outcomes: 5 marbles, no order or repetition: (20 choose 5)
We don’t have to find what it actually is because this isn’t an arithmetic course and computer can compute it better and faster than people can
A has too many different possible outcomes
instead find P(A’) and then P(A)=1-P(A’)
A’ : not all colors appear
A’ = B does not appear, or G does not appear, or R does not appear
∪,⋂
A’ = B’∪R’∪G’
P(A’) = B’∪R’∪G’ = P(B’) + P(R’) + P(G’) - P(B’R’) - P(B’G’) - P(R’G’) + P(B’R’G’)
Some could be crossed out because they logically cant happen, not enough marbles
P(A’) = [(8 ch 5) + (15 ch 5) + (17 ch 5) - (5 ch 5) - (12 ch 5)] / [(20 ch 5)]
ii) Say a friend wants to borrow 6 marbles of a specific color combination. What’s the chance you won’t be able to help him
Idea: You dont know which combination he wants so you assume theyre all equally possible
Number of possible outcomes: all possible combinations
He wants xR  red, xB blue, xG green
((3 superset 6))
We can’t help if xR>5 or xG>3 because we dont have that many
Possibilities with xG>3 → 4 of the marbles(at least) are green, the others could be anything → ((3 superset 3))
P(A) = [1+((3 2))] / ((3 6))

![equation](http://www.sciweavers.org/tex2img.php?eq=1%2Bsin%28mc%5E2%29%0D%0A&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)
