# Vector spaces

[TOC]

> Give a brief history of the development of this subject? Specifically, how did the idea of vector spaces evolve over time and reach its current form?

## Vectors

> What is a vector?

Answer:

> **Definition-1** - A vector is an ordered collection of entities. 

This is an algebraic definition.

*Example1.1*:  $\ V = \{(x, y, z) | x, y, z \in \mathbb{R}\}$ is the set of tuples $(x, y, z)$, each of which is a vector.

*Example1.2*: $\ P = \{a_0 + a_1x + a_2x^2\ | a_0, a_1, a_2 \in \mathbb{R}\}$ is the set of second degree polynomials. Any polynomial in $P$ can in fact be represented by the ordered tuple $(a_0, a_1, a_2)$. It follows that $P$ and $V$ have the same cardinality.

> **Definition-2** - A vector is a quantity that has a magnitude and a direction.

This is a geometric definition, but less accurate.

##Vector spaces

> What is a vector space?

---

> Why should a vector space be closed under vector-addition and scalar multiplication? Does linearity enter into the definition of closure?

Explore the following analogies:

-  Self-sufficiency - 
  - the process of fusion inside stars
  - sexual reproduction in biological populations
-  Interaction
  - one of the simplest interactions between members of a set is a linear combination.

---

> What are the axioms obeyed by a vector space?

---

> What motivated the choice of axioms? What would happen if some of them were dropped out? 

---

> Give as many examples of vector spaces as possible.

---

## Subspaces

> How does the notion of subspace drive home the importance of closure in the definition of a vector space?

Explore the idea of federal units within a nation-state.

---

> Why study subspaces?

There is a dual process of synthesis and analysis. Vectors aggregate to form vector spaces and this can be thought of as a movement of synthesis. Breaking the vector space down into the smaller aggregates of subspaces, which are themselves vector spaces, uncovers its structure. A subspace is the result of an analysis.

> Unity and Multiplicity

There are two principles in the universal existence that always alternate between each other - unity and multiplicity. The first principle always seeks to unify, to bring together, to transcend superficial differences, and arrive at the essence of things, however disparate they may seem in appearance. The second principle seeks to divide the whole into parts, study each of the parts by a similar process of division, and also understand the interaction between these parts, and their relation to the whole.

The scientist's tryst with matter presents a clear example. He breaks down objects into compounds, compounds into elements, elements into atoms, atoms into elementary particles. At each level in the hierarchy he studies the interactions between entities at that level, all the while trying to understand what effect it has on other levels of the hierarchy. He breaks down water into hydrogen and oxygen, understands each element at the atomic level, comes back to the molecular level and studies the chemical reactions that they take part in.

Likewise the vector space as a concept is an act of generalization, an attempt to unify a lot of mathematical objects sharing similar properties under a common framework. A subspace is the first step in this analysis, where the entity is broken down to study its parts.

---

> List all the subspaces of $\mathbb{R^2}$ and $\mathbb{R^3}$?

First, all lines passing through the origin are subspaces of $\mathbb{R^2}$.

Now consider a subspace $S$ of $\mathbb{R^2}$ that is not present in the above class. Such a subspace exists, namely, the trivial subspace $\mathbb{R^2}$. For every point $(x, y)$ in $S$, the line $L[(0, 0), (x, y)]$ is a subset of $S$. Without loss of generality assume $y\neq0$. Now consider a point $(X, Y)$ not on $L$. Evoking the closure property, it can be seen that $(1, 0)$ and $(0, 1)$ belong to $S$, and therefore $S = \mathbb{R^2}$.

Every subspace that is not a line is the entire space $\mathbb{R^2}$. It follows that the only subspaces of $\mathbb{R^2}$ are straight lines passing through the origin.

---

> Why is a parabola not a subspace of $\mathbb{R^2}$ even though the points in a parabola seem to satisfy some form of closure?

The type of closure enjoined in vector spaces is linear. If people are grouped based on caste, this group will be closed under the property "caste" but it will not be closed under "language".

---

> Why study interactions between subspaces?

At each level in the hierarchy, different entities never exist in isolation, there is a constant interaction. The intersection among subspaces is effected by the familiar operations of union and intersection. The natural question to ask is : does this interaction preserve the subspace-property?

---

> What can be said about the union and intersection of subspaces?

$X$ and $Y$ are two subspaces of a vector space $V$. 

$X \cap Y$ is also a subspace. It may be the trivial subspace $\{0\}$ if $X$ and $Y$ have no other element in common.

If $X \subseteq Y$ or $Y \subseteq X$, then $X \cup Y$ is a subspace. If this is not the case, then there exist vectors $x$ and $y$ such that $X \cup Y$ is not a subspace. Let $x \in X \cap Y^c$ and $y \in X^c \cap Y$. If $X \cup Y$ is a subspace, the vector $x+y$ has to be in either $X$ or $Y$ or both. If $x+y \in X$, then $y \in X$, which is a contradiction. Likewise if $x+y \in Y$, then $x \in Y$, again a contradiction.

