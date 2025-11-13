You effectively implemented a Genetic Algorithm (GA) for the Traveling Salesman Problem (TSP). The README is very helpful for following your code, which is modular, clear and well-documented. Here's a detailed comment on your work:

- Solution representation: The path representation is a standard and effective choice for a GA.

- Initial solution: Starting from a randomly shuffled greedy solution instead of a completely random one is a good idea.

- Parent selection: Tournament selection is a standard approach and works well for this problem.

- Crossover: The use of edge recombination is effective in preserving valuable edge information. One of the main problems of this crossover is that it relies on the problem symmetry, which is not case for "r1" and "r2" problems. Maybe for those cases it would be helpful to use other types of crossover, such as order crossover.

- Mutation: Combining a standard mutation (swap) with a more sophisticated one (2-opt) significantly improves your results in the "g" problems, as demonstrated in the README. The problem is 2-opt does not account for the asymmetry of problems "r1" and "r2".

- Elitism: A standard and useful practice. Refining the best individuals further with 2-opt is a smart improvment.

- Adaptation: Scaling parameters according to the problem size makes sense. To further improve your already strong results, you might explore self-adaptive parameter tuning (e.g., for the mutation rate).

Overall, your algorithm produces very good results for the "g" problems, while it doesn't seem to work properly in the "r1" and "r2" cases: the fitness doesn't improve upone the initial solution. The final visualization is particularly helpful for understanding the system’s behavior and visualizing the paths in space.

I have applied some modifications to your code to account for the asymmetry in the "r1" and "r2" problems (no modifications for "g" cases):
- use ordered crossover instead of edge recombination;
- do not apply opt-2 afeter the swap mutation;
- do not refine best individuals in the elitarian process;

To show the improvement I have run it on the "r1_100" problem.
