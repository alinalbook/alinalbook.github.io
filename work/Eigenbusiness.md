## Eigenbusiness

[TOC]

**Note** : 

- Eigenbusiness is not a real term; it is an umbrella term to refer all eigenthings - eigenvectors, eigenvalues, eigenspaces, eigenbases.
- An endomorphism is a linear transformation from a vector space to itself: $T : V \rightarrow V$ is an endomorphism.

Eigenbusiness continues the study of linear transformations. Matrices was about the computational side of linear transformations. Eigenbusiness is the study of endomorphisms with a special property.

### Eigenvectors and Eigenvalues

If $T : V \rightarrow V$ is a linear transformation, then a non-zero vector $v \in V$ is an eigenvector of $T$ with eigenvalue $\lambda$ if:
$$
Tv = \lambda v
$$
The first question is one that probes the definition: why should the vector be non-zero?

If $v = 0$, then $Tv = \lambda v\ \  \forall \lambda \in \mathbb{R}$.

That seems too trivial to be of any interest. 

The next question is: what is so special about an eigenvector that gives it a special name?

$T$ is an endomorphism. An endomorphism is an interesting transformation since it takes vector from a vector space and maps it to another vector in the same space. This is best understood by visualizing what a linear transformation does to the vectors geometrically. For a very good video of the same, refer [3Blue1Brown](https://www.youtube.com/watch?v=kYB8IZa5AuE&index=4&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab).

Let $V = \mathbb{R^2}$

Consider an endomorphism $T$, whose matrix representation is given by:
$$
\begin{bmatrix}
3 & 1\\
0 & 2
\end{bmatrix}
$$
In the standard basis, the vector $\begin{bmatrix}1 & 0\end{bmatrix}$ is stretched to $\begin{bmatrix}3 & 0\end{bmatrix}$, while the vector $\begin{bmatrix}0 & 1\end{bmatrix}$ is sheared into $\begin{bmatrix}1 & 2\end{bmatrix}$. Given this geometric interpretation, what is happening to an eigenvector of $T$ under it? It just gets scaled along its span. Whatever be the line that vector happens to lie on, the transformation leaves the vector on the same line, scaled by a factor of $\lambda$, which is its eigenvector. Note that $\begin{bmatrix}1 & 0\end{bmatrix}$ is an eigenvector with eigenvalue three. 

That partially answers our question. They are somewhat special, but are they so vital so as to receive a separate name? This can be answered only if we see what eigenvectors can do. And for this we need to explore, note down the observations, and see if any interesting patterns emerge.

---

### Characteristic Polynomial

Let us start probing. Since the eigenvalue is more accessible, let us play around with a few values:

1. $\lambda = 0$

   $Tv = 0$. This gives us the following result.

>  The null-space of $T$ is a set of eigenvectors of $T$ with the eigenvalue equal to zero.

2. $\lambda = 1$

   $Tv = v$. If $T$ is the identity transformation, every vector is an eigenvector. Trivial. 

   How about constructing a non-trivial transformation that has an eigenvector with eigenvalue one?

   Consider $T$:
   $$
   \begin{align}
   T : \mathbb{R^2} \rightarrow \mathbb{R^2}\\
   [T]_{\beta}^{\beta} = \begin{bmatrix}
   					1 & 2\\
   					0 & 3
   				 \end{bmatrix}
   \end{align}
   $$
   Every vector on the $\text{x-axis}$ is an eigenvector with eigenvalue one.

3. $\lambda = -1$

   $Tv = -v$. If $T = -I$, then every vector is an eigenvector under this transformation.

So far so good. But these examples do not give us a general idea since most of them result in very trivial cases. The particular cases haven't been illumining, let us return to the general. The first case gives us a hint for the next question.

What about the set of all eigenvectors of $T$, does it form a subspace of $V$? Let us inspect. 

If $u$ and $v$ are eigenvectors with eigenvalues $\lambda_{u}$ and $\lambda_{v}$ respectively, then is $u + v$ an eigenvector?
$$
T(u + v) = Tu + Tv = \lambda_u u + \lambda_v v = \lambda(u + v)
$$
This is always guaranteed if $u$ and $v$ share the same eigenvalue. This leads us to the definition of the eigenspace of $T$ corresponding to an eigenvalue $\lambda$.

> The eigenspace of $T$ corresponding to an eigenvalue $\lambda$ is denoted by $E_\lambda$, and is the set of all eigenvectors with eigenvalue $\lambda$ along with the null vector. It is a subspace of $V$. 
>
> $E_0$ is the null space of $T$.

The next set of questions are quantitative in nature: 

- How many eigenvalues does $T$ have? 
- How many eigenvectors are associated with each eigenvalue? 
- Does each $T$ have at least one eigenvalue-eigenvector pair?

Few quick observations:

- The trivial vector space $V = \{0\}$, with the identity transformation doesn't have any eigenvalue. So a linear transformation can have no eigenvalues. It can have exactly one eigenvalue as in the case of identity transformation.

- The number of eigenvectors for a given eigenvalue is infinite.

  If $v$ is an eigenvector of $T$ with eigenvalue $\lambda$, then $\alpha v$ is also an eigenvector for any non-zero $\alpha$. This is because $T (\alpha v) = \alpha T v = \alpha \lambda v = \lambda T (\alpha v)$. 

- The first bullet answers this question.

The third question was too general.  We can ask a better question

For a non-trivial vector space $V$ does each endomorphism $T : V \rightarrow V$ have at least one eigenvalue-eigenvector pair?

To answer this question, we need to take a closer look at the equation, $Tv = \lambda v$, in its most general case.


$$
\begin{align}
v \neq 0 \text{ and }Tv &= \lambda v		&iff \ \ \ \ \ &(1)\\ 
v \neq 0 \text{ and }Tv    &= (\lambda I) v	&iff \ \ \ \ \ &(2)\\
v \neq 0 \text{ and }Tv - (\lambda I) v &= 0	&iff \ \ \ \ \ &(3)\\  
v \neq 0 \text{ and }(T - \lambda I) v &= 0	&iff \ \ \ \ \ &(4)\\
N(T - \lambda I) &\neq \{0\}	&iff \ \ \ \ \ &(5)\\
T - \lambda I &\text{ is not one-one}	&iff \ \ \ \ \ &(6)\\
T - \lambda I &\text{ is not invertible}	&iff \ \ \ \ \ &(7)\\
[T - \lambda I]_\beta^\beta &\text{ is not invertible}	&iff \ \ \ \ \ &(8)\\
\text{det}([T - \lambda I]_\beta^\beta) &= 0 & &(9)
\end{align}
$$
This is a sequence of nine beautiful arguments that straddles all the topics that we have covered till now. Notice the smooth transition from purely theoretical arguments to purely computational ones. The bridge is provided by argument (8). This provides a method to compute all the eigenvalues of a given linear transformation.

(1) begins with the definition of an eigenvector-eigenvalue pair.

(2) recasts the R.H.S as a scaled identity transformation. The effect of $T$ on its eigenvector is the same as the effect of $\lambda I$.

(3) and (4) combine the two linear transformations into one. The eigenvectors of $T$ become the null-vectors of $T - \lambda I$.

(5) If such an eigenpair exists, then the null space of $T - \lambda I$ must be non-trivial.

(6) This can happen only if $T - \lambda I$ is not one-one.

(7) This can happen only if $(T - \lambda I)$ doesn't have an inverse

(8) This means the matrix of the linear transformation is not invertible.

(9) This leads to the determinant being zero.

>  $\text{det}([T - \lambda I]_\beta^\beta) = 0$ is the characteristic equation with the LHS as the characteristic polynomial.

Let us pause for a brief while and study the characteristic polynomial. The first question that springs up is, what is its degree? Let us start by trying out a few examples.

1. $[T]_{\beta}^{\beta}$ is $1 \times 1$: 

   The polynomial is $a_{11}  - \lambda$ and has degree $1$.

2. $[T]_{\beta}^{\beta}$ is $2 \times 2$: 

   The polynomial is $(a_{11} - \lambda)(a_{22} - \lambda) - a_{12} a_{21}$ and is of degree $2$.

For a $3 \times 3$ matrix, expanding the determinant along any one of the rows involves $2 \times 2$ determinants. These $2 \times 2$ determinants have a degree at most $2$. When multiplied by elements from the first row, the degree can increase by at most $1$. This suggests the following result which can be verified by induction:

> The degree of the characteristic polynomial of an endomorphism on an $n-$dimensional space is $n$.

The characteristic polynomial is of degree $\text{dim}(V)$ in $\lambda$. Therefore, the number of eigenvalues is upper-bounded by the dimension of the underlying vector space. This answers our question about the number of eigenvalues. 

How do we find an eigenvector for a given eigenvalue? This amounts to solving the system of linear equations:
$$
[T - \lambda I]_\beta^\beta v = 0
$$
The next natural question concerns the roots of the polynomial. Consider an arbitrary $2 \times 2$ matrix whose characteristic polynomial is $(a_{11} - \lambda)(a_{22} - \lambda) - a_{12}a_{21}$.  What if $a_{12}a_{21} = 0$? The roots are the diagonal entries. If the matrix is diagonal then the roots of the characteristic polynomial are the diagonal entries.

> The eigenvalues for a diagonal matrix are its diagonal entries.

What about any arbitrary matrix. Expanding the determinant may give us more insight. But expanding the determinant of a fully filled matrix is messy work. Using what we know about diagonal matrices, let us think about arriving at an arbitrary matrix by filling up the zero-holes in a diagonal matrix. Any arbitrary matrix $A$ can be represented as:
$$
A = \begin{bmatrix}
	a_{11} & \cdots  & a_{1n}\\
	\vdots  & \vdots & \vdots\\\
	a_{n1} & \cdots & a_{nn}
	\end{bmatrix}
$$
Start with $diag(\{a_{11}, ..., a_{nn}\})$. Characteristic polynomial of $A_0$ neatly splits into $n$ factors.  Now start plugging some of the holes and expand along the first row. The matrix at this stage is still sparse. The cofactor matrix corresponding to all non-diagonal elements is an $n-1 \times n-1$ matrix, but with two $\lambda$ terms removed, and no new $\lambda$ terms added. This introduces new terms whose degree is at most $n-2$.  This suggests the following hunch:

> The characteristic polynomial is of the form $\prod \limits_{i=1}^{n} (a_{ii} - \lambda) + g(\lambda)$, where $g(\lambda) \in P_{n-2}(\mathbb{R})$.

This fact can be established using induction. Expanding the product in the first term gives us an even more interesting result:

> $\text{det}(A - \lambda I) = (-1)^{n} \lambda + (-1)^{n-1} \text{tr}(A) \lambda^{n-1} + a_{n-2} \lambda^{n-2}  + ... + a_{1} \lambda + \text{det}(A) $

Note that the characteristic equation is quite rich in information:

- Trace
- Determinant
- Eigenvalues

All this computation, however, has not taken us any closer to the roots of the polynomial. This remains an open question at this stage. We will return to it with a few remarks later.

---

### Eigenbasis

The number of eigenvalues of an endomorphism is upper-bounded by the dimension of the underlying vector space. Let us take up an endomorphism $T$, which has $\text{dim}(V) = n$ eigenvalues. Let us look at the eigenspace of each eigenvalue, $E_{\lambda_i}$. We can ask the following question:

Do these eigenspaces have any element other than the null vector in common?

If possible let two eigenspaces have common element other than zero. Then:


$$
\exists \ \ v \in E_{\lambda_i} \cap E_{\lambda_j},\ \ \lambda_i \neq \lambda_j, \ v \neq 0  \\
Tv = \lambda_i v \ \ \ \ \text{and}  \ \ \ \ Tv = \lambda_j v,\ \ \lambda_i \neq \lambda_j, \ v \neq 0  \\
(\lambda_i - \lambda_j) v = 0,\ \ \lambda_i \neq \lambda_j, \ v \neq 0  \\
\text{a contradiction!}
$$
Thus,
$$
\bigcap \limits_{i = 1}^{\text{dim}(V)} E_{\lambda_i} = \{0\}
$$
**Eigenvalues are not very social!** And that brings another interesting question in its wake. Are eigenvectors any more social than their scalar counterparts? In other words, is the set of eigenvectors corresponding to different eigenvalues linearly independent? The aloofness of the eigenspaces seems to suggest that the answer might be in the affirmative.

To simplify things consider an endomorphism on $\mathbb{R^3}$ with $3$ distinct eigenvalues. Take one non-zero vector from each eigenspace - $v_1$ from $E_{\lambda_1}$, $v_2$ from $E_{\lambda_2}$ and $v_3$ from $E_{\lambda_3}$. The set in question is $\{v_1, v_2, v_3\}$.

The vectors are pairwise independent. If $\{v_1, v_2, v_3\}$  is linearly dependent, then $v_3 \in \text{ span}(\{v_1, v_2\})$. We have non-zero scalars $\alpha_1$ and $\alpha_2$ such that:
$$
\begin{align}
v_3 &= \alpha_1 v_1 + \alpha_2 v_2 &(1)\\
\lambda_3 v_3 &= \alpha_1 \lambda_1 v_1 + \alpha_2 \lambda_2 v_2 &(2)\\
v_3 &= \alpha_1{\frac{\lambda_1}{\lambda_3}} v_1 + \alpha_2{\frac{\lambda_2}{\lambda_3}} v_2 &(3)\\
\end{align}
$$
In step (2), we have applied the endomorphism on both sides. If $\lambda_3 = 0$, step (3) is not valid. But if it is zero, then the three vectors are linearly independent.

Since $\{v_1, v_2\}$ is a basis for $\text{span}(\{v_1, v_2\})$, the representation for $v_3$ must be unique. This leads to:
$$
\frac{\lambda_1}{\lambda_3} = 1 \ \ \  \text{and} \ \ \ \frac{\lambda_2}{\lambda_3} = 1\\
\lambda_1 = \lambda_2 = \lambda_3\\
\text{a contradiction!}
$$
Thus $v_3$ is not in the span of $v_1$ and $v_2$. $\{v_1, v_2, v_3\}$ form a linearly independent set, and also a basis for $\mathbb{R^3}$. The basis so formed is called an eigenbasis, for obvious reasons. This argument can be extended to a vector space of any arbitrary but finite dimension through induction.

> Eigenvectors corresponding to distinct eigenvalues are linearly independent.

---

### Diagonalization

It would be interesting to know what the matrix of the endomorphism looks like in the eigenbasis. Let $\beta = \{v_1, v_2, v_3\}$ be an eigenbasis of $V$. Then:
$$
\begin{align}
[T]_\beta^\beta &= \begin{bmatrix}
				\lambda_1 & 0 & 0\\
				0 & \lambda_2 & 0\\
				0 & 0 & \lambda_3
			    \end{bmatrix}\\\\
			  &= \text{diag}(\lambda_1, \lambda_2, \lambda_3)
\end{align}
$$
Surprise! It is a diagonal matrix with the corresponding eigenvalues for its elements. Why would this be a good thing? A diagonal matrix makes computational life so easy. As an example look at the following properties:


$$
\begin{align}
\text{diag}(\lambda_1, \lambda_2, \lambda_3) \begin{bmatrix}
										x_1\\
										x_2\\
										x_3
									\end{bmatrix}
									&= \begin{bmatrix}
										\lambda_1 x_1\\
										\lambda_2 x_2\\
										\lambda_3 x_3
									    \end{bmatrix} &&(1)\\\\
\text{diag}(\lambda_1, \lambda_2, \lambda_3)^n &= \text{diag}(\lambda_1^n, \lambda_2^n, \lambda_3^n) &&(2)\\\\
\text{det}(\text{diag}(\lambda_1, \lambda_2, \lambda_3))  &= \lambda_1 \lambda_2 \lambda_3 &&(3)\\\\
\text{diag}(\lambda_1, \lambda_2, \lambda_3)^{-1} &= \text{diag}\bigg(\frac{1}{\lambda_1}, \frac{1}{\lambda_2}, \frac{1}{\lambda_3}\bigg) \ \ \text{if }\ \ \  \lambda_1 \lambda_2 \lambda_3 \neq 0 &&(4)
\end{align}
$$

One look at the computational compactness that diagonal matrices provide would convince any endomorphism to search for an eigenbasis. If the search is successful then the endomorphism is said to be diagonalized. The Columbuses among endomorphisms are called diagonalizable endomorphisms. The process of discovery is called diagonlization. Formally,

> An endomorphism is diagonalizable if the underlying vector space has an ordered basis in which the matrix representation is diagonal.

Evoking the linear transformation-matrix correspondence, a matrix is said to be diagonalizable if its linear transformation is said to be diagonalizable. Formally, for a square matrix $A$,

> $A$ is diagonalizable if $L_A$ is diagonalizable.

An important point to note here is the use of **if** instead of **iff**. Here we are defining what the term diagonalizable means when applied to matrices; the use of **iff** doesn't make sense since the term has not yet been defined for matrices. This is a definition and not a theorem or a lemma.

We have stumbled upon diagonal matrices by studying the eigenbasis of an endomorphism. This has reoriented the object of our study - it is the process of diagonalization that we wish to study in greater detail now. Since the problem has been redefined we need to search for the best solution that can help us solve it. Constructing an eigenbasis is one way to get a diagonal matrix representation. Are there other ways? Let us probe.

Let $D$ be a diagonal matrix of representation of an endomorphism $T$ in some basis $\beta$.


$$
\begin{align}
[T]_{\beta}^{\beta} &= D\\
D &= \text{diag}(\lambda_1, \lambda_2, ...., \lambda_n)
\end{align}
$$
If $e_i$ is a basis vector, then $D e_i = \lambda_i e_i$; $e_i$ is an eigenvector of $T$ and $\beta$ is an eigenbasis of $T$.

Thus,

> An endomorphism is diagonalizable *iff* it has an eigenbasis.

First we established that if an endomorphism has an eigenbasis, its matrix representation in that basis is diagonal. What we are saying here is that if an endomorphism is diagonalizable, then the basis corresponding to it is an eigenbasis. This makes the link between a diagonal matrix and eigenbasis irrevocable. 

At this stage we can ask one of two questions

1. Given any arbitrary matrix $A$, can it be diagonalized?  
2. Given a diagonalizable matrix, what all properties does it have?

The first question is general in nature. It shelters all possible matrices and tries to extract some rule of separation which will filter out only those matrices that can be diagonalized. The second question is particular in nature. Generally, the second type of questions can be answered with lesser effort than the first. And this happens quite frequently in mathematics: if a question is too broad, then restrict the domain by asking more specific questions. This may not help us answer the original question. But it may open new directions of attack. The way to do good mathematics is to ask a lot of questions that span the entire range of the question-space, right from the most particular and trivial to the most general and difficult. Examples and exercises are in this sense trivial questions. The answers to them may not reveal a lot about the subject, but it may throw some light on narrow bypaths that may prove to be useful in our more difficult explorations.

It is the second question that we will try to answer now.

**Given a diagonalizable matrix, what all properties does it have?**

If $T$ is an endomorphism that is diagonalizable, then how do we compute its diagonal representation? This falls in the domain of matrices, and we will take their help. All that we need to do is a change of basis from the current basis to the eigenbasis. Thus,
$$
D = Q [T]_{\alpha}^{\alpha} Q^{-1}
$$
where, $Q = [T]_{\alpha}^{\beta}$ , $\alpha$ is the non-diagonal basis, $\beta$ is the eigenbasis.

Note that $Q$ is invertible.  Therefore the diagonal matrix is similar to the non-diagonal matrix. This leads to an interesting question. Is the converse true? If a matrix is similar to a diagonal matrix, is it diagonalizable? Let us probe.

Every invertible matrix is a change-of-basis matrix. To see why this is the case, let $A = [v_1, v_2, ..., v_n]$ be an invertible matrix. Then $\beta = \{v_1, ..., v_n\}$ is a basis of $V$. Let the standard basis be $\alpha = \{e_1, ..., e_n\}$. Then,
$$
A = [L_A]_{\alpha}^{\alpha} = [I]_{\beta}^{\alpha}
$$
Thus, if a matrix is similar to a diagonal matrix, then it is diagonalizable. Summarizing the above result in a single neat statement:

> A matrix is diagonalizable *iff* it is similar to a diagonal matrix.

Now that we have a diagonal matrix let us complete the circle and get back to where we started : eigenvalues and eigenvectors.
$$
\begin{align}
D &= Q [T]_{\alpha}^{\alpha} Q^{-1}\\
\end{align}
$$
In the diagonal basis, $\beta$, the column vector $e_i$ is an eigenvector with eigenvalue $\lambda_i$. Using this we see that the columns of $Q^{-1}$ are the eigenvectors of $T$. Recasting the equation and renaming $Q$ by $Q^{-1}$, we get
$$
[T]^{\alpha}_{\alpha} = Q \text{diag}(\lambda_1, ..., \lambda_n) Q^{-1}
$$
with the column vectors of $Q$ giving us the eigenvectors of $T$.

This section on diagonalization has been rich with properties. This is a more or less complete characterization of diagonalizable matrices. It answers two questions:

1. What is a diagonalizable endomorphism? What is a diagonalizable matrix?
2. What are the characteristics of diagonalizable matrices and endomorphisms?

The following are the answers that we have arrived at:

1. An endomorphism $T$ on $V$ is diagonalizable if $V$ has a basis $\beta$ such that, $[T]_{\beta}^{\beta}$ is diagonal.
2. An endomorphism $T$ on $V$ is diagonalizable *iff* if $(V, T)$ has an eigenbasis.
3. An $n \times n$ matrix $A$ is diagonalizable if the endomorphism $L_A$ is diagonalizable.
4. A matrix is diagonalizable *iff* it is similar to a diagonal matrix.
5. Given an $n$-dimensional vector space $V$ with an arbitrary basis $\alpha$, if an endomorphism $T$ is diagonalizable, then $[T]_{\alpha}^{\alpha} = Q\ diag({\lambda_1, ..., \lambda_n})\ Q^{-1}$. Where $Q = [v_1, ..., v_n]$ is an $n \times n$ matrix whose columns are the eigenvectors of $T$ represented in the basis $\alpha$, and $\lambda_i$ is the eigenvalue for $v_i$.

We return to the first question that we asked.

**Given any arbitrary matrix $A$, can it be diagonalized?**  

















