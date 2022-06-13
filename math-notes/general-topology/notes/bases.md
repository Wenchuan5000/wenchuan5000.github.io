# Bases for Topologies

Let $\mathcal I$ be a set of all open intervals in $\mathbb R$. Let $\mathcal T \subseteq \mathcal P(\mathbb R)$ with $\mathcal I \subseteq \mathcal T$, and for any $U \in \mathcal T$, $U$ can be considered as the union of a certain $\mathcal U \subseteq \mathcal I$, such that $U = \bigcup \mathcal U$.

As $\mathbb R = \bigcup \mathcal I$, and $\mathcal I \subseteq \mathcal I$, $\mathbb R \in \mathcal T$.

Let $\mathcal A \subseteq \mathcal T$. By the condition, for any $A \in \mathcal A$, there exists a $\mathcal U_A \subseteq \mathcal I$, such that $A = \bigcup \mathcal U_A$. Thus,
$$
\bigcup \mathcal A = \bigcup_{A \in \mathcal A}\left(\bigcup \mathcal U_A \right) = \bigcup \left( \bigcup_{A \in \mathcal A} \mathcal U_A \right) = \bigcup \mathcal U,
$$
where $\mathcal U = \bigcup_{A \in \mathcal A} \mathcal U_A$. As $\mathcal U \subseteq \mathcal I$, thus $\mathcal T$ is closed under arbitrary union.

Let $S_1, S_2 \in \mathcal T$. Similarly, $S_1 = \bigcup \mathcal X$ and $S_2 = \bigcup \mathcal Y$ for some $\mathcal X, \mathcal Y \in \mathcal I$. Thus, we have
$$
\begin{aligned}
S_1 \cap S_2 &= \bigcup_{X \in \mathcal X} X \cap \bigcup_{Y \in \mathcal Y} Y \\
&= \bigcup_{X \in \mathcal X} \left( X \cap \bigcup_{Y \in \mathcal Y} \mathcal Y \right) \\
&= \bigcup_{X \in \mathcal X} \left( \bigcup_{Y \in \mathcal Y} (X \cap Y) \right) \\
\end{aligned}
$$
Every $X \cap Y$ is also an open interval, so $X \cap Y \in \mathcal I$. Thus, their union is also an element of $\mathcal T$, as $\mathcal T$ is closed under arbitrary union. By induction, for any $S_1, \ldots, S_n \in \mathcal T$, their union is also an element of $\mathcal T$; i.e., $\mathcal T$ is closed under finite intersection.

Thus, $\mathcal T$ is a topology for $\mathbb R$.

Now, let $U$ be any element in $\mathcal T$, then there exists a $\mathcal U \subseteq \mathcal I$, such that $U = \bigcup \mathcal U$. With this property, we call $\mathcal I$ a basis, or, in this notes and somewhere else, analytic basis for $\mathcal T$.

---

### Definition: Analytic bases

Let $(X, \mathcal T)$ be a topological space, and let $\mathcal B \subseteq \mathcal T$.

$\mathcal B$ is an **analytic basis** for $\mathcal T$, iff for any $U \in \mathcal T$, there is a $\mathcal B' \subseteq \mathcal B$, such that
$$
U = \bigcup \mathcal B'.
$$

---

Following the example above, for any $U \in \mathcal T$, $U$ can be considered as the union of a collection $\mathcal I'$ of open intervals. So, for any $x \in U$, there must be an open interval $I_x$ containing $x$. As $I_x$ is a proper interval (as it containing $x$ at least), there is another interval $I_x' \subseteq I_x$ containing $x$.

Conversely, as for any $U \in \mathcal T$ and for any $x \in U$, there exists an $I_x \in \mathcal I$, such that $x \in I_x \subseteq U$, $U$ itself can be considered as this:
$$
U = \bigcup_{x \in U} I_x.
$$
The two directions are equivalent.

---

### Lemma: An alternative definition of bases

Let $(X, \mathcal T)$ be a topological space, and let $\mathcal B \subseteq \mathcal T$.

$\mathcal B$ is an analytic basis for $\mathcal T$, iff for any $U \in \mathcal T$ and for any $x \in U$, there is a $B \in \mathcal B$, such that
$$
x \in B \subseteq U.
$$

---

**Proof.** First, prove $\Rightarrow$.

Let $\mathcal B$ be an analytic basis for $\mathcal T$.

Note that $X \in \mathcal T$, so, there exists a $\mathcal B' \subseteq B$, such that $X = \bigcup \mathcal B'$, which implies that for any $x \in X$, there exists a $B \in \mathcal B$ containing $x$.

As $\mathcal B$ is a basis for $\mathcal T$, for any $U \in \mathcal T$, there exists a $B' \subseteq \mathcal B$ such that $U = \bigcup \mathcal B'$, which implies that for any $B' \in \mathcal B$, $B' \subseteq U$.

$\Box$

Now, prove $\Leftarrow$.

Let $U \in \mathcal T$. For any $x \in U$, let $B_x \in \mathcal B$ with $x \in B_x \subseteq U$.

As
$$
\bigcup_{x \in U} \{x\} = U,
$$
and $\{x\} \subseteq B_x$, we have

$$
U \subseteq \bigcup_{x \in U} B_x.
$$

