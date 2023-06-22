# Integration over submanifold of $\mathbb{R}^n$

## Volume of $k$-parallelepiped in $\mathbb{R}^n$
We shall begin by defining the volume of a $k$-parallelepiped in $\mathbb{R}^n$ (Here $k\leq n$). Following {cite:t}`hubbard2015vector`, we first try to consider the case when $k=n$. Let $\mathcal{P}_n$ be the $n$-parallelepiped spanned by vectors $\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n$, a reasonable definition for volume would be:

$$
\text{Vol}\left(\mathcal{P}_n\right) = \left|\det \left[\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n\right]\right|
$$

This is a reasonable definition for volume, because:
1. When $\mathbf{v}_1, \mathbf{v}_2,\cdots, \mathbf{v}_n = \mathbf{e}_1, \mathbf{e}_2, \cdots, \mathbf{e}_n$, $\text{Vol}\left(\mathcal{P}_n\right) = 1$

2. When $\mathbf{v}_i \to \alpha_i \mathbf{v}_i$, $\text{Vol}\left(\mathcal{P}_n^{\text{(new)}}\right)=|\alpha_i|\text{Vol}\left(\mathcal{P}_n^{\text{(old)}}\right)$

3. If $\mathbf{v}_i = \mathbf{v}_j$ for some $i\neq j$, $\text{Vol}\left(\mathcal{P}_n\right) = 0$

4. The volume is invariant under unitary transformation, because $|\det \left(UT\right)|= \sqrt{\det\left[\left(UT\right)^\dagger \left(UT\right)\right]} = \sqrt{\det\left[T^\dagger U^\dagger UT\right]} = \sqrt{\det\left[T^\dagger T\right]}=|\det\left(T\right)|$

5. The volume is unchanged when the spanning vectors are exchanged

Furthermore, this definition also agree with our usual notion of volume in dimension 2 and 3. For example, when $n=2$, 

````{admonition} **Example: Volume of 4-sphere** 
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
````



## References
```{bibliography}
:filter: docname in docnames
```