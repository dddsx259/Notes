# cheatsheet
## PART1: definition
### 1. Triangular matrix:   

A matrix that only upper or lower triangular entry is non-zero.
&emsp;A matrix is **upper triangular** if the (i j)-entry is 0 whenever $i>j$.
&emsp;A matrix is **lower triangular** if the (i j)-entry is 0 whenever $i<j$.

### 2. **Diagonal matrix:**
A square matrix that both upper and lower triangular
(i.e. Only diagonal entries is non-zero)  

### 3. **Standard vectors**
A vector in whose only i-th entry is 1 is denoted by $e_i:\ e_1, e_2, ..., e_n$ are collectively known as the **standard vectors** $e_i$  
(also called **standard unit vectors** or **standard basis vectors**) 

### 4. **Identity Matrix I**:
A matrix that only diagonal entries are $1$, others are all $0$.

### 5. Equicalent 
The two systems are **equivalent** if they have the same solution set.

### 6. **Augmented matrix**:
We append RHS constants vector to coefficient matrix, written as the following form: $ [A\ |\ b] $

### 7. **EROs**: **elementary row operations**
(I) **Exchange** two rows
(II) **Multiply** a row by a nonzero constant
(III) **Add** a multiple of a row to another row

### 8. **REF row echelon matrix:**
(1)  Zero rows must be at the bottom of the matrix (if any)
(2) The **leading entry** (i.e. first non-zero entry, also called **pivot**) of non-zero row must be on the right of the leading entries in the rows above (i.e. the entries below a leading entry must be 0)
We call it is in **row echelon form (REF)**

### 9. **RREF reduced row echelon matrix:**
(3) The column that each leading entry in only has one non-zero entry (i.e. pivot itself)
(4) Every leading entry of non-zero rows are 1
We call it is in **reduced** **row echelon form (RREF)**, or **row canonical form**

### **Inconsistent:**
If there is a linear system with no solution at all, it’s **inconsistent.**
&emsp;i.e. It's RREF has $[0\ 0\ ...\ 0\ |\ 1]$

### 10. **Rank** and **Nullity**:
&emsp;The **rank** of $A$ (denoted by **$rank(A)$**) is the number of **pivots** in the RREF of  $A$(also the REF of $A$)
&emsp;The **nullity** of $A$ (denoted by **$nullity(A)$**) is defined to be the number of **free variables** in the solutions of $Ax=0$

### 11. **Span** and **Generation set**:
Let $S$ be a finite non-empty set of vectors in $\mathbb{R}^n$, the **span** of $S$ (denoted by **$span(S)$**) is defined to be the set of all linear combinations of the vectors in S
And S is called the **generation set** of $span\{s\}$;

### 12. Elementary matrix
An **elementary matrix** is a matrix obtained from the identity matrix by performing a **single ERO**.
Specifically:
- **Type I Elementary Matrix**:
    - Corresponds to **swapping** two different rows.
    - e.g. swapping the first row with the second row in a 3x3 identity matrix.
- **Type II Elementary Matrix**:
    - Corresponds to **multiplying** a row by a non-zero scalar.
    - e.g. multiplying the second row of the identity matrix by a non-zero constant k.
- **Type III Elementary Matrix**:
    - Corresponds to **adding** a multiple of one row to another row.
    - e.g. in the identity matrix, adding k times the second row to the first row (where k is any constant).

### 13. LU Decomposition
LU decomposition of $A$ is a factorization of the form $A=LU$ in which $L$ is a unit lower triangular (square) matrix (i.e. all entries on the diagonal are 0) and $U$ is upper triangular (not necessarily square).    

$$A = 
\begin{pmatrix}
    2 & 1 \\
    4 & 3
\end{pmatrix}=
\begin{pmatrix}
    1 & 0 \\
    2 & 1
\end{pmatrix}
\begin{pmatrix}
    2 & 1 \\
    0 & 1
\end{pmatrix}
= LU
$$

$$其中：
L = 
\begin{pmatrix}
1 & 0 \\
2 & 1
\end{pmatrix},
\quad
U = 
\begin{pmatrix}
2 & 1 \\
0 & 1
\end{pmatrix}
$$

### 14. PLU Decomposition

When a matrix **hasn’t LU decomposition**, we can find an **invertible** permutation matrix $P$, so that $P^(-1)A $ has LU decomposition.

$$
P^{-1}A=LU\\
A=PLU
$$

As addition, because permutation matrix is an **Orthogonal Matrix**, so we have:

$$
P^{-1}=P^T
$$

### 15. Matrix Transformation
Let A be an m×n matrix. The function:
$$
T_a:\ R^n\rightarrow R^m\\
defined\ by\ T_a(x)=Ax
$$
is said to be the matrix transformation induced by A (such A is called the standard matrix of T).

### 16. Linear Transformation
A function $T : \mathbb{R}^n → \mathbb{R}^m$ is said to be a linear transformation if 
$$
T(u+v) =T(u)+T(v)\\
and\\
T(cu) = cT(u)
$$
for any $u,v \in \mathbb{R}^n$ and $c\in \mathbb{R}$, 
&emsp;i.e. $T$ **preserves** addition and scalar multiplication.

