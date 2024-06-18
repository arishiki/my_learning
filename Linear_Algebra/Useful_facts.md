# Proposition
For linearly independent $a_1, \cdots, a_m$ in some vector space, the matrix $\{\langle a_{i}, a_{j}\rangle\}_{i,j}$ in $\mathbb{R}^{m\times m}$ is regular.
## proof
Let $\alpha_{1},\cdots, \alpha_{n}$ be any real numbers and $\sum_{j}\alpha_{j}\langle a_{.}, a_{j}\rangle_{:,j}=0$. $\sum_{j}\alpha_{j}\langle a_{.}, a_{j}\rangle_{:,j}=\langle a_{.}, \sum_{j}\alpha_{j}a_{j}\rangle_{:,j}=0$. Since $\langle a_{i}, \sum_{j}\alpha_{j}a_{j}\rangle = 0$ for any $i = 1,\cdots, m$, $\sum_{i}\alpha_{i}\langle a_{i}, \sum_{j}\alpha_{j}a_{j}\rangle = 0$. Thus, $\langle \sum_{i}\alpha_{i}a_{i}, \sum_{j}\alpha_{j}a_{j}\rangle = 0$, which means $\sum_{i}\alpha_{i}a_{i} = 0$. By linear independency of $a_1, \cdots, a_m$, column vectors of the matrix considered are linear independent, which is followed by the regularity of the matrix. $\square$
### Note
This is true for any bi-linear mapping.

# Corollary
For a matrix $A\in\mathbb{R}^{m\times n}$ such that $\text{rank}(A)\geq n$, $A^{\mathsf{T}}A\in\mathbb{R}^{n\times n}$ is regular.
## proof
Let $A=(a_{1} \cdots a_{n})$ and $e_{1}, \cdots, e_{n}$ be canonical basis for $\mathbb{R}^{n}$. The matrix $(A^{\mathsf{T}}Ae_{1},\cdots, A^{\mathsf{T}}Ae_{n})$ is $\{\langle a_{i}, a_{j}\rangle\}_{i,j}$ and this is regular by the proposition.