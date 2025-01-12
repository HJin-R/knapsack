# Search Algorithms for the 1-0 Knapsack Problem

The 1-0 Knapsack Problem is a classic optimization problem in computer science and mathematics. 

## 1. Problem Overview: The 1-0 Knapsack Problem
The 1-0 Knapsack Problem is a well-known optimization problem where the goal is to select items to maximize total value
without exceeding the weight capacity of a knapsack.
Each item has a weight and a value, and you decide whether to include each item (1) or not (0).
Problem Definition:
You are given:
N items, each with a weight and a value
Objective: Maximize the total value of selected items while ensuring the total weight does not exceed 

Example:
Suppose you have the following items:

Item 1: Weight = 2, Value = 3
Item 2: Weight = 3, Value = 4
Item 3: Weight = 4, Value = 5
If the knapsack capacity 
𝑊=5
W=5, one possible optimal solution is to select Item 1 and Item 2. The total weight is 
2 + 3 = 5,
the total value is 
3 + 4 = 7

This problem is NP-complete, meaning there is no efficient algorithm to find the exact solution in polynomial time for large inputs. 
Therefore, heuristic and metaheuristic approaches are often used to find approximate solutions.


## 2. Implemented Algorithms
### A. Genetic Algorithm (GA)
Theory:
Genetic algorithms (GAs) are inspired by the process of natural selection. They iteratively evolve a population of potential solutions by mimicking biological operations such as reproduction, crossover, and mutation.

Steps in GA:

Initialization: Create an initial population of random solutions.
Evaluation: Compute the fitness of each solution (e.g., total value of selected items without exceeding the weight limit).
Selection: Select the fittest solutions to become parents.
Crossover: Combine pairs of parent solutions to produce offspring solutions.
Mutation: Apply small random changes to offspring to introduce variation.
Replacement: Replace the least fit individuals with offspring to form the next generation.
Advantages:
Effective in exploring large search spaces.
Can escape local optima due to random mutations.
Disadvantages:
Sensitivity to the parameter settings 


### B. Tabu Search

Theory:
Tabu Search is a metaheuristic that explores the solution space systematically while avoiding cycles and previously visited solutions using a "tabu list."
The tabu list temporarily forbids certain moves to prevent revisiting the same solutions.

Steps:

Initialization: Start with an initial solution and calculate its fitness.
Neighborhood Search: Generate neighboring solutions by making small changes (e.g., flipping 1s to 0s or vice versa).
Best Move Selection: Choose the best neighbor solution, even if it has worse fitness than the current solution.
Tabu List Update: Add the recent move to the tabu list to prevent revisiting.
Aspiration Criterion: Override the tabu list if a move leads to a globally better solution.

Advantages:
Avoids local optima by systematically exploring the search space.
Balances exploration and exploitation through the tabu list.


### C. Steep Hill Climbing

Theory:
Steep Hill Climbing is a simple greedy search algorithm that iteratively improves a solution by making the best possible move at each step until no better moves are available.

Steps:

Initialisation: Start with a random solution.
Evaluation: Calculate the fitness of the current solution.
Neighborhood Search: Generate all neighboring solutions by flipping bits (changing 1s to 0s or vice versa).
Best Move Selection: Move to the neighbour with the highest fitness, provided it improves the solution.
Termination: Stop when no better neighbors exist.

Advantages:
Simple and easy to implement.
Works well for small problem sizes.
Disadvantages:
Can get stuck in local optima without exploring other parts of the search space.


