# Boundaries

## Basic Definition

Boundaries is a class of sets deduced by the definitions of closures and interiors.

> #### Definition: Boundaries
>
> Let $(X, \mathcal T)$ be a topological space, and let $A \subseteq X$.
>
> The **boundary** of $A$, denoted $\partial A$ is defined as the set
> $$
> \partial A := \mathrm{cl}(A) \setminus \mathrm{int}(A).
> $$

There is a common misunderstanding that, in Euclidean metric space $(\mathbb R^n, \rho)$, the boundary of any set has no volume. This is not true. Take Euclidean metric space $(\mathbb R, \rho)$ for example. Let $C$ be the set of all rational numbers in $[0 \ldots 1]$. Then, by the definition,
$$
\partial C = \mathrm{cl}(C) \setminus \mathrm{int}(C) = [0 \ldots 1] \setminus \emptyset = [0 \ldots 1].
$$
Clearly, in this case, the volume of $\partial C$ is 1, even if the volume of $C$ is $0$.

## Boundaries of Boundaries

> #### Lemma: The Boundary of the Boundary of a Set Is A Subset of the Boundary of the Set
>
> Let $(X, \mathcal T)$ be a topological space, and let $A \subseteq X$. Then, we have
> $$
> \partial( \partial A) \subseteq \partial A.
> $$

**Proof.** As $\partial A$ is closed in $(X, \mathcal T)$, $\mathrm{cl}(\partial A) = \partial A$. Then, we have
$$
\partial (\partial A) = \mathrm{cl}(\partial A) \setminus \mathrm{int}(\partial A) = \partial A \setminus \mathrm{int}(\partial A) \subseteq \partial A.
$$
$\blacksquare$

Note that, the $=$ in the assertion needs not holds, no matther the topological space is a metric space or not. For example, let $\rho$ be the Euclidean metric on $\mathbb R$, and let $A$ be all irrational numbers in the interval $[0\ldots 1]$. The closure of $A$ is $[0\ldots 1]$, and the interior of $A$ is empty. So,
$$
\partial A = [0 \ldots 1] \setminus \emptyset = [0 \ldots 1].
$$
Now, we have
$$
\partial (\partial A) = [0\ldots 1] \setminus (0 \ldots 1) = \{0,1\}.
$$
There is another extreme example. Let $(X, \mathcal T)$ be a indiscrete topological space, and let $A$ be a non-empty proper subset of $X$. (in which case, $X$ has at least two elements.) The closure of $A$ is $X$, and the interior of $A$ is empty. So $\partial A = X$. As $X$ is clopen, the interior of $X$ is $X$ itself, we have
$$
\partial (\partial A) = X \setminus X = \emptyset.
$$

## The Relation Between Boundaries and Open/Closed Sets

By the definition of boundaries, it is easy to find that, in a topological space $(X, \mathcal T)$, a subset $A$ is closed if and only if $\partial A \subseteq A$, as $\mathrm{cl}(A) = A$ is closed, and $\partial A$ is a subset of $\mathrm{cl}(A)$; and $A$ is open if and only if $A \cap \partial A$ is empty, as $\mathrm{int}(A) = A$ is open, and and $\partial A$ does not contains $\mathrm{int}(A)$.

Also, there is another interesting proposition about the relation between boundaries and open/closed sets.

> #### Lemma: A Set Is Clopen if and Only if Its Boundary Is Empty
>
> Let $(X, \mathcal T)$ be a topological space, and let $A \subseteq X$.
>
> $A$ is clopen if and only if $\partial A$ is empty.

**Proof.** This proposition can be prove from the both sides.

$\partial A$ is empty if and only if
$$
\mathrm{cl}(A) \subseteq \mathrm{int}(A).
$$
Note that $\mathrm{int}(A) \subseteq A$, and $A \subseteq \mathrm{cl}(A)$, so
$$
\mathrm{int}(A) \subseteq \mathrm{cl}(A).
$$
So, $\mathrm{cl}(A) \subseteq \mathrm{int}(A)$ if and only if $\mathrm{cl}(A) = \mathrm{int}(A)$, which holds if and only if
$$
\mathrm{cl}(A) = A = \mathrm{int}(A).
$$
Note that $\mathrm{cl}(A) = A$ if and only if $A$ is closed, and $\mathrm{int}(A) = A$ if and only if $A$ is open. Thus, $A$ is clopen.

$\blacksquare$

For example, in a discrete topological space, all sets are clopen, so the boundary of any set is empty.