# Linear Transformations

[TOC]

Up to this point we have tried to understand a vector space as an isolated entity. But again, a vector space like $\mathbb{R^2}$ is one among an infinite collection of vector spaces. It is natural to study the interaction between vector spaces, and the mathematical apparatus that enables this interaction is a function. Here again, a simple function between two subsets is not likely to be interesting. We turn to a much more powerful function, one that preserves the linearity of vector spaces. We call them linear transformations.

---

## Definition

---

## Examples


 -  Dilation of vectors: $T(x) = \alpha x$.
 -  Rotations are linear transformations - rotate the sides of the parallelogram and adding the sides is the same as adding the sides and then rotating it. Reflections in \mathbb{R^2} through any line passing through the origin is as good as a rotation by twice the angle made by a line connecting the origin and this point with the line of reflection.
 -  Every matrix is a linear transformation.
 -  Permutations are linear transformations. A permutations is a matrix. This is a deductive argument. Visually, you are just manipulating the order of elements in a tuple; how does it matter if you add two tuples and reorder them or permute them post addition, so long as the integrity of the ordering is maintained in either case?
 -  The most interesting example is the derivative operator on the space of polynomials, which is clearly linear. $D : P^{n}(x) \rightarrow P^{n-1}(x)$
 -  Projection and inclusion are linear transformations.
 -  Any change of units is a linear transformation. A transformation from the space of "atoms" to the space of "elementary particles" is linear. Conversion from inches to feet, from kg to g are similar examples.


Examples serve a very important purpose. Besides being the material out of which the knower builds his mathematical intuition, examples act as powerful tools against which we can test our fledgling ideas. One good counterexample can save hours of misapplied efforts at trying to prove an incorrect proposition. We can demonstrate the truth of both these statements. When we are required to reason about $\mathbb{R^n}$, the immediate image that comes to our mind is $\mathbb{R^3}$ or $\mathbb{R^2}$. This is especially true when we are dealing with geometric properties like the distance between two vectors in a metric space.

Examples that exemplify a concept should preferably come in large numbers. This is for two reasons. Firstly, the variety helps to establish the wideness and scope of the concept. The more areas the concept spans, the greater is its power. Secondly, multiple instantiations of a concept prevent the possibility of a too narrow and naive understanding.

