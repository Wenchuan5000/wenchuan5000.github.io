# Interiors and Closures

## Basic Definitions

> #### Definition: Interiors
>
> Let $(X, \mathcal T)$ be a topological space, and let $U \subseteq X$.
> 	
> The **interior** of $A$, denoted $A^\circ$ or $\mathrm{int} (A)$, in $(X, \mathcal T)$ is defined as the union of all open sets contained in $A$. Explicitly, $\mathrm{int}$ can be considered as a mapping from $\mathcal P(X)$ to $\mathcal P(X)$, which is defined as
> $$
> \mathrm{int}(A) := \bigcup (\mathcal P(A) \cap \mathcal T).
> $$

It is a straight conclusion, by the definitioin, that the interior of $A$ is open in $(X, \mathcal T)$.

Note that, for topological spaces $(X, \mathcal T)$ and $(X, \mathcal T')$ with the same set $X$, the interior of a subset $A \subseteq X$ might be different if $\mathcal T \ne \mathcal T'$. For example, if $\mathcal T$ is a discrete topology on $\mathbb R$, and $\mathcal T'$ is the Euclidean topology on $\mathbb R$, then,
$$
\mathrm{int}_{\mathcal T'}([0\ldots 1]) = [0 \ldots 1] \ne (0 \ldots 1) = \mathrm{int}_{\mathcal T}([0 \ldots 1]).
$$
Here, $\mathrm{int}_{\mathcal T}$ and $\mathrm{int}_\mathcal{T'}$ denote the interior mappings in $(X, \mathcal T)$ and $(X, \mathcal T')$ respectively.

Also, note that, for any subset $A, B \subseteq (X, \mathcal T)$, if $A \subseteq B$, then $\mathrm{int} (A) \subseteq \mathrm{int}(B)$. It is a straight consiquence of the definition. But, on the contrary, $\mathrm{int} (A) \subseteq \mathrm{int}(B)$ do not implies $A \subseteq B$. For example, if $\mathcal T$ is a indiscrete topology for $\mathbb R$, then
$$
\mathrm{int}([0\ldots1]) = \emptyset \subseteq \emptyset = \mathrm{int}([1\ldots2]),
$$
but, apparently, none of the intervals contains the other.

> #### Definition: Closures
>
> Let $(X, \mathcal T)$ be a topological space, and let $A \subseteq X$.
>
> The **closure** of $A$, denoted $A^-$, or $\mathrm{cl}(A)$, is defined to be the set
> $$
> \mathrm{cl}(A) := X \setminus \mathrm{int}(A^\complement).
> $$

It is a straight corollary that the closure of any set is closed in its topological space, as the interior of the set is open in the space.

Considering the closure of $A$ as the intersection of all closed sets containing $A$ is a popular alternative definition of closures. Let $\mathcal C$ be the set of all closed sets containing $A$. This condition holds if and only if for any $C \in \mathcal C$, there is a $U \in \mathcal T$, such that $C = X \setminus U$, and $U \subseteq A^\complement$. Let $\mathcal U$ be the set of all such $U$, then the previous condition is equivalent to
$$
\mathrm L(A) = \bigcap \mathcal C = X \setminus \bigcup \mathcal U = X \setminus \mathrm{int}(A^\complement).
$$
By this alternative definition, we know that a set is closed in its topological space if and only if its closure is itself.

Another equivalent definition of closures is to consider the closure of any set $A$ as the union of $A$ and its derived set, which is defined as following.

> #### Definition: Derived Sets (Limit Points)
>
> Let $(X, \mathcal T)$ be a topological space, and let $A \subseteq X$.
>
> The **derived sets**, denoted $A'$, or $\mathrm{L}(A)$, is the set of all **limit points** of $A$. That is,
> $$
> \mathrm L(A) := \left\{ x \in X : A \cap (U \setminus \{x\}) \ne \emptyset, \; x \in U \in \mathcal T \right\}.
> $$

Any limit point $x$ of $A$ should be an element of the closure of $A$. Otherwise, $x$ is an interior point of $A^\complement$, which implies that there is an open set $U$ containing $x$ with $U \subseteq A^\complement$, i.e., $U \cap A = \emptyset$, hence $A \cap (U \setminus \{x\})$ is empty. This is a contradiction. So
$$
A \cup \mathrm L(A) \subseteq \mathrm{cl}(A).
$$
On the other hand, for any point $x \in \mathrm{cl}(A)$, $x$ should be a member of $A$ or a limit point of $A$. Assume $x$ is neither a member of $A$ nor a limit point of $A$, then $x$ is an interior point $A^\complement$. As
$$
\mathrm{int}(A^\complement) = X \setminus \mathrm{cl}(A),
$$
we have $x \notin \mathrm{cl}(A)$. This contradiction shows that $x \in A \cup \mathrm{L}(A)$.

So, we have, we have
$$
\mathrm{cl}(A) \subseteq A \cup \mathrm{L}(A).
$$
Then, we
$$
\mathrm{cl}(A) = A \cup \mathrm{L}(A)
$$
as an alternative definition of closures.

## Some Proposition on Interiors and Closures

> #### Lemma: The Union of the Interiors of Sets Is a Subset of the Interior of the Union of These Sets
>
> Let $(X, \mathcal T)$ be a topological space, let $\mathcal S \subseteq \mathcal T$. Then, we have
> $$
> \bigcup_{S \in \mathcal S} \mathrm{int}(S) \subseteq \mathrm{int} \left( \bigcup \mathcal S \right).
> $$

**Proof.**
$$
\begin{aligned}
\bigcup_{S \in \mathcal S} \mathrm{int}(S) &= \bigcup \left\{ \mathrm{int}(S) \right\}_{S \in \mathcal S}
\end{aligned}
$$
Let $\mathcal M = \mathcal P\left( \bigcup \mathcal S \right) \cap \mathcal T$, then we have
$$
\begin{aligned}
\mathrm{int}\left( \bigcup \mathcal S \right) &= \bigcup \mathcal M.
\end{aligned}
$$
As $\mathcal M$ contains all open subset of $\bigcup \mathcal S$, and as $\mathrm{int}(S)$ is open for any $S \in \mathcal S$,
$$
\left\{\mathrm{int}(S) \right\}_{S \in \mathcal S} \subseteq \mathcal M.
$$
Thus,
$$
\bigcup_{S \in \mathcal S} \mathrm{int}(S) \subseteq \mathrm{int} \left( \bigcup \mathcal S \right)
$$
$\blacksquare$

Note that, the $=$ relation does not need to hold in this proposition. For example, let $\mathcal T$ be an indiscrete topology for $\mathbb R$, then
$$
\emptyset = \bigcup_{x \in \mathbb R} \mathrm{int}(\{x\}) \subsetneq \mathrm{int} \left( \bigcup_{x \in \mathbb R} \{x\} \right) = \mathbb R.
$$

> #### Lemma: The Finite Intersection of the Interiors of Sets Equals the Interior of the Finite Intersection of These Sets
>
> Let $(X, \mathcal T)$ be a topological space, let $\mathcal F$ be a finite subset of $\mathcal T$. Then, we have
> $$
> \bigcap_{F \in \mathcal F} \mathrm{int}(F) = \mathrm{int} \left( \bigcap \mathcal F \right).
> $$

**Proof.** Let
$$
U = \bigcap_{F \in \mathcal F} \mathrm{int}(F) = \bigcap \{ \mathrm{int}(F) \}_{F \in \mathcal F}.
$$
By open axiom 3, $U$ is open. As $\mathrm{int}(F) \subseteq F$ for any $F \in \mathcal F$,
$$
U \subseteq \bigcap \mathcal F.
$$
As $U$ is an open subset of $\bigcap \mathcal F$,
$$
U \subseteq \mathrm{int} \left( \bigcap \mathcal F \right).
$$
One the other hand, let $x \in \mathrm{int} \left( \bigcap \mathcal F \right)$, we need to show that $x \in U$ also. As $\mathrm{int} \left( \bigcap \mathcal F \right)$ is open, there is an open $N \ni x$ such that $N \subseteq \mathrm{int} \left( \bigcap \mathcal F \right)$. By the definition of interiors, $N$ is an open subset of $\bigcap \mathcal F$. So, for any $F \in \mathcal F$, $N$ is an open subset of $F$, hence $N \subseteq \mathrm{int}(F)$. That is,
$$
\begin{aligned}
N \subseteq \bigcap_{F \in \mathcal F} \mathrm{int}(F).
\end{aligned}
$$
Thus,
$$
\bigcap_{F \in \mathcal F} \mathrm{int}(F) = \mathrm{int} \left( \bigcap \mathcal F \right).
$$
$\blacksquare$

## Other Set-Classes Deduced by Interiors and Closures

> #### Definition: Boundaries

> #### Definition: Exteriors