As every $B_x \subseteq U$, we have
$$
\bigcup_{x \in U} B_x \subseteq U.
$$
Thus,
$$
U = \bigcup_{x \in U} B_x.
$$
$\blacksquare$

---

“Analytic bases” is not a popular name for the class of $\mathcal B$. Usually, we just call them **basis**. But, in this note, I’d rather use the name “analytic”, such that we can distinguish them from synthetic bases which is a concept might be confused with analytic bases (see the definition below).

The concept of synthetic bases is also important, as analytic bases are required to be subsets of the topologies of their spaces, but synthetic bases are not. With this concept, as we will see, we can generate a topology for a set by a cover (synthetic basis) of the set – before the topology is generated, it is meaningless to considered if this cover is a subset of any topology for the set.

---

### Definition: Synthetic bases

Let $(X, \mathcal T)$ be a topological space.

A subset $\mathcal B \subseteq \mathcal P(X)$ is a **synthetic basis** of $X$ iff

1. $\mathcal B$ is a cover of $X$, i.e., $\bigcup \mathcal B \supseteq X$.

2. For any $B_1, B_2 \in \mathcal B$, there exists $\mathcal A \subseteq \mathcal B$, such that

$$
B_1 \cap B_2 = \bigcup \mathcal A.
$$

---

Let $\mathcal I$ be the set of all open intervals in $\mathbb R$. Then, a collection
$$
\mathcal T = \left\{ \bigcup \mathcal A : \mathcal A \subseteq \mathcal I \right\}
$$
is an topology for $\mathbb R$. Here $\mathcal I$ is an analytic basis for $\mathcal T$. Also, for any $I_1, I_2 \in \mathcal I$,
$$
I_1 \cap I_2 = (\min(I_1 \cap I_2), \max(I_1 \cap I_2)).
$$
Thus, $\mathcal I$ is also a synthetic basis for $\mathcal T$.

---

### Lemma: Bases are synthetic

Let $(X, \mathcal T)$ be a topological space, and let $\mathcal B \subseteq \mathcal P(X)$.

If $\mathcal B$ is a basis for $\mathcal T$, then $\mathcal B$ is a synthetic basis of $X$.

---

**Proof.** As $\mathcal B$ is a basis for $\mathcal T$,

1. $\mathcal B$ is a cover of $X$, i.e., $\bigcup \mathcal B \supseteq X$.

2. For any $B_1, B_2 \in \mathcal B$, there exists $\mathcal B' \subseteq \mathcal B$, such that

$$
B_1 \cap B_2 = \bigcup \mathcal B'.
$$

$X \in \mathcal T$, thus, there exists a $\mathcal B' \subseteq \mathcal B$ such that $X = \bigcup \mathcal B'$. Thus, $\mathcal B$ is a cover of $X$.

Let $B_1, B_2 \in \mathcal B$. As $\mathcal B \subseteq \mathcal T$, $B_1, B_2 \in \mathcal T$, so $B_1 \cap B_2 \in \mathcal T$. Thus, there exists $\mathcal B' \subseteq \mathcal B$, such that
$$
B_1 \cap B_2 = \bigcup \mathcal B'.
$$
$\blacksquare$

---

How does a synthetic basis generate a topology?

First, note that, for a given set $X$, we can construct a specific topology for $X$ from any cover of $X$ as a start. For example, let $\mathcal C$ be a cover of $X$. Then, we can find a synthetic basis:
$$
\mathcal B = \left\{ \bigcap \mathcal A: \mathcal A \subseteq \mathcal C \land |\mathcal A| \in \mathbb N \right\}.
$$
Generating a topology by $\mathcal B$ means that we need to find the smallest topology containing $\mathcal B$.

By the condition, the synthetic basis $\mathcal B$ is closed under finite intersection. So, now, we need to find the smallest superset of $\mathcal B$ preserving this property and safisfying the rest of the open set axioms.

Let
$$
\mathcal T = \left\{ \bigcup \mathcal A: \mathcal A \subseteq \mathcal B \right\}.
$$
By $\mathcal T$ is defined, $\mathcal T$ is a superset of $\mathcal B$ and is closed under arbitrary union. Also, As $\mathcal B$ is a cover of $X$, and $\mathcal B \subseteq \mathcal B$, we have $X = \bigcup \mathcal B \in \mathcal T$.

Thus, $\mathcal T$ is a topology for $X$, and it is generated from the synthetic basis $\mathcal B$.

Note that, in this case, $\mathcal B$ is not needed to be an analytic basis for $\mathcal T$. For example, let
$$
\mathcal B = \{ [n, n + 1) \subseteq \mathbb R: n \in \mathbb Z \}.
$$
$\mathcal B$ is a synthetic basis of $\mathbb R$ (for any $B_1, B_2 \in \mathcal B$, $B_1 \cap B_2 = \bigcup \emptyset$). Let $\mathcal T$ be the topology generated by $\mathcal B$.

Take $[0, 2)$ for example, it is the union of $[0,1)$ and $[1,2)$, thus it is an element of $\mathcal T$. But, it is not an element of $\mathcal B$.

---

### Definition: Generated Topology

Let $(X, \mathcal T)$ be a topological space, and let $\mathcal B$ be a synthetic basis of $X$.

$\mathcal T$ is **generated** by $\mathcal B$, iff
$$
\mathcal T = \left\{ \bigcup \mathcal A: \mathcal A \subseteq \mathcal B \right\}.
$$