This work, titled [Exemplification in Mathematics Education](http://mcs.open.ac.uk/jhm3/PME30RF/PME30RFPaper.pdf), presents a wonderful survey on the importance of examples. Two terms stand - *concept image* and *personal example space*. A concept image is the complete cognitive structure associated with a concept. Personal example space is the repertoire of examples that the learner has access to at any time.

> **Sri Aurobindo** : The experience of reasoning and its errors should be given to the mind and it should be taught to observe how these work for itself; it should proceed from the example to the rule and from the accumulating harmony of rules to the formal science of the subject, not from the formal science to the rule, and from the rule to the example

From the document - "Extending example spaces as a learning/teaching strategy in mathematics":

> **The role of examples in mathematics**
>
> It is has long been acknowledged that people learn mathematics principally through engagement with examples, rather than through formal definitions and techniques.  Indeed, it is only through examples that definitions have any meaning, since the technical words of mathematics describe classes of objects or relations with which the learner has to become familiar.

---

## Properties

Here we proceed with the usual questions that we can ask about functions. What happens if the function is injective, surjective or bijective? We will ask each of this questions for the linear transformation and see what we get. For all discussions in this section it is assumed that $T : V \rightarrow W$ is a linear transformation from $V$ to $W$.

**Injective linear transformation**

> $T$ is injective iff $T(x_1) = 0 \text{ and } T(x_2) = 0 \implies x_1 = x_2$ 

---

> $T$ is injective iff $T(x) = 0  \implies x = 0$ 

**Surjective linear transformation**

> If $T$ is surjective, $dim(W) \leq dim(V)$

**Bijective linear transformation**

> If $T$ is bijective, $T^{-1}$ exists, and is a linear transformation.

---

> If $T$ is bijective, $dim(V) = dim(W)$.

---

> Let $dim(V) = dim(W) = n$ and $B_{V} = \{v_1, ..., v_n\}$ be a basis of $V$ and $B_{W} = \{w_1, ..., w_n\}$ be a basis of $W$, then there exists a linear transformation with $T(v_i) = w_i$.

---

> **Definition** : A bijective linear transformation is called an **isomorphism**.

---

> **Definition** : Two vector spaces are **isomorphic** if there exists a bijective linear transformation from the one to the other.

---

Now we will see if linear transformations in general have anything special about them. We won't impose the injectivity or surjectivity constraints apriori, but give them their place if they evolve naturally.

Let $T : V \rightarrow W$ be a linear transformation, with $B_V = \{v_1, ..., v_n\}$ as a basis for $V$. Since $T$ need not be surjective, let us restrict our attention to the range of $T$. Denote this by $R(T) = \{y \ \big| \ T(x) = y \text{ for some } x \in V\}$. Observe that $R(T) = span(\{T(v_1), ..., T(v_n\})$. Clearly, $R(T)$ is a subspace.

> **Definition** : $R(T)$ is called the range space of $T$.

 The next question we can ask is if $\{T(v_1), ..., T(v_n\}$forms a basis for $R(T)$. If it does, then the following results apply:
$$
\begin{align}
a_1T(v1) + ... + a_nT(v_n) &= 0 \implies a_i = 0 \text{ for } i = 1, ..., n\\
T(a_1v1 + ... + a_nv_n) &= 0 \implies a_i = 0 \text{ for } i = 1, ..., n]\\
T(x) &= 0 \implies x = 0
\end{align}
$$
This implies that $T$ is injective, and $T : V \rightarrow R(T)$ is a bijection. The converse is also true: if $T$ is injective then $dim(R(T)) = n$. So we get:

> $T : V \rightarrow W$ is injective iff $dim(R(T)) = dim(V)$.

In the most general case, if $T$ is not injective, then we have some $x \in V$ such that $T(x) = 0 \text{ and } x \neq 0$. At this step there is a beautiful observation about the nature of $T$. If $T(x) = 0$ and $T(y) = 0$, then $T(x + \alpha y) = 0$. In other words, $\{x \big| T(x) = 0, x \in V\}$ is a subspace of $V$. We call this the null-space of $T$, denoted by $N(T)$:

> **Definition** : The **null space** of a linear transformation is the set of elements that are mapped to zero.

We now have two subspaces to work with - $N(T)$ and $R(T)$.
$$
\begin{align}

N(T) &= \{x \big| T(x) = 0, x \in V\}\

R(T) &= span(\{T(v_1), ..., T(v_n)\})

\end{align}
$$
If $v$ is an element in a basis of $N(T)$, then $T(v) = 0$. If this element is also found in the current basis that we have chosen, $B_V$, then $T(v)$ is in the spanning set and can be comfortably removed without loosing the spanning property. Then we would be one step closer to a basis for $R(T)$. Let us see if we can reach there. 

Consider the following argument : Since $B_{V}$ is a basis of the entire vector space, it is reasonable to suppose that it contains the basis of any subspace of $V$. But we need to prove this result:

> Can every basis of a vector space be reduced to a basis of any of its subspaces? 

$\{(0, 1), (1, 0)\}$ is a basis of $\mathbb{R^2}$. But neither element in the basis can act as a basis for the subspace $\{(x, x) \big| x \in \mathbb{R}\}$. This is not true!

Clearly, restricting a basis is not going to work. The natural option is to extend a basis of the null space to one for the vector space.

Let $B_{N(T)} = \{v_1, ..., v_k\}$ be a basis for the null space. Now extend this to arrive at a basis for $V$ - $B_V = \{v_1, ..., v_k, v_{k+1}, ..., v_n\}$. Now
$$
\begin{align}
T(B_V) &= \{T(v_1), ..., T(v_k), T(v_{k+1}), ..., T(v_n)\}\\
&= \{0, T(v_{k+1}), ..., T(v_n)\}
\end{align}
$$
A few more computations will convince the reader that $\{T(v_{k+1}), ..., T(v_n)\}$is a basis for $R(T)$.

And so we arrive at the theorem:

> **Rank-nullity theorem** : $dim(V) = dim(N(T)) + dim(R(T))$




The rank-nullity theorem can be visualized as a process that takes basis vectors from the domain, squishes a subset - the null space - into the null-vector of the co-domain, and with the remaining vectors, spans the range - range-space - of the linear transformation.


![](https://i.imgur.com/OfhykV5.png)

When presented in this way, the rank-nullity theorem is no longer viewed as yet another mathematical theorem that has to be committed to memory, but forms the essence of how linear transformations work, something without which the understanding of the concept will be incomplete. Theorems should not be introduced as topics in the syllabus for the examination, but as integral parts of the concepts being developed. The sacred triplet of definition, theorem and proof is a central principle of abstract mathematics and has been the pedagogical framework for teaching it to students. Though it has greatly condensed mathematical communication, it has stifled the soul of mathematics. The joy of teaching and learning mathematics lies in the progressive emergence of beautiful patterns as the theory unfolds; the thrill lies in the discovery of the unexpected. The definition-theorem-proof framework makes learning mathematics very mechanical and predictable : the student creates a mental checklist as he learns the subject - every definition goes into one bucket, theorems go into another, and the really diligent student maintains a bucket for proofs, the rest find it an unnecessary burden. This is completely contrary to the way mathematicians do mathematics.

Mathematics textbooks play an important role in the persistence of this framework. Besides being the study material for students, textbooks double up as teaching guides for teachers. The average school teacher or college lecturer relies heavily on the textbook. It not only provides the content for the classes, but also informs the teacher's pedagogical approach. An unoriginal teacher may well be a clone of the textbook's author, each chapter and section being animated by him in front of his students. A poorly written book in the hands of such a teacher is a nightmare to the students. Recruiting first class teachers for all schools is not a practicable solution; there is already a shortage for teachers. What we can do is to put good textbooks in the hands of all teachers. This greatly simplifies the problem, and strikes two birds with a single stone - the student has in front of him a natural, engaging presentation of mathematics, the teacher has with her an illuminating guide that she can safely follow.

The presentation of mathematics need not restrict itself to a book. It can use every medium at its disposal - podcasts, animations, 3-D models, anything that can carry the idea to the student with clarity and appeal. Nor does it need to exclusively work with only one medium. The ideal textbook would be a portal with text, pictures and animations, woven seamlessly into one grand piece of presentation. Such a virtual textbook is bound to capture the imagination of even the math-phobic students.

The community of teachers needs to open its eyes to the new possibilities that the internet has enabled. This new endeavor demands a great and exacting labor, but the old methods have let us high and dry.

---

**Ordered Basis, Column Vectors**

A basis greatly simplifies the representation of vectors. Each vector has a unique representation given a basis. For finite dimensional vector spaces, we can ask for something more - order. This is the next principle that we will be invoking. Efficiency led us to the idea of basis. An ordered efficiency results in an ordered basis. 
Given a basis $B = \{b_1, b_2, ..., b_n\}$ for a n-dimensional vector space, an ordered basis is a specific ordering of the elements of the basis. The moment we impose this ordering, the idea of the basis recedes into the background. That doesn't mean that it disappears. On the contrary, it becomes something something implicit. As its name repeatedly suggests, a basis is the support of a vector space. With an ordered basis, we can begin to comfortably deal with the contents within the buckets, without being troubled by the buckets themselves. This is well expressed in the Japanese principle of Seiton - everything in its place, and a place for everything. The moment you have a place for everything, the acts of retrieval and deposition become automatic, the actual location designated to hold the object is gently pushed to the background, and all that matters is the object that we need to deal with.

When we started, the vector space seemed like a colossal building teeming with innumerable vectors. We could not parse their language, or pin down their motives. But gradually, by the principles of analysis, synthesis, efficiency and order, we have managed to understand them more intimately, more clearly. The vector space is still the giant structure that it was when we began our exploration, but it is less imposing.

---

**Matrices and Linear Transformations**

Let $T : V \rightarrow W$ be a linear transformation. The linear transformation is completely specified if the elements $T(b_1), T(b_2), ..., T(b_n)$ is known, where the elements $b_i$ form an ordered basis. Using the notation of column vectors that we have defined we have the following expression: for any column vector $x = [x_1, x_2, ..., x_n]^T$ in $V$, the image of the linear transformation is another column vector $y = [y_1, y_2, ..., y_m]$ in $W$. Thus we have:

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

We can give this an alternate representation by grouping all the $x_i$s together. This makes sense since the $x_i$s form a column vector in the domain, the $y_i$s form the corresponding column vector of the range. Note that both these column vectors keep changing. The only thing that remains is the constant column vectors of the linear transformation on the basis elements. These can be clubbed together into what is called a matrix.
$$
\begin{bmatrix}
       y_{1} \\
       y_{2} \\
       \vdots \\
       y_{m}
     \end{bmatrix}  = \begin{bmatrix}
       a_{11} & a_{12} & \cdots & a_{1n} \\
       a_{21} & a_{22} & \cdots & a_{2n} \\
       \vdots & \vdots & \vdots & \vdots\\
       a_{m1} & a_{m2} & \cdots & a_{mn}
       \end{bmatrix}  \begin{bmatrix}
       x_{1} \\
       x_{2} \\
       \vdots \\
       x_{n}
     \end{bmatrix}
$$
In this equation we see that the linear transformation is clearly associated with the matrix. All other operations follow. Matrix multiplication is a result of composition of linear transformations, and that is the reason we define matrix multiplication in that weird way. In fact matrix multiplication should be defined simply with a column vector - this is nothing but weighting each column of the matrix with its corresponding element in the column vector, and then adding the resulting column vectors together.

The reverse process is to assign a linear transformation for every matrix.

If $A$ is an $m \times n$ matrix, $L_{A} : \mathbb{R}^n \rightarrow \mathbb{R}^m$ is the corresponding linear transformation, with $\alpha$ and $\beta$ being the standard bases for the two spaces. $[L_{A}]_{\alpha}^{\beta} = A$.

The principle that is being worked out here is "correspondence". Since linear transformations and matrices are intimately related, properties that hold for one type naturally hold for the other. Thus associativity of composition for linear transformations is equivalent to the associativity of matrix multiplication, and the inverse of a linear transformation is related to the inverse of a matrix.

---

**Moving between Bases**

Given that there are infinite bases for a finite dimensional vector space, a natural question that arises is "how do we move between the different bases in a vector space?". A vector will have two different column vectors associated with the bases $\beta$ and $\beta^{'}$ respectively. How are these two column vectors related? They are related by the change-of-coordinate matrix $[I_{V}]_{\beta}^{\beta^{'}}$. This is the matrix corresponding to the identity transformation. A notable property is that the change-of-basis matrix is invertible. What about the matrix representations of a linear transformation in different bases? How are they related? $[T]_{\beta^{'}}^{\beta^{'}} = Q [T]_{\beta}^{\beta} Q^{-1}$. This brings us to the notion of similar matrices. Note that the two matrices correspond to the same linear transformation. Another interesting fact is that every invertible matrix can be associated with a change-of-coordinate matrix. Thus, two matrices $A$ and $B$ are similar, if for some invertible matrix $Q$, $B = Q A Q^{-1}$.

---
