Chapter3. Solvinig Problems by Search
=====================================
3.5 <font color=green> INFORMED(HEURISTIC)SEARCH STRATEGIES </font>
----------------------------------------
----------------------------
### 3.5.1 Greedy best-first search
### 3.5.2 A* search
1. #### Minimizing the totoal estimated solution cost
+ $f(n) = g(n) + h(n)$
    + h(n) is the estimated cost of the cheapest path from n to the goal
    + g(n) the cost to reach the node
2. #### Conditions for optimality: Admissibility and consistency
+ $h(n)$ be an **<font color=red>admissible** heuristic
    + an admissible heuristic is one that **_never overestimates_** the cost to reach the goal.
    + an example of admissible heuristics is the straight-line distance $h_{SLD}$
+ $h(n)$ be an **<font color=red>consistency**(monotonicity)
    + required only for applications of A* to graph search
    + A heuristic $h(n)$ is consistent if, for every node $n$ and every successor $n'$ of n generated by any action a, the estimated cost of reaching the goal from n is no greater than the step cost of getting to $n'$
    $h(n) <= c(n,a,n') + h(n')$
    + every consistent heuristic is also admissible
3. #### Optimality of A*
    + tree-search version of $A*$ is *optimal* if $h(n)$ is admissible
    + graph-search versioin is *optimal* if $h(n)$ is consistent
        + fisrt establish: *if $h(n)$ is consistent, then the values of f(n) along any path are nondecreasing*
        + second prove: *whenever $A*$ selects a node n for expansion, the optimal path to that node has been found.*
        + A* search is complete, optimal, optimally efficient
        + **prunning**, **optimally efficient**, **absolute error**, **relative error** 
        + There can be exponetially many states with $f(n) < C*$ even if the absolute error is bounded by a constant.
    
3.6 <font color=green>HEURISTIC FUNCTIONS
------------------------------------------
----------------------------
### 3.6.1 The effect of heuristic accuracy on performance
   + effective branching factor
   + why $h_2$ is better than $h_1$?
### 3.6.2 Generating admissible heuristics from relaxed problems
   + **relaxed problem**
        A problem with fewer restrictions on the action
        *the cost of an optimal solution to a relaxed problem is an admissible heuristic for the original problem*
### 3.6.3 Generating admissible heuristic from subproblems:Pattern databases
   + **patern databases**, **subproblem**, **disjoint pattern databases**
   + Admissible heuristic can also be derived from the solution cost of a subproblem of a given problem. 
### 3.6.4 Learning heuristic from experience
   **feature**
   + to construct a heuristic function?
        + devise relaxed problems
        + learn from experience