### 17. Injectivity and surjectivity
Let $T : \mathbb{R}^n →\mathbb{R}^m$ be a **linear transformation** with standard matrix $A$. Then:
(a) $T$ is **injective** if and only if $rankA = n$ (equivalently, T has null space{0} ).
(b) $T$ is **surjective** if and only if $rankA = m$.

### 18.Null space of T (aka null space of A,  kernel of T)
The **preimage**(原像) of $\{0\}$
&emsp;i.e. the set of all $v$ such that $T(v)=0$ is called the **null space** of $T$.

---
## PART2: property  

### 1. Given the system A**x** = **b**, the following statements are **equivalent.**    
(a) The system is consistent.
(b) The vector $b$ is a linear combination of the columns of $A$.
(c) The reduced row echelon form of the augmented matrix of the system has no row of the form $[0\ 0\ …\ 0\ |\ 1]$.

### 更一般地，在解决具有无限多解的线性系统时，我们可以将增广矩阵转换为简化行最简形式。设定那些对应于非主元列的变量为**自由变量(free variables)**，而那些对应于主元列的变量为**基础变量(basic variables)**。需要注意的是，简化行最简形式使得基础变量很容易用自由变量表示出来。

### 2. Let A be an $m\times n$ matrix. The following statements are equivalent.
(a) $Ax = b$ is consistent for every **$b\subseteq \mathbb{R}^m$**.
(b) The span of the columns of $A$  is $\mathbb{R}^m$.
(c) The RREF of $A$  has no zero row.
(c’) The RREF of $[A\ |\ b]$ has no row of the form $[0\ 0\ …\ 0\ |\ 1]$ for every **$b⊆\mathbb{R}^m$**
(d) rank(A) = m

### 3. Let A be an $m\times n$ matrix. The following statements are equivalent.
(a) The columns of $A$ are linearly independent.
(b) $Ax = b$ has at most one solution for every **$b⊆\mathbb{R}^m$**.
(c) $nullity(A) = 0$
(d) $rank(A) = n$
(e) The RREF of A is $[e_1\ e_2\ …\ e_n]$
(f) The system $Ax = 0$ only has the **trivial solution**.

### 4. Equivalent conditions about invertibility:
The following statements are equivalent for an n×n matrix A:
(1) $A$ is invertible
(2) The RREF of $A$ is $I$.
(3) The span of the columns of $A$ is $\mathbb{R}^n$ 
(4) $rank(A)=n$.(i.e. $nullity(A)=0$)
(5) $Ax=b$ is consistent for every $b∈\mathbb{R}^n$ 
(6) The columns of $A$ are linearly independent.
(7) $Ax=0$ only has the trivial solution.
(8) There exists a matrix $B$ such that $BA=I$.
(9) There exists a matrix $C$ such that $AC=I$.
(10) $A$ is a product of elementary matrices.
(11) $det(A)\neq0$
​
### 5. Common geometric transformation
#### (1) Reflection on x/y - axis
$$\begin{pmatrix}
    x\\
    y
\end{pmatrix}
\Rightarrow
\begin{pmatrix}
    x\\
    -y
\end{pmatrix}
\ or\ 
\begin{pmatrix}
    -x\\
    y
\end{pmatrix}
$$

just multiply following matrix:
$$
\begin{pmatrix}
    1 & 0\\
    0 & -1
\end{pmatrix}
\ or\ 
\begin{pmatrix}
    -1 & 0\\
    0 & 1
\end{pmatrix}
$$
#### (2)Translation upward by 1 unit
Not exist a linear transformation fot it

#### (3)Enlargement about the origin by a factor of $k$
$$
\begin{pmatrix}
    x\\
    y
\end{pmatrix}\Rightarrow
\begin{pmatrix}
    kx\\
    ky
\end{pmatrix},\ k\in \mathbb{R}
$$
just multiply following matrix:
$$
\begin{pmatrix}
    k & 0\\
    0 & k
\end{pmatrix}
$$
......

6. A transformation $T : \mathbb{R}^n → \mathbb{R}^m$ is **linear** if and only if it is a **matrix transformation**.

---
## PART3: glossary
1. Triangular matrix: 三角矩阵
1. upper triangular matrix: 上三角矩阵
1. lower triangular matrix: 下三角矩阵
1.  Diagonal matrix: 对角线矩阵
1. EROs: elementary row operations
1. REF: row echelon form
1. RREF: reduced row echelon form
1. Inconsistent: 不一致的
1. rank: 秩
1. nullity: 零度
1. Span: 张量空间
1. Generation set: 生成集
2. Elementary matrix: 初等矩阵
3. factorization: 因子分解
4. Orthogonal Matrix: 正交矩阵
5. Matrix Transformation: 矩阵变换
6. Linear Transformation: 线性变换
7. Injectivity: 单射性
8. Surjectivity: 满射性
9. Null space: 零空间
10. Kernel: 核
11. preimage: 原像
12. 