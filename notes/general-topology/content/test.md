# Metric Spaces

## What is a Metric Space?

How do we measure the distance between two points in a space? Take $\mathbb R^n$ for example, for any points $x, y \in \mathbb R^n$, the distance between $x$ and $y$ is given by
$$
\rho(x, y) = \left( \sum_{i = 1}^n |x_i - y_i|^2 \right)^\frac{1}{2},
$$
where for any $p \in \mathbb R^n$, $p_i$ denotes the $i$-th component of $p$. Here, we consider $\rho$ as a function from $\mathbb R^n \times \mathbb R^n$ to $\mathbb R$, called **Euclidean metric function** on $\mathbb R^n$. Then, $\rho$ satisfies the following conditions: For any $x$, $y$, and $z \in \mathbb R^n$,

1. $\rho(x, y) = 0$ if and only if $x = y$;
2. $\rho(x, y) = \rho(y, x)$;
3. $\rho(x, y) + \rho(y, z) \ge \rho(x, z)$; this property is also called **triangle inequality**.

In this case, we call the ordered pair $(\mathbb R^n, \rho)$ the **$n$-dimensional Eulidean metric space**.

Just like how the first scientist defined the unite of 1 kilogram, a metric function is not entirely naturally given, but is chosen depend on what distance we need to find. In the example above, the set $\mathbb R^n$ can be replaced by any set $X$, and the metric function $\rho$ can be any operation from $X \times X \to \mathbb R$ satisfying the 4 conditions above. And this is how metric spaces are defined.


> #### Definition: Metric Spaces
>
> Let $X$ be any set. A mapping $\rho: X \times X \to \mathbb R$ is a **metric** on $X$ if and only if it satisfies the **open axioms**. That is, for any $\mathbf x, \mathbf y, \mathbf z \in X$,
>
> 1. $\rho(x, y) = 0$ if and only if $x = y$ (**identity**);
> 2. $\rho(x, y) = \rho(y, x)$ (**symmetry**);
> 3. $\rho(x, y) + \rho(y, z) \ge \rho(x, z)$ (**triangle inequality**).
>
> An ordered pair $(X, \rho)$ is a **metric space** if and only if $\rho$ is a metric on $X$.


Some author also consider $\rho(x, y) \ge 0$ as an axiom in the list above, but, rigoroursly, it is a property deduced by the 3 axioms. By triangle inequality, we have
$$
\rho(x, y) + \rho(y, x) \ge \rho (x, x).
$$
By symmetry, we have
$$
\rho(x, y) + \rho(x,y) \ge \rho(x, x).
$$
By identity, we have
$$
2\rho (x,y) \ge 0.
$$
Thus,
$$
\rho(x,y) \ge 0.
$$

So, if we are going to prove if an operation is a metric, this is an unnecessary progress.

## Balls

> #### Definition: Open Balls
>
> Let $(X, \rho)$ be a metric space, let $x \in X$, and let $\delta \in \mathbb R_{> 0}$.
>
> The **open $\delta$-ball**, or simply **$\delta$-ball**, of $x$ is defined as the set
> $$
> B(x, \delta) = \left\{ y \in X: \rho(x,y) < \delta \right\}.
> $$

The “shape” of an open ball is determined by the metric and the set. In the 3-dimentional Euclidean metric space $(\mathbb R^3, \rho)$, for example, an open $\delta$-ball of $x$ is a sphere with $x$ as its center and $\delta$ as its radius. But if $\rho$ is a **taxicap metric** on $\mathbb R^3$, i.e.,
$$
\rho(x,y) = |x_1 - y_1| + |x_2 - y_2| + |x_3 - y_3|,
$$
then, an open $\delta$-ball of $x$ is no longer a sphere, but a box with $x$ as its center and $2\delta$ as the length of it edges.

If $<$ is replaced by $\le$ in the definition, then we have the definition blew.

> #### Definition: Closed Balls
>
> Let $(X, \rho)$ be a metric space, let $x \in X$, and let $\delta \in \mathbb R_{> 0}$.
>
> The **closed $\delta$-ball** of $x$ is defined as the set
> $$
> \overline B(x, \delta) = \left\{ y \in X: \rho(x,y) \le \delta \right\}.
> $$

Note that, in the both definitions above, we have the condition $y \in X$. This means, open (closed) balls is always are always subsets of $X$. For example, let
$$
X = [0 , 1] \times [0,1],
$$
and let $\rho$ be an Euclidean metric on $X$. In this case, $B(0,1)$ is not a disk, but disk sector.

## Some Examples on Metric Spaces

### Ratio Metrics on $\mathbb R_{> 0}$

Some metrics do not care about the any geometrical length. For example, let $\rho: \mathbb R_{> 0} \times \mathbb R_{> 0} \to \mathbb R$ be defined as
$$
\rho(x,y) =
\begin{cases}
\displaystyle \frac{x}{y} - 1 &: x \ge y; \\
\displaystyle \frac{y}{x} - 1 &: x < y,
\end{cases}
$$
then $\rho$ is a metric on $\mathbb R_{> 0}$ only cares about the ratio between any two points in the space.

