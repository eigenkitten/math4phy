# Integration over submanifold of $\mathbb{R}^n$

## Volume of $k$-parallelepiped in $\mathbb{R}^n$
We shall begin by defining the volume of a $k$-parallelepiped in $\mathbb{R}^n$ (Here $k\leq n$). Following {cite:t}`hubbard2015vector`, we first try to consider the case when $k=n$. Let $\mathcal{P}_n$ be the $n$-parallelepiped spanned by vectors $\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n$, a reasonable definition for volume would be:

$$
\text{Vol}\left(\mathcal{P}_n\right) = \left|\det \left[\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n\right]\right| = \sqrt{\det\left(T^\dagger T\right)}
$$ (parallelepiped_volume_n)

where $T=\left[\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n\right]$

This is a reasonable definition for volume, because:
1. When $\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n = \mathbf{e}_1, \mathbf{e}_2, \cdots, \mathbf{e}_n$, $\text{Vol}\left(\mathcal{P}_n\right) = 1$

2. When $\mathbf{v}_i \to \alpha_i \mathbf{v}_i$, $\text{Vol}\left(\mathcal{P}_n^{\text{(new)}}\right)=|\alpha_i|\text{Vol}\left(\mathcal{P}_n^{\text{(old)}}\right)$

3. If the columns of $T$ are linearly dependent, the $\text{Vol}\left(\mathcal{P}_n\right) = 0$

4. The volume is invariant under unitary transformation, because $|\det \left(UT\right)|= \sqrt{\det\left[\left(UT\right)^\dagger \left(UT\right)\right]} = \sqrt{\det\left[T^\dagger U^\dagger UT\right]} = \sqrt{\det\left[T^\dagger T\right]}=|\det\left(T\right)|$

5. The volume is unchanged when the spanning vectors are exchanged

To generalize the definition in {eq}`parallelepiped_volume_n`, we note that the second form of the definition $\text{Vol}\left(\mathcal{P}_n\right)=\sqrt{\det\left(T^\dagger T\right)}$ works even when $k\leq n$. This is because if $T\in \mathbb{R}^{n\times k}$, then $T^\dagger T \in \mathbb{R}^{k\times k}$, which is not only a square matrix, but also one with dimension $k$. Therefore, we propose the following definition for the volume of $k$-parallelepiped in $\mathbb{R}^n$:

$$
\text{Vol}\left(\mathcal{P}_k\right) =\sqrt{\det\left(T^\dagger T\right)}
$$ (parallelepiped_volume_k)

where $T=\left[\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_k\right]$ and $k$ is allowed to be smaller than $n$.

Furthermore, this definition also satisfy properties 1-5 listed above, agreeing with our usual intuition for volume. Most of the properties listed above follows directly from the definition, with an exception for (3). Hence, we will only prove (3) here:

````{admonition} **Proposition** 
:class: tip
The volume element defined in {eq}`parallelepiped_volume_k` satisfy property (3).
````

```{admonition} **Proof**
:class: dropdown, seealso
We shall prove the proposition by showing that $T^{\dagger}T$ is singular. By hypothesis, the columns of $T$ are linearly dependent, therefore there exist some $\mathbf{v} \in \mathbb{R}^{k}$, $\mathbf{v}\neq \mathbf{0}$ such that $T\mathbf{v} = \mathbf{0}$. Immediately, we see that $\left(T^{\dagger}T\right)\mathbf{v} =T^{\dagger}\left(T\mathbf{v}\right) = \mathbf{0}$. Therefore, $T^{\dagger}T$ is singular and the determinant is zero.
```


Moreover, the definition agree with our usual definition of volume in $\mathbb{R}^3$. 

````{admonition} **Example: Area of a parallelogram in $\mathbb{R}^3$** 
:class: tip
Consider a parallelogram in $\mathbb{R}^3$ spanned by two vectors $\mathbf{v}_1, \mathbf{v}_2$. According to the definition:


$$
\text{Vol}\left(\mathcal{P}_2\right) = \sqrt{
    \det\begin{bmatrix}
    \mathbf{v}_1 \cdot \mathbf{v}_1 & \mathbf{v}_1 \cdot \mathbf{v}_2\\
    \mathbf{v}_2 \cdot \mathbf{v}_1 & \mathbf{v}_2 \cdot \mathbf{v}_2
    \end{bmatrix}} = \sqrt{|\mathbf{v}_1|^2 |\mathbf{v}_2|^2(1-\cos^2 \theta)} = |\mathbf{v}_1| |\mathbf{v}_2| |\sin \theta|
$$
where $\theta$ is the angle between the two vectors. This is precisely the norm of the cross product $|\mathbf{v}_1 \times \mathbf{v}_2|$.
````

## Differential volume element
Consider a $k$-dimensional surface in $\mathbb{R}^n$ parameterized by a function $X:U\subset \mathbb{R}^{k} \to \mathbb{R}^n$:

$$
X\left(\theta_1, \theta_2, \cdots, \theta_k \right)
$$

Clearly, the coordinate basis for the tangent space are:

$$
\frac{\partial X}{\partial \theta_1}, \frac{\partial X}{\partial \theta_2}, \cdots, \frac{\partial X}{\partial \theta_k}
$$

Therefore, the differential volume element is the volume spanned by these coordinate basis:

$$
d^k\mathbf{X} = \sqrt{\det \left[T^\dagger T\right]} \,d^k \boldsymbol{\theta}
$$

where $d^k \mathbf{\theta} = d\theta_1 d\theta_2 \cdots d\theta_k$ and 

$$
T = \left[\frac{\partial X}{\partial \theta_1}, \frac{\partial X}{\partial \theta_2}, \cdots, \frac{\partial X}{\partial \theta_k}\right]
$$

```{note}
In fact in $\mathbb{R}^2$, $T^\dagger T$ is also called the **first fundamental form** of the surface.
```

With the differential volume element, we can perform integration on submanifolds of $\mathbb{R}^n$. Here are some examples



````{admonition} **Example: Surface area of 4-sphere** 
:class: tip
The 4-sphere is defined by the following implicit equation:

$$
x^2 + y^2 + z^2 + w^2 = R^2 
$$

This can also be parameterized using the spherical coordinates:

$$
x &= R\sin \alpha \sin \theta \cos \phi\\
y &= R\sin \alpha \sin \theta \sin \phi\\
z &= R\sin \alpha \cos \theta\\
w &= R\cos \alpha
$$

where $\alpha, \theta \in [0,\pi]$ and $\phi \in [0,\pi]$


Hence, the differential volume element is given as:

$$
dS = R^3 \sin^2 \alpha \sin \theta d\alpha d\theta d\psi
$$

and the surface area:

$$
S = \int_0^{\pi} d\alpha \int_{0}^{\pi} d\theta \int_0^{2\pi} d\phi \,\,R^3 \sin^2 \alpha \sin \theta = 2 \pi^2 R^3
$$



````




## References
```{bibliography}
:filter: docname in docnames
```