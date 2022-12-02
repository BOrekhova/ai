- The key idea is the following: generate a population of structures, test them for quality, select structures to reproduce, produce new ones, replace old ones with new ones, repeat the process.

### EA system:
1. Create a randomized population, made up of **chromosomes** (= data structures, which encode the potential solution, common a discrete string) (problem of **representation**)
2. until DONE (based on **stopping criteria**): find **objective/fitness** score for each member of population, select members to act upon using some **variation** operations (crossover, mutations), replace some members of the population with these new children, keep some old members (elitism/inheritance)
- fitness proportional (=roulette wheel) / tournament (types of selection)
- selection provides a **fitness biased method**: data structures that have a higher fitness score are more likely to continue existing (we can still accept the worst cases)
- we use mutation and crossover to reach **variation** in our population, and objective/fitness function to reach **selection**

### Genetic programming (GP)
- representation: tree-based
- bloat is extra nodes that can be removed (adding 0, or multipling, they provide no change in result )
- ADF are functions that may be defined as shorter ones (we can construct GP as a set of many ADF, that we already know)
- remember crossover/mutation in GP!
- heritablity: imagine a tree which has a lot of bloat nodes. then mutation of the tree does not affect fitness score much, **then** its children will be more likely to survive than children's of non-bloated tree
- parsimony: we would like to get a simple solution with a perfect design (=a tree where nothing left to be removed). let trees grow, trim them in the end! or put some threshold and then penalize the fitness score
- method can be used to represent function stack

### Cartesian genetic programming (CGP)
- representation: DAG (directed acyclic graph)
- mutations/crossover (=flip) are the same

### Evolutionary programming
- representation: FSM
- no crossover
- mutations: insertions (do not insert an isolated node), deletions (delete random transitions of selected node), changing in transition, output, starting node

### Evolutionary strategies
- Representation: vector of real values
- Selection: if a mutation is better, then replace the parent
- mutation: add small normally distributed parameter to a value

### Misc
- representation plays a big role on which methods are available to us, speed of evaluation becomes a factor
- crossover is more expensive
- fitness eval is **always** more expensive