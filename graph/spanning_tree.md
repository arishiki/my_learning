In this article, we denote $\{n, n+1, \cdots, m\} = [n,m]$ and $\{n, n+1, \cdots, m-1\} = [n,m)$. For a set $A$, $2^{A}$ denotes the set of functions from $A$ to $\{0,1\}$.
For an edge $E$ in a weighted graph, let $\text{weight}(E)$ be the corresponding weight.

# Proposition
Let $\mathcal{E} = \{E_{1}, E_{2},\cdots , E_{n}\}$ be the set of edges of a connected weighted graph $G$ and $w_{1}\geq w_{2},\geq\cdots, \geq w_{n}$ be corresponding weights. The following procedure produce a maximum spanning tree.
>## Procedure
>We construct a set of edges $\{A_{i}\}_{i=1}^{n}$ recursively.
>Firstly, we set $A_1=\{E_{1}\}$. When we constructed $A_{i-1}$, we define $A_{i} = A_{i-1}$ if $A_{i-1}\cup \{E_{i}\}$ forms a loop and otherwise we let $A_{i}$ to be $A_{i-1}\cup \{E_{i}\}$ (we include edges greedily). The constructed $E_{n}$ is a maximum spanning tree.
# proof
We identify a subset of $E$ with a function from $[1,n]$ to $\{0,1\}$.
That is, for $A\subset E$, $A(i) = 1$ if and only if $E_{i}\in A$.

Let $A$ be the set constructed as the procedure. It is obvious that $A$ is a spanning tree. We prove that it is indeed maximum.
Let $B$ be any another spanning tree. We construct a sequence of spanning trees $B_{0}, B_{1}, B_{2},\cdots , B_{n}$ with the sequence of sum of weights $\{\sum_{B_{i}(j)=1}w(j)\}$ increasing. It suffices to prove that $B_{n}\subset A_{n}$.
Let $B_{0} = B$.

We construct $\{B_{i}\}_{i=0}^{n}$ so that it satisfies the following:
1. $B_{i}$ is a spanning tree.
2. $B_{i}\restriction [1,i]\subset A$

We construct $B_{i}$ from $B_{i-1}$ assuming $B_{i-1}$ satisfies the conditions 1 and 2 as below:
(i)Case where $E_{i}\notin B_{i-1}\setminus A$ (i.e. $E_{i}\in A$ or $E_{i}\notin B_{i-1}$)
In this case, let $B_{i}=B_{i-1}$. In this case, the sum of the weight remains the same.

(ii)Case where $E_{i}\notin B_{i-1}\setminus A$
In this case, we construct $B_{i}$ by trying to removing $E_{i}$ from $B_{i-1}$. To keep it spanning, we exploit the fact that there is a bypass route in $A$ from $\text{n}1(E_{i})$ to $\text{n}2(E_{i})$. We add some of edges in this bypass route while avoiding making a loop. Through the process, the sum of the weights only increases.

$A\cup\{E_{i}\}$ includes a loop $L$ such that $E_{i}\in L$ and $L\setminus E_{i}\subset A\restriction [1,i)$ by the construction of $A$ ($E_{i}$ is rejected in the course of construction because before $i$, the members of $L\setminus E_{i}$ are already chosen). Let $L = \{E_{i} = \{N^{i}_{0}, N^{i}_{1}\}, \{N^{i}_{1}, N^{i}_{2}\}, \cdots, \{N^{i}_{m-1}, N^{i}_{m}\}\}$. We recursively construct a sequence $C_{0}^{i}=\empty\subset C_{1}^{i}\subset \cdots\subset C_{m-1}^{i}\subset L$. We maintain that for $k=1,\cdots, m-1$, $(B_{i-1}\setminus \{E_{i}\})\cup C_{k}^{i}$ contains no loop and that there is a path in $(B_{i-1}\setminus \{E_{i}\})\cup C_{k}^{i}$ from $N^{i}_{1}$ to $N^{i}_{j}$ for $j = 1, \cdots, k+1$ along the recursive construction.

Assume that for $k-1$, the recursion hypothesis holds.
We construct $C_{k}^{i}$.
If $(B_{i-1}\setminus \{E_{i}\})\cup C_{k-1}^{i}\cup \{N^{i}_{k}, N^{i}_{k+1}\}$ contains no loop, then $C_{k}^{i}=C_{k-1}^{i}\cup \{N^{i}_{k}, N^{i}_{k+1}\}$. This keeps the assumption for $k$.

If it contains a loop, we let $C_{k}^{i}=C_{k-1}^{i}$. This is because if adding $\{N^{i}_{k}, N^{i}_{k+1}\}$ to $(B_{i-1}\setminus \{E_{i}\})\cup C_{k-1}^{i}$, which has no loop by the assumption, causes a loop, then $(B_{i-1}\setminus \{E_{i}\})\cup C_{k-1}^{i}$ already has a path from $N^{i}_{k}$ to $N^{i}_{k+1}$. Thus, assumption for $k$ holds.

By recursion, we obtain $C_{0}^{i}=\empty\subset C_{1}^{i}\subset \cdots\subset C_{m-1}^{i}\subset L$. By the assumption for $m-1$, $(B_{i-1}\setminus \{E_{i}\})\cup C_{m-1}^{i}$ contains no loop and that there is a path from $N^{i}_{1}$ to $N^{i}_{m}$ in $(B_{i-1}\setminus \{E_{i}\})\cup C_{m-1}^{i}$. We let $B_{i} = (B_{i-1}\setminus \{E_{i}\})\cup C_{m-1}^{i}$. Combined with the assumption on $B_{i-1}$, means that $B_{i}$ is a spanning tree because there is another path that connects the points which were connected by the only removed edge $E_{i}$. Also, $B_{i}\restriction [1,i] = B_{i-1}\restriction [1,i-1]\subset A$.

Note that $C_{m-1}^{i}$ is not empty. It is because of the following factor. If $C_{m-1}^{i}$ is empty then $(B_{i-1}\setminus \{E_{i}\})\cup C_{m-1}^{i}$ = $(B_{i-1}\setminus \{E_{i}\})$ is said to connect the nodes of $E_{i}$, which means $B_{i-1}$ has a loop containing $E_{i}$. But this contradicts the no-loop assumption of $B_{i-1}$.

This construction of $B_{i}$ from $B_{i-1}$ involves removing one edge $E_{i}$ and the addition of $C_{m-1}^{i}$, which is not empty. $C_{m-1}^{i}\subset L\subset A\restriction [1,i)$, thus the added edges (one or more) precede $E_{i}$ ($A^{-1}(C_{m-1}^{i})\subset [1,i)$). This means that transitioning from $B_{i-1}$ to $B_{i}$ only increases the sum of the weights.

By recursion, we obtain $B_{0}, B_{1}, B_{2},\cdots , B_{n}$ and by the assumption, $B_{n}\subset A$, which concludes the proof.