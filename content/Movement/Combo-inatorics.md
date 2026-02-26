# Eternal Return
Say you have 10 combos, each following the [eternal return](FIX%20ME.md#Eternal%20Return%20The%20end%20IS%20the%20beginning) formula.
Further, say a round consists of an arrangement of 3 different combos.  

If we re-call some high school maths, we will recognize this as a [permutation](https://en.wikipedia.org/wiki/Permutation#k-permutations_of_n) problem:
$$
P(n,r)=\frac{n!}{(n-r)!}
$$
where $n$ is the size of your arsenal and $r$ is the number of combos in a round.

We crunch the numbers and arrive at 720 rounds.

Not too bad, but if we try two new rounds every day we'll exhaust this in a year.
We can roughly quadruple this by adding five new combos:
$$
P(15,3)=2730
$$
At that scale you have *freedom* to always do a different round, *without* crazy mental load.

# Multi-reset
This is where we graduate to college math.
When we add new resets, the scenario can be described with a directed graph, where each node is a reset position and each edge is a combo.  

Figuring out how many different rounds can exist in this scenario reduces to:
- Counting walks in a directed graph

To assist our calculations we construct an [Adjacency Matrix](Adjacency%20Matrix.md) where entries
$$
a_{ij}=\text{number of combos that start in position i and end in position j}
$$

If we can allow for combo-repeats (re-use edge), the solution is $A^n$ where $n$ is the number of combos in the round. The entries of this matrix tell us how many 'walks' we can take if we start/end in position i/j. We can sum each matrix entry to get the total number of possibilities.

Example: graph TODO
Let's say we have 10 combos as before, but now two positions A, B.
3 combos from A to A, 2 from A to B.
3 combos from B to B, 2 from B to A.

If we enumerate the number of possible rounds with 3 combos in this case we get: 250.


Surprisingly, even with repeats we have less options than eternal return.


TODO: Case no repeats


# Can I go anywhere?

Directed combos: https://en.wikipedia.org/wiki/Eulerian_path#Directed_Eulerian_graphs

Assuming you can time-reversal your combos: https://en.wikipedia.org/wiki/Eulerian_path#Undirected_Eulerian_graphs