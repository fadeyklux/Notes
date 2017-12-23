MOEA/D
==============
## Conclusion
+ **main idea**
    approximation of the **PF** can be decomposed into a number of scalar objective optimization subproblems.
+ **major motivation**
    any information about these $g^{te}(x|\lambda,z^*)$ with weight vectors close to $\lambda^i$ should be helpful for optimizing $g^{te}(x|\lambda,z^*)$.
+ which parts in MOEA/D need **problem-specific** method?
    1. when generate initial population
    2. when initialize referrence points
    3. when improve y' using problem-specific repair/improvement heuristic
## Futher reading
+ approximate the PF by using a mathematical model [5]-[8]
+ cMOGA [40] Hisao
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
+ #### 