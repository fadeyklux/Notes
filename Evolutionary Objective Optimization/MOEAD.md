<font color = lighblue>MOEA/D
==============
## **Main idea**
>approximation of the **PF** can be decomposed into a number of scalar objective optimization subproblems.
+ Why This decompostion works? What's the mechanism?
    + most important, because all of the algorithm is based on this theorm

## **Question**
    
>For each Pareto optimal point $x^*$, there exists a weight vector $\lambda$ such that $x^*$ is the optimal solution of $g^{te}(x|\lambda,z^*)$ and each optimal solution of $g^{te}(x|\lambda,z^*)$ is a Pareto optimal solution.
+ is there a unique solution $x^*$ of $g^{te}(x|\lambda,z^*)$ for a given $\lambda$ and $z$? making $x^*$ = $Arg\{g^{te}(x|\lambda,z^*)\}$
+ **proof**
    $x^*$ is a pareto optimal point, $\forall x \in \Omega ,\exists$ at least one $i$, $s.t$ $f_i(x^*) > f_i(x)$ we choose such $\lambda$ that $\max \limits_{1\leq j\leq m} \{\lambda_j| f_j(x) - z_j^*|\} = \lambda_i|f_i(x)-z_i^*|$ since $|f_i(x^*)-z_i^*| < |f_i(x)-z_i^*|$ $min\{g^{te}(x^*|\lambda,z^*)\} = \lambda_i|f_i(x^*)-z_i^*|$. thus $x^*$ is the optimal solution of  $g^{te}(x|\lambda,z^*)$.
    + but this leading to another question
    for different pair of $(x^*, x)$ the $i$ may be different, which means different $\lambda$. It seems that no unique $\lambda$ can hold for all condition for a given pareto optimal point $x^*$ 

## **Major motivation**
any information about these $g^{te}(x|\lambda,z^*)$ with weight vectors close to $\lambda^i$ should be helpful for optimizing $g^{te}(x|\lambda,z^*)$.

## which parts in MOEA/D need **problem-specific** method?
1. when generate initial population
2. when initialize referrence points
3. after generating **y'** using problem-specific repair/improvement heuristic
## **plan description** of MOEA/D
+ every time we optimize N scalar subproblem
+ the **_ith_** subproblems was assgined with a $x^i$ and $\lambda^i$
+ **update among one neighbour**
+ for every subporblem, consider it's neighbour, generate a new child y from it and update all the solutions to subproblems belongs to this neighbour.
+ update **EP**
------------------------
## 1. INTRODUCTION
+ dominate
+ decision(variable) Pspace
+ attainable objective  set
+ Pareto optimal(objective) vector
+ Pareto optimal points
+ Pareto set(PS)
+ Pareto front

## 2.DECOMPOSITION OF MULTIOBJECTIVE OPTIMIZATION
+ A. **Weighted Sum** Approach [1]
+ B. **Tchebycheff** Approach [1]
+ C. **Boundary Intersection(BI)** Approach

## 3.THE FRAMEWORK OF MOEA/D
+ #### A. General Framework
    + neighborhood of the _i_ th subproblem
+ #### B. Discussions
    + Why a **Finite Number of Subproblems** are considered?
    + How **diversity** is Maintained?
    + **Matiing restriction** and role of T
+ #### C. Variants of MOEA/D
    + step 2.2 is not a must in MOEA/D
    + **EP** is an option
## 4. COMPARISION WITH MOGLS
+ #### C. MOKP
    + NP-hard
+ #### D. Implementations
## 5. COMPARISON WITH NSGA-II
+ objective normalization

## Futher reading
+ approximate the PF by using a mathematical model [5]-[8]
+ cMOGA [40] Hisao