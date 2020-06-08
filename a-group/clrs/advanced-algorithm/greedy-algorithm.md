---
description: >-
  For many optimization problems, using dynamicprogramming to determine the best
  choices is overkill; simpler, more efficient algorithmswill do.
---

# Greedy Algorithm

A greedy algorithm always makes the choice that looks best at the moment. That is, it makes a locally optimal choice in the hope that this choice will lead to a globally optimal solution.

## Elements of the greedy strategy

A greedy algorithm obtains an optimal solution to a problem by making a sequence of choices. 

#### Greedy-choice property

The first key ingredient is the greedy-choice property: we can assemble a globally optimal solution by making locally optimal \(greedy\) choices.

A dynamic programming algorithm proceeds bottom up, whereas a greedy strategy usually progresses in a top-down fashion, making one greedy choice after another, reducing each given problem instance to a smaller one.

#### Optimal substructure

A problem exhibits optimal substructure if an optimal solution to the problem contains within it optimal solutions to subproblems. This property is a key ingredient of assessing the applicability of dynamic programming as well as greedy algorithms.