---

There is another curious result about subspaces.

> Let $x$ and $y$ be two elements in a vector space $V$. Let $U$ be a subspace of $V$ such that $x+y \in U$. Then what can we say about the memberships $x \in U$ and $y \in U$.

$(0, 1) + (1, 0) = (1, 1) \in L[(0, 0), (1, 1)]$, but $(0, 1) \text{ or } (1, 0) \notin L$.

Closure shouldn't be confused with its converse :
If $x+y \in U$, a subspace of $V$, then $x$ and $y$ are in $U$.

The interactions that we have studied do not belong to the realm of subspaces. The operations of union and intersection could be done with any two subsets of the vector space. We will return to this point in a while. 

## Linear combination

> Why study linear combination?

Again evoking the double-principles of unity-multiplicity and synthesis-analysis, a linear combination is an even smaller aggregate than the subspace. If the vector space is the some substance, a subspace represents the molecules that make up the substance, a linear combination can be thought of as the elements that make up the compounds. 

---

> What is a linear combination?

---

## Span

> What is the span of a subset?

---

> Why do we study the concept of span?

The rich structure found in a vector space is not just because it is a collection of vectors. If that were all to a vector space, it would be no different from a set. What makes it rich is the interaction between vectors, and the properties that enable this interaction. Therefore, a simple collection of vectors, and a static linear combination of them will reveal nothing. What the concept of span brings to the theory is an infinite variety of combinations, the multifarious interactions that are possible among a handful of vectors. And at this point the synthetic and generative process begins; an ascent to the earlier forms of subspace, and finally the vector space, but through a more primitive, unremarkable form like a subset of vectors. And this generative principle is called the span. The parallel to Nature is striking. Nature begins with a limited number of entities, and performs an infinite number of experiments producing one form after another - all that we see around us is nothing but a span of the primordial elements of the past.

---

> span$(\phi) = \{0\}$ is a convention.

Every subspace is can be written as the span of a set of vectors. 

---

> Let $U$ be the collection of all subspaces that contain $S$. Then the following are true for the span:
>
> - span$(S) \subseteq V,\ \  \forall V \in U$ 
-  span$(S) = \bigcap \limits_{V \in U} V$
-  span$(S)$ is the smallest subspace that contains $S$. 
-  span$(S) = S\  \ \ \text{iff}\ \ \  S$ is a subspace.

---

### Subspace interactions - span

> What could be the right law of interaction among subspaces?

Let us return to our chemistry example. What is the right law of interaction between chemical compounds? A simple union doesn't seem to be of much effect. For example, consider the reaction of the form:

$AB + CD \rightarrow AD + CB$

Simply grouping the molecules $A, B, C$ and $D$ is not going to bring about any effect. Indeed, this is what happens in the union of two vector spaces. Every element $x \in V$ is put alongside $y \in W$. This law of a simple union is sufficient for sets without any structure; but with a powerful structure given by vector spaces, this is simply not enough. 

Going back to the equation, we can parse it as follows: $AB$ gets broken down into $A$, $B$; likewise with $CD$. At the molecular level a recombination takes place to form the new compounds $AD$ and $CB$. This is what we want with our subspaces. Take subspaces $V$ and $W$ at the subspace level; break them down into vectors $x \in V$ and $y \in W$; combine them at the vector level resulting in $x+y$. We can define a new operation "$+$" that produces the intended result.

> If $V$ and $W$ are subspaces of a vector space $U$, then define $V+W$ as follows:
>
> $V+W = \{x + y \ \big|\  x \in V, y \in W\} = \text{span}(U \cup V)$

---

## Linear independence

> Why study the concept of linear independence?

The governing principle behind linear independence is *efficiency* and it follows directly from the span. A set that spans or generates the entire vector space is called the spanning set. Linear independence answers this question : what is the smallest spanning set?

---

> Define linear independence.

---

> The empty set is linearly independent. But the trivial subspace $\{0\}$ is not.

A set $S = \{v_1, v_2, ..., v_n\}$ is linearly dependent if there exists real numbers $a_1, a_2, ..., a_n$ such that 
$a_1v_1 + a_2v_2 + ... + a_nv_n = 0$
For the empty set such numbers cannot be found, and therefore it is linearly independent.

---

> If $S$ is linearly independent, so is any subset of it.	

---

The following results study the interaction between the ideas of "span", the exhaustive principle, and "linear independence", the economical principle. This result aides in the introduction of the basis.

> If $S$ is linearly independent, for any  $S^{'} \subsetneq S$, span$(S^{'}) \subsetneq$ span$(S)$.

---

> If $S$ is linearly dependent, there exists a vector $v$ in $S$ such that
>  span$(S - \{v\}) = $span$(S)$

