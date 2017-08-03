# Matrices

[TOC]

The previous chapter was all about linear transformations. Terence Tao claims that the essence of linear algebra is the study of linear transformations. How far this claim is true remains to be seen. But this chapter on matrices certainly strengthens it. We concluded the previous chapter with the an important concept - the correspondence between matrices and linear transformations.

Matrices are very concrete representations of linear transformations. It is a grid of numbers, definitely less abstract than a function between vector spaces. This chapter will focus on the study of matrices; the linear transformation will act as a constant support in the background, coming forward to offer its services as and when required. This connection should never be severed.

**Collection of Column-Vectors**


$$
\begin{align}

y &= x_1 T(b_1) + ... + x_n T(b_n)

\end{align}
$$

$$
\begin{bmatrix}
       y_{1} \\
       y_{2} \\
       \vdots \\
       y_{m}
     \end{bmatrix}  = x_1\begin{bmatrix}
       a_{11} \\
       a_{21} \\
       \vdots \\
       a_{m1}
     \end{bmatrix} + \cdots + x_n \begin{bmatrix}
       a_{1n} \\
       a_{2n} \\
       \vdots \\
       a_{mn}
       \end{bmatrix}
$$

The column-vector view of a matrix closely links the linear transformation and the matrix. Each column is the image of the linear transformation on one of the basis vectors. The effect is one of warping the space. Refer [3blue1brown](https://www.youtube.com/watch?v=kYB8IZa5AuE&index=4&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) for a beautiful visualization of this concept.

### Rank of a Matrix

The rank of a linear transformation is its signature. Why is this the case? From the rank-nullity theorem it is clear that for any linear transformation $T$ from $V$ to $W$,  $rank(T) + nullity(T) = dim(V)$. The nullity is one aspect of the linear transformation, but not very striking - it is a measure of that part of the domain which  is degenerate. The rank, on the other hand is a useful measure that gives the extent of control over the co-domain. Also, if the rank is determined, the nullity is automatically fixed. Thus it will be instructive to study the rank of the linear transformation in greater detail.

Let us first look at the various values of the rank. It can range from $0$ to $min(dim(V), dim(W))$. If it is $0$, then the linear transformation is trivial. Any intermediate value is unremarkable; but the extremes are interesting. $T$ is invertible *iff* $dm(V) = dim(W) = rank(T)$,

All this is fine, but given a linear transformation, how can we compute its rank? It is one thing to theorize about its existence, another to actually compute it. Perhaps it is for these purposes that the correspondence with matrices is most useful. The matrix is the computational side of the linear transformations, its more practical, application loving aspect. An excess of this tendency reduces linear algebra to matrix algebra, completely veiling its theoretical side. In a more wholesome view of things they are the obverse and reverse of a single concept, and perfectly complement each other.

By exploiting the correspondence between linear transformation and matrices, we give the following definition to the rank of a matrix, in the hope that computing the rank of a matrix may be more tangible.

> If $A$ is an $m \times n$ matrix, $rank(A) = rank(L_A)$.

A few observations can be made here:

> $rank(A) = dim(span(Col(A)))$, where $Col(A)$ is the set of column vectors of $A$.

The span of the column vectors is nothing but the range space of $A$. Naturally, its dimension is the rank. This observation doesn't make our life any easier, but this observation is visually more powerful.

### Elementary Matrix Operations

The theory of elementary matrix operations must be studied for its own sake though its utility in computing the rank of the matrix is a strong motivator.

When a matrix is treated as a grid of numbers, nothing more and nothing less, we can think about a few harmless operations: swapping rows and columns, adding two rows together, multiplying all elements in a row by a constant factor and so on. These operations are truly elementary in the sense that these are some of the simplest operations that can be done with matrices, also because they cannot be reduced to something more fundamental. Elementary matrix operations are the atomic operations in the space of matrix operations. But the consequences of these operations are by no means trivial. This is what makes their study interesting. The computational aspect is a recurrent theme in the study of matrices, which leads us to the question: how are these operations effected? By matrix multiplication. The matrices responsible for effecting the elementary operations are elementary row and column matrices. The first observation is that these matrices must be square. The exact form these matrices take is given below:

1. Row interchange: This is a permutation matrix.
2. Row scaling (non-zero): This is a diagonal matrix.
3. Row addition

Row operations are effected using left multiplications of the target matrix with one of the elementary row matrices. The first observation is that all operations are invertible. One can arrive at this observation without doing lengthy calculations: 

1. Applying the row interchange on itself returns the identity matrix.

   $EE = I$

2. Scaling by the inverse returns the same matrix.

   $diag\{a_1, ..., a_n\} \times diag\{b_1, ..., b_n\} = diag\{a_1b_1, ..., a_nb_n\}$

3. Negative addition returns the same matrix.

Thus the inverse of each elementary operation is another elementary operation of the same type.

Column operation are effected by right-multiplications with the target matrix.

> The rank of a matrix is invariant under the operation of multiplication with invertible matrices.

Since elementary matrices are invertible, the above observation suggests a method to compute the rank. 

### Rank-matrix

This has its origin in solving simultaneous equations using Gaussian elimination. 

> The rank of a row-echelon matrix is equal to the number of non-zero rows.

The rank is bounded above by the number of non-zero rows. Since the matrix is row-echelon, each row contributes exactly one unit to the dimension of the range space. One way to understand this is by trying to arrive at the basis vectors of the range space. If column operations are also permitted, any $M \times N$ matrix  $A$ of rank $n$ can be reduced to the following form by a series of elementary matrix operations.


$$
E_1E_2...E_i \ A \  E_{i+1}E_{i+2}...E_{i+k} = \begin{bmatrix}       I_{n \times n} \ \ \ \  0_{n \times N-n}\\ 
			        0_{M-n \times n} \ \ \ \ 0_{M-n \times N-n}
\end{bmatrix}
$$
The resultant matrix, which we will call rank-matrix of $A$ is also of rank $n$. This gives us a clear procedure to compute the rank of a matrix. A series of very simple, elementary operations have resulted in an extremely powerful result. Atoms are the building blocks of nature. Elementary matrix operations build matrices. To see why this is true, let us reconstruct $A$ from the rank-matrix of $A$. Since elementary matrices are invertible, we can rewrite the above equation as follows:
$$
A  = E_1^{-1}E_2^{-1}...E_i^{-1}      \begin{bmatrix} 
					I_{n \times n} \ \ \ \  0_{n \times N-n}\\ 
			        	0_{M-n \times n} \ \ \ \ 0_{M-n \times N-n}
			       \end{bmatrix} E_{i+1}^{-1}E_{i+2}^{-1}...E_{i+k}^{-1}
$$
This can be viewed as a generative process to arrive at any arbitrary matrix of a given rank. The exact operations are not important, but it gives us a good idea of how elementary matrices "build" matrices.

One interesting observation here is that the transpose operation preserves the rank of the rank-matrix. From the above equation it follows that the transpose preserves the rank of any matrix provided the transpose of an invertible matrix is also invertible. Let us see if this is the case:
$$
\begin{align}
I &= AA^{-1}\\
I &= (AA^{-1})^T = (A^{-1})^T A^T\\
I &= (A^T)^{-1}A^T
\end{align}
$$
From the above equations it is clear that

> A matrix is invertible *iff* its transpose is invertible.

We have used the fact that $(A^T)^{-1} = (A^{-1})^T$. Thus:

> The rank of a matrix is invariant under the operation of transpose, or $rank(A^T) = rank(A)$.

Thus the rank of a matrix is also equal to the dimension of the span of the row space. It is also equal to the following:

1. The number of linearly independent rows.
2. The number of linearly independent columns.

### Matrix Inverse

Now, if the matrix $A$ is invertible, then it has full rank, and its rank matrix is just the identity matrix. The above equation becomes:


$$
\begin{align}
A  &= E_i^{-1}E_{i-1}^{-1}...E_1^{-1}\ \  I\ \  E_{i+k}^{-1}E_{i+2}^{-1}...E_{i+1}^{-1}\\
     &= F_1 F_2...F_i \ \ F_{i+1} F_{i+2}...F_{i+k}\\
 \end{align}
$$
An invertible matrix can be expressed as a product of elementary matrices. This immediately suggests the following result:

> A matrix is invertible *iff* it can be expressed as a product of elementary matrices.

The above equation suggests something more - a procedure to compute the inverse of the matrix using elementary row and column operations.
$$
\begin{align}
F_{i+k}^{-1} F_{i+k-1}^{-1}...F_{1}^{-1} A &= I\\
F_{i+k}^{-1} F_{i+k-1}^{-1}...F_{1}^{-1} I &= A^{-1}
\end{align}
$$
A sequence of elementary operations on $A$ that produces the identity matrix, when applied on the identity matrix, produces the inverse of $A$.

We started with computing the rank of a matrix, and that has led us to a method to compute the inverse of a matrix. We have done all this with the help of elementary matrix operations. Small things can often be incredibly powerful.

### Determinants

The determinant is another operation on a matrix that is defined recursively. For an $n \times n$ matrix
$$
\text{det}(A) = \sum \limits_{j = 1}^{n} (-1)^{i+j} A_{ij}\  \text{det}(\bar{A_{ij}})
$$
where $\bar{A_{ij}}$ is the cofactor matrix which is obtained by eliminating row $i$ and column $j$ from matrix $A$.  

For a two dimensional square matrix $A = [v_1, \ \ v_2]$ with column vectors $v_1$ and $v_2$, the column vectors represent the sides of a parallelogram. The vectors $[1, 0]$ and $[0, 1]$ are transformed into $v_1$ and $v_2$ respectively. The area of the square formed by the basis vectors prior to the transformation is 1. $|\text{det}(A)|$ gives the area of the parallelogram with sides $v_1$ and $v_2$, while $\text{sign}(\text{det}(A))$ gives the orientation of the transformed vectors.

For a more intuitive understanding of what determinants are refer [3Blue1Brown](https://www.youtube.com/watch?v=Ip3X9LOh2dk&index=7&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab). Roughly speaking, the determinant of a square-matrix of size $n$ is the signed $\text{n-dimensional}$ volume of $\text{n-dimensional}$ parallelepiped formed by the columns of $A$. To understand why the determinant is computed in this way, refer [exterior algebra](https://en.wikipedia.org/wiki/Exterior_algebra).

### Properties of determinants

Instead of dealing with a matrix, we can work with a collection of column vectors:

If $A = [v_1, v_2, ..., v_n]$, then $\text{det}(A) = \text{det}(v_1, v_2, ..., v_n)$. 

There are two fundamental properties:

1. $\text{det}(v_1, ..., v_i + \alpha\  v_j, v_{j+1}, ..., v_k) = \text{det}(v_1, ..., v_i, v_{j+1}, ..., v_k) + \alpha\  \text{det}(v_{1}, ..., v_{j}, v_{j+1}, ... v_k)$
2. $\text{det}(v_1, ..., v_i, ..., v_j, ..., v_n) = -\text{det}(v_1, ..., v_j, ..., v_i, ..., v_n)$

Determinants are not linear, but exhibit linearity through the column vectors. Determinants are anti-symmetric.

Since elementary matrices have occupied so important a place in much of our discussion on matrices, what are the determinants of elementary matrices?

1. The first row-operation reverses the sign of the determinant.
2. The second row operation just scales the determinant by the same constant the row was scaled by. 
3. The third row operation leaves the determinant unchanged.

The determinant of the elementary matrices are $-1$, $\alpha$ and $1$ respectively.

From this we get our fourth property:

> $\text{det}(EA) = \text{det}(E) \text{det}(A)$

If $A$ is an invertible matrix, then $A = E_1 E_2 ... E_n$ where the $E_is$ are elementary matrices. 

$\text{det}(A) = \prod \limits_{j = 1}^{n} \text{det}(E_j) \neq 0$

And so our fifth property reads:

> If a matrix is invertible, its determinant is non-zero.

Is the converse of this statement true? Let us check.

First we perform an elementary matrix factorization of $A$.

$A = E_1... E_i A_r E_j...E_n$, where $A_r$ is the rank-matrix of $A$. Since all matrices other than $A_r$ are elementary matrices, $\text{det}(A)$ is a product of non-zero determinants with $\text{det}(A_r)$ whose value is not known to us. But $\text{det}(A) \neq 0 \implies \text{det}(A_r) \neq 0$. Since $A_r$ is a diagonal matrix with only ones and zeros along the diagonal, it has to be the identity for the determinant to be non-zero. Thus $A$ is invertible.

> A matrix is invertible *iff* its determinant is non-zero.

Now we come to the determinant of the product of two matrices : $\text{det}(AB)$

If $A$ and $B$ are both invertible, then $AB$ is just a product of elementary matrices, and so$\text{det}(AB) = \text{det}(A) \text{det}(B)$

If one of $A$ and $B$ is only invertible, then $L_{AB}$ does not have an inverse, thus $\text{det}(AB) = 0$. Our sixth property:

> $\text{det}(AB) = \text{det}(A) \text{det}(B)$

Now we come to the transpose. If $A$ is invertible, then 

$\text{det}(A^T) = \prod \limits_{j=1}^n \text{det}(E_j^T)$

If $A$ is not invertible, then its transpose is also not invertible, and both determinants equal zero. Combining these two observations we get our seventh property:

> $\text{det}(A^T) = \text{det}(A)$

One more interesting property. If two square matrices are similar, then they essentially represent the same linear transformation albeit in different bases. The observation is that the determinant of similar matrices is the same:

If $A$ is similar to $B$, then there exits an invertible matrix $Q$ such that $A = Q B Q^{-1}$.

Taking determinant on both sides, our eighth and final property:

$\text{det}(A) = \text{det}(Q A Q^{-1}) = \text{det}(B)$

Summarizing the eight properties:

1. $\text{det}(v_1, ..., v_i + \alpha\  v_j, v_{j+1}, ..., v_k) = \text{det}(v_1, ..., v_i, v_{j+1}, ..., v_k) + \alpha\  \text{det}(v_{1}, ..., v_{j}, v_{j+1}, ... v_k)$
2. $\text{det}(v_1, ..., v_i, ..., v_j, ..., v_n) = -\text{det}(v_1, ..., v_j, ..., v_i, ..., v_n)$
3. $\text{det}(E_1) = -1;\ \text{det}(E_2) = \alpha;\ \text{det}(E_3) = 1$
4. $\text{det}(EA) = \text{det}(E)\text{det}(A)$
5. $A$ is invertible *iff* $\text{det}(A) \neq 0$
6. $\text{det}(AB) = \text{det}(A) \text{det}(B)$
7. $\text{det}(A^T) = \text{det}(A)$
8. If $A$ and $B$ are similar, $\text{det}(A) = \text{det}(B)$


---

### Cramer's Rule

Cramer's rule is a cumbersome computational tool to compute the inverse of a matrix. But its derivation is quite interesting. We will do the derivation for a $3 \times 3$ matrix, $A$.
$$
A =
	\begin{bmatrix}
		a & b & c\\
		d & e & f\\
		g & h & i
	\end{bmatrix}
$$
Now replace the first row by the second row:
$$
\bar{A} =
	\begin{bmatrix}
		d & e & f\\
		d & e & f\\
		g & h & i
	\end{bmatrix}
$$
Clearly, $\text{det}(\bar{A}) = 0$

We will make use of this fact and expand the determinant of $\bar{A}$ on the first row.
$$
0 = \text{det}(\bar{A}) = d A_{11} -eA_{12} + f A_{13}
$$
, where $A_{ij}$ is the cofactor of the $ij^{th}$ element.

In a similar manner, replace the first row by the third row and expanding on the first, we get:
$$
0 = \text{det}(\bar{A}) = g A_{11} -hA_{12} + i A_{13}
$$
Doing similar operations on the second row:
$$
0 = \text{det}(\bar{A}) = -a A_{21} + bA_{22} - c A_{23}\\
0 = \text{det}(\bar{A}) = -g A_{21} + hA_{22} - i A_{23}
$$
And for the third row:
$$
0 = \text{det}(\bar{A}) = a A_{31} - bA_{32} + c A_{33}\\
0 = \text{det}(\bar{A}) = d A_{31} - eA_{32} + f A_{33}
$$
We also have three equations for the determinant of $A$. For convenience, we shall list down the six equations obtained till now.
$$
a A_{11} - bA_{12} + c A_{13} = \text{det}(A)\\
-d A_{21} + eA_{22} - f A_{23} = \text{det}(A)\\
g A_{31} - hA_{32} + i A_{33} = \text{det}(A)\\
$$

$$
d A_{11} -eA_{12} + f A_{13} = 0\\
g A_{11} -hA_{12} + i A_{13} = 0\\
-a A_{21} + bA_{22} - c A_{23} = 0\\
-g A_{21} + hA_{22} - i A_{23} = 0\\
a A_{31} - bA_{32} + c A_{33} = 0\\
d A_{31} - eA_{32} + f A_{33} = 0
$$

This can be expressed compactly as the product of two matrices:
$$
\begin{align}
\begin{bmatrix}
a & b & c\\
d & e & f\\
g & h & i
\end{bmatrix}
\begin{bmatrix}
A_{11} & -A_{21} & A_{31}\\
-A_{12} & A_{22} & -A_{32}\\
A_{13} & -A_{23} & A_{33}
\end{bmatrix}
&= 
\begin{bmatrix}
\text{det}(A) & 0 & 0\\
0 & \text{det}(A) & 0\\
0 & 0 & \text{det}(A)
\end{bmatrix}\\\\
&= \text{det}(A) I
\end{align}
$$
The second matrix on the left is the transpose of the cofactor matrix, and is called the adjoint of A.
$$
A\ \text{adj}(A) = \text{det}(A) I
$$
If $A$ is invertible, then $\text{det}(A) \neq 0$. Which gives us:


$$
A^{-1} = \frac{1}{\text{det}(A)}\  \text{adj}(A)
$$
This gives us another computational procedure to find the inverse of a matrix.

---

### System of Linear Equations

If $A$ is an $m \times n$ matrix of coefficients, and $x$ is an $n$ dimensional vector of unknowns, and $y$ is an $m$ dimensional vector, then the system is specified by 
$$
A x = y
$$
If this system has a solution then $y$ is in the span of the columns of $A$. This will certainly happen if the rank of $A$ is greater than or equal to $m$. Thus $\text{rank}(A) \geq m$ is a sufficient condition for a solution to exist. Let us look at the traditional way of studying the three cases of $n = m$, $n > m$ and $n < m$.

1. **Overdetermined system**: more equations than unknowns ($m > n$): Take the following example:

   ​
   $$
   \begin{bmatrix}
   	1 & 2\\
   	3 & 1\\
   	2 & 4\\
   	6 & 2
   \end{bmatrix}
   \begin{bmatrix}
   	x_1\\
   	x_2\\
   \end{bmatrix}
   =
   \begin{bmatrix}
   4\\
   8\\
   8\\
   16
   \end{bmatrix}
   $$
   ​

   This system has a unique solution $x_1 = 2,\ x_2 = 1$. The rank of $A$ is $2$. Though the rank of $A$ is less than $m = 4$, the system has a solution. Thus $rank(A) \geq m$ is not a necessary condition for a solution to exist.

   Consider another example:

   ​
   $$
   \begin{bmatrix}
   	1 & 1\\
   	1 & 2\\
   	1 & 3\\
   	1 & 4
   \end{bmatrix}
   \begin{bmatrix}
   	x_1\\
   	x_2\\
   \end{bmatrix}
   =
   \begin{bmatrix}
   2\\
   3\\
   4\\
   6
   \end{bmatrix}
   $$
   This system has no solution.


1. **Underdetermined system**: fewer equations than unknowns ($m < n$): 

   Consider this example
   $$
   \begin{bmatrix}
   	1 & 1 & 1 & 1\\
   	1 & 2 & 1 & 1\\
   \end{bmatrix}
   \begin{bmatrix}
   	x_1\\
   	x_2\\
   	x_3\\
   	x_4
   \end{bmatrix}
   =
   \begin{bmatrix}
   4\\
   5
   \end{bmatrix}
   $$
   This has at least two solutions, $x_1 = x_2 = x_3 = x_4 = 1$ and $x_1 = x_2 = 1, x_3 = 2, x_4 = 0$. Here the rank of $A$ is 2, but the solution is not unique. In fact there are infinitely many solutions to this system. Here is the argument. Since the rank of $A$ is 2, its nullity is $4$. If $x$ is a solution, $x + h$ is a solution.

   Another example:
   $$
   \begin{bmatrix}
   	1 & 1 & 1 & 1\\
   	1 & 1 & 1 & 1\\
   \end{bmatrix}
   \begin{bmatrix}
   	x_1\\
   	x_2\\
   	x_3\\
   	x_4
   \end{bmatrix}
   =
   \begin{bmatrix}
   4\\
   5
   \end{bmatrix}
   $$
   Here no solutions exist. 

   ​

2. **Exactly-determined system**: number of equations equal to number of unknowns ($m = n$):

   If $A$ is full-rank, then a unique solution exists.

   If $A$ is not full-rank, then its row-echelon form will have rows which are zeros. If the zero-rows do not have corresponding zeros in $y$, then no solutions exist. If they are also zero, remove these rows from the matrix. The resulting matrix is full-rank, and has a unique solution. But the variables corresponding to the zero-rows can assume any value, resulting in an infinite number of solutions.

---

### Summary

In this chapter we have studied the computational side of linear transformation with the help of matrices. The chapter began by stressing the importance of the correspondence between linear transformations and matrices. The first property of interest to us was the rank of a matrix. We briefly studied the beautiful properties of elementary row and column operations. That not only helped us understand the rank of a matrix, it also gave a generative view of matrices. The power of elementary matrices was seen in its ability to give us an algorithm to compute the inverse of a matrix. We then proceeded to study determinants. A very brief geometric intuition was given. The focus was on the surprising algebraic properties of determinants. The chapter closes with another method to compute the inverse of a matrix, this time using determinants.

**Key words**

rank, elementary matrices, row-echelon form, rank-matrix







