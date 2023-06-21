# Rank and Nullity

## Rank
Let $T\in \mathbb{R}^{m\times n}$ be a matrix and denote $\mathbf{t}_i \in \mathbb{R}^m$, $1\leq i \leq n$ to be its' column:

$$
T = \left[\mathbf{t}_1 \, \mathbf{t_2} \, \cdots \, \mathbf{t_n} \right]
$$

The **rank** of $T$, denoted as $\text{rank}(T)$, is the number of linearly independent columns in $T$. It is clear from the definition above that

$$
\text{rank}(T) = \text{dim}\left(\text{img} \,T\right)
$$

where $\text{img}$ is the image of $T$ (i.e. the subspace spanned by columns of $T$).

## Computing the rank of matrix
The rank of a matrix can be computed by gaussian elimination.