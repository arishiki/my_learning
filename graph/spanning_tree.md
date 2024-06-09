In this article, we denote $\{n, n+1, \cdots, m\} = [n,m]$ and $\{n, n+1, \cdots, m-1\} = [n,m)$. For a set $A$, $2^{A}$ denotes the set of functions from $A$ to $\{0,1\}$.

# Proposition
Let $E = \{E_{1}, E_{2},\cdots , E_{n}\}$ be the set of edges of a connected weighted graph $G$ and $w_{1}\geq w_{2},\geq\cdots, \geq w_{n}$ be corresponding weights. The following procedure produce a maximum spanning tree.
>## Procedure
>We construct a set of edges $\{A_{i}\}_{i=1}^{n}$ recursively.
>Firstly, we set $A_1=\{E_{1}\}$. When we constructed $A_{i-1}$, we define $A_{i} = A_{i-1}$ if $A_{i-1}\cup \{E_{i}\}$ forms a loop and otherwise we let $A_{i}$ to be $A_{i-1}\cup \{E_{i}\}$ (we include edges greedily). The constructed $E_{n}$ is a maximum spanning tree.
# proof
We identify a subset of $E$ with a function from $[1,n]$ to $\{0,1\}$.
That is, for $A\subset E$, $A(i) = 1$ if and only if $E_{i}\in A$.

Let $A$ be the set constructed as the procedure. It is obvious that $A$ is a spanning tree. We prove that it is indeed maximum.
Let $B$ be any another spanning tree. We construct a sequence of spanning trees $B_{0}, B_{1}, B_{2},\cdots , B_{n}$ with the sequence of sum of weights $\{\sum_{B_{i}(j)=1}w(j)\}$ increasing. It suffices to prove that $B_{n} = A_{n}$.
Let $B_{0} = B$.

We construct $\{B_{i}\}_{i=0}^{n}$ so that it satisfies the following:
1. $B_{i}$ is a spanning tree.
2. $B_{i}\restriction [1,i)\subset A$
We utilize the following lemma.

## Lemma
Let $F\subset E$ be a loop-free subgraph. Suppose that there exists $E_{i}$ such that $F\cup \{E_{i}\}$ has a loop. Then a loop in $F\cup \{E_{i}\}$ is unique.
## proof of Lemma
Let $L_{0}=E_{i}, L_{1}, \cdots, L_{m}$ be a loop of $F\cup \{E_{i}\}$ and $L'_{0}=E_{i}, L'_{1}, \cdots, L'_{k}$ be another loop. If they are distinct, then there exists the first node they take other directions (when they fork) and the first node they meet after that. Between them they form a loop without $E_{i}$, which contradicts the assumption that $F$ is loop-free. $\square$

Suppose that $B_{i}, i\in[0,n]$ satisfies the above condition 1 and 2 and that $E_{i}\in B_{i}\setminus A$ (induction hypothesis). Then $A\cup\{E_{i}\}$ includes a loop $L$ such that $E_{i}\in L$ and $L\setminus E_{i}\subset A\restriction [1,i)$ by the construction of $A$ ($E_{i}$ is rejected in the course of construction because before $i$, the members of $L\setminus E_{i}$ are already chosen). Let $L = \{L_{0}=E_{i}, \cdots, L_{m}\}$. Note that $L\setminus E_{i}\subset A$. Intuitively, we take $E_{i}$ from $B_{i}$ and add $L\setminus E_{i}$ while taking some other edges to avoid loop by addition of $L\setminus E_{i}$.
If $B_{i}\cup\{L_{j}\}$ contains a loop, it is unique by the lemma. We denote such loop by $l(j)$. Note that $L_{j}\notin B_{i}$ from the loop-free assumption of $B_{i}$.
Let $I=\{j\in[1,m]:B_{i}\cup\{L_{j}\}\text{ contains a loop}\}$ ($I$ is the domain of $l$). Note that $I\neq [1,m]$ because if $I = [1,m]$, $\{E_{i}, l(1)\setminus L_{1}, \cdots, l(m)\setminus L_{m}\}$ would be a loop in $B_{i}$, which contradicts the assumption. We let $\min ([1,m]\setminus I) = \varphi(i)$.
Let $j\in I$. Since $A$ does not contain a loop and $L_{j}\in A$, there exists an edge in $l(j)\setminus A$. We choose such an edge and denote by $f(j)$. Note that $weight(f(j))\leq weight(L_{j})$. This is because (TBD)
Based on these preparation, we construct $B_{i+1}$ from $B_{i}$. (TBD)