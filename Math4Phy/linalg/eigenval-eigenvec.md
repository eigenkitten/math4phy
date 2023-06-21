# Eigenvalues and Eigenvectors
The idea of eigenvalues and eigenvectors are arguably the most important concept in linear algebra. 

## Existence of eigenvalue
We shall first show that eigenvalues exist. Note that this is a non-trivial fact because it depends on the vector space we are living in and the fields we used to define our the vector space. For example, the rotation matrix

$$
\begin{pmatrix}
\cos \theta & -\sin \theta \\
\sin \theta &  \cos \theta
\end{pmatrix}
$$

Do not have any eigenvalues in $\mathbb{R}$. 

We now state the conditions:
````{admonition} **Theorem** 
:class: tip
Let $V\neq\{\mathbf{0}\}$ be a finite dimensional vector space over $\mathbb{C}$ and $T: V \to V$ be a linear map, then $V$ admits at least one eigenvalue. 
````
```{admonition} **Proof**
:class: dropdown, seealso
This is a standard proof presented in many linear algebra text (e.g. {cite:t}`axler1997linear,beezer2012first`). Let $n < \infty$ be the dimension of the vector space. To simplify our discussion, we note that our vector space is isomorphic to $\mathbb{C}^n$. Furthermore, a basis exist. Hence, we can represent $T$ as a $n\times n$ complex matrix over certain basis. 

Now, because $V$ is non-empty, there exist some non-zero vector $\mathbf{v} \in V$. we construct the following list of $n+1$ vectors:

$$
\left(\mathbf{v},T\mathbf{v},T^2 \mathbf{v},\cdots, T^n \mathbf{v}\right)
$$

Since the vector space is of dimension $n$, these vectors must be linearly dependent:

$$
a_0 \mathbf{v} + a_1 T \mathbf{v} + a_2 T^2 \mathbf{v} + \cdots + a_n T^n \mathbf{v} = \mathbf{0}
$$

where $a_0,a_1,\cdots,a_n$ not all zero. Furthemore, we know that $a_1,\cdots,a_n$ not all zero otherwise $\mathbf{v}=0$ or $a_0=a_1=\cdots=a_n=0$. Let $a_m$ ($m>0$) be the first non-zero coefficient and consider the following polynomial over $\mathbb{C}$:

$$
p(z) = a_0 + a_1 z + \cdots + a_m z^m
$$
where $z\in \mathbb{C}$. By the fundamental theorem of algebra, we know the polynomial above is factorizable over $\mathbb{C}$:

$$
p(z) = c(z-\lambda_1)(z-\lambda_2)\cdots (z-\lambda_m)
$$

This allow us to factorize the matrix polynomial above:

$$
p(T) &= a_0 \mathbf{v} + a_1 T \mathbf{v} + a_2 T^2 \mathbf{v} + \cdots + a_n T^n \mathbf{v} \\
&= (T-\lambda_1 I )(T-\lambda_2 I )\cdots (T-\lambda_m I)
$$

Therefore:
$
(T-\lambda_1 I )(T-\lambda_2 I )\cdots (T-\lambda_m I) \mathbf{v}=0
$

Hence, there is at least one value of $\lambda_j$ in which $(T-\lambda_j I)$ is non-injective and thus the eigenvalue exist.
```
In fact, the proof is also a way to constructively find the eigenvalue and eigenvector of a matrix $T$, provided that we can find all the roots of the characteristic polynomial.


Let $T\in \mathbb{C}^{n\times n}$


## References
```{bibliography}
:filter: docname in docnames
```