# Topological Spaces

### Definition: Topological spaces

Let $X$ be any set. A family $\mathcal T \subseteq \mathcal P(X)$ is a **topology** on $X$ iff it satisfies the **Open Set Axioms** as following.

1. $X \in \mathcal T$.

2. $\mathcal T$ is closed under arbitrary union; i.e.,
$$
\forall \mathcal U \subseteq \mathcal T : \; \bigcup \mathcal U \in \mathcal T.
$$

1. $\mathcal T$ is closed under finite intersection; i.e.,
$$
\forall \mathcal U \subseteq \mathcal T: |\mathcal U| \in \mathbb N : \bigcap \mathcal U \in \mathcal T.
$$

The ordered pair $(X, \mathcal T)$ is a **topological space** iff $\mathcal T$ is a topology on $X$.

A subset $U \subseteq X$ is an **open set** of $(X, \mathcal T)$, or **open subset** of $X$ (with the topology $\mathcal T$), iff $U \in \mathcal T$.

---

Some authors also consider $\emptyset \in \mathcal T$ as a part of the Open Set Axiom, but, rigorously, that is not necessary, because it can be proved by no matter the Axiom 2 or 3. Note, that $\emptyset$ is a subset of any sets, so $\emptyset \subseteq \mathcal T$. By using Axiom 2, we have
$$
\emptyset = \bigcup \emptyset \in \mathcal T.
$$
Or, by using Axiom 3, we have
$$
\emptyset = \bigcap \emptyset \in \mathcal T,
$$
as $\emptyset$ is also a finite set with $|\emptyset| = 0$.

---

By Axiom 3, even if the family $\mathcal T$ is an infinite topology on an infinite set $X$, it does not implies that $\mathcal T$ is closed under infinite intersection. For example, if $X = \mathbb R$, and $\mathcal T$ is the set of all open intervals in $\mathbb R$, then
$$
\left( -\frac{1}{i}, \frac{1}{i} \right)_{i \in \mathbb Z_{> 0}} \subseteq \mathcal T.
$$
But,
$$
\bigcap_{i \in \mathbb Z_{> 0}} \left( -\frac{1}{i}, \frac{1}{i} \right) = [0],
$$
which is not an open interval.

Being unnecessary to be closed under infinite intersection does not means that the topology can not be closed under infinite intersection. For example, let $\mathcal T$ be the **discrete topology** on an infinite set $X$. That is, $\mathcal T = \mathcal P(X)$. In this case, $\mathcal T$ is closed under arbitrary intersection.