There is another metric on $\mathbb R_{> 0}$ which is quite similar. Let $\rho: \mathbb R_{> 0} \times \mathbb R_{> 0} \to \mathbb R_{\ge 0}$ be defined as
$$
\rho(x,y) = \left|\log \left( \frac{x}{y} \right) \right|,
$$
then $\rho$ is a metric on $\mathbb R_{> 0}$, and it can be proved by the properties of logarithm functions.

### Discrete Metric Spaces

**Discrete metric** $\rho$ on $X$ only cares about if any two points $x$ and $y$ in $X$ coincide or not. That is,
$$
\rho(x,y) =
\begin{cases}
1 &: x \ne y; \\
0 &: \text{else}.
\end{cases}
$$

### $p$-Product Metric Spaces

Euclidean metric space is one of $p$-product metric spaces. Let
$$
X = \prod_{i = 1}^n X_i.
$$
Then, for any $p \in \mathbb R_{\ge 1}$, the $p$-product metric $\rho_p: \mathbb R^n \times \mathbb R^n \to \mathbb R$ is defined as
$$
\rho_p(x, y) = \left( \sum_{i = 1}^n \rho_i^p(x_i, y_i) \right)^\frac{1}{p},
$$
where $\rho_i(x_i, y_i)$ can be the Euclidean metric on $X_i$ for any $i \in \{1, \ldots, n\}$, but it is not required. Indeed, $p$-product metric spaces are metric space. It is easy to show that $\rho_p$ satisfies the metric axiom 1 and 2. Now, we prove that the $\rho_p$ satisfies the metric axiom 3. That is to show that
$$
\left( \sum_{i = 1}^n \rho_i(x_i, z_i)^p \right)^\frac{1}{p} \le \left( \sum_{i = 1}^n \rho_i(x_i, y_i)^p \right)^\frac{1}{p} + \left( \sum_{i = 1}^n \rho_i(y_i, z_i)^p \right)^\frac{1}{p}
$$
for any $x,y,z \in X$.

**Proof.** By Minkowski's inequality,
$$
\left( \sum_{i = 1}^n (\rho_i (x_i, y_i) + \rho_i(y_i, z_i))^p \right)^\frac{1}{p} \le \left( \sum_{i = 1}^n \rho_i(x_i, y_i)^p \right)^\frac{1}{p} + \left( \sum_{i = 1}^n \rho_i(y_i, z_i)^p \right)^\frac{1}{p}.
$$
As for any $i$, $\rho_i$ is a metric on $X_i$. So $\rho_i$ satisfies the open axiom 3. Thus,
$$
\left( \sum_{i = 1}^n \rho_i(x_i, z_i)^p \right)^\frac{1}{p} \le \left( \sum_{i = 1}^n (\rho_i (x_i, y_i) + \rho_i(y_i, z_i))^p \right)^\frac{1}{p}.
$$
That is,
$$
\rho(x, z) \le \rho(x,y) + \rho(y,z),
$$
which is precisely the metric axiom 3.

$\blacksquare$

### Uniform Metrics

Let $M$ be a set of all bounded functions $S \to (T, \rho_T)$, where $\rho_T$ is a metric on $T$. Here, we treat all of these functions as points in $M$. Let $\rho: M \times M \to \mathbb R$ be defined as
$$
\rho(f,g) = \sup_{x \in S} \rho_T(f(x), g(x)),
$$
Then $\rho$ is a metric on $M$. It is actually easy to prove that $\rho$ is indeed a metric on $M$. Take the metric axiom 3 for example.

**Proof.** Let $f, g, h \in M$, then we have
$$
\begin{aligned}
\rho(f, g) + \rho(g, h) &= \sup_{x \in S} \rho_T(f(x), g(x)) + \sup_{x \in S} \rho_T (g(x), h(x)) \\
&= \sup_{x \in S} \left( \rho_T (f(x), g(x)) + \rho_T (g(x), h(x)) \right).
\end{aligned}
$$
As $\rho_T$ satisfies the metric axiom 3, we have
$$
\ldots \ge \sup_{x \in S} \rho(f(x), h(x)) = \rho(f,h).
$$
$\blacksquare$

### Hausdorff Metrics

Let $(M, \rho)$ be a metric space. Let $\rho_H: \mathcal P(M) \setminus \{\emptyset\} \to \mathbb R$ be defined as
$$
\rho_H(X, Y) = \max \left\{ \sup_{x \in X} \rho(x, Y), \sup_{y \in Y} \rho (y, X) \right\},
$$
where
$$
\rho_H(a, B) = \inf_{b \in B} \rho(a,b).
$$

$\rho_H$ is called **Hausdorff metric**. It measures how two subsets $X$ and $Y$ of $M$ are similar.

