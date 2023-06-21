# Cauchy-Schwarz Inequality 
````{admonition} **Theorem (Cauchy-Schwarz)** 
:class: tip
Let $\langle\cdot,\cdot\rangle$ be an inner product defined in $\mathbb{C}^n$, then for any $\vec{v},\vec{w} \in \mathbb{C}^n$, we have:

```{math} |\langle \vec{v},\vec{w}\rangle|^2 \leq \langle \vec{v},\vec{v}\rangle \langle \vec{w},\vec{w}\rangle
    :label: thm_cauchy_schwarz
```
Furthermore, the equality is obtained if and only if $\vec{v}=\lambda \vec{w}$ for some complex number $\lambda$.
````

To prove the Cauchy-Schwarz theorem, we shall first introduce the pythagorean theorem:

`````{admonition} **Theorem (Pythagorean)**
:class: tip
Let $\vec{v},\vec{w} \in \mathbb{C}^n$ satisfy $\langle\vec{v},\vec{w}\rangle = 0$, then:

````{math} \langle\vec{v},\vec{v}\rangle + \langle \vec{w},\vec{w}\rangle = \langle \vec{v}\pm\vec{w},\vec{v}\pm\vec{w}\rangle
    :label: thm_pythagorean
````
`````
```{admonition} **Proof (Pythagorean)**
:class: dropdown, seealso

$$
&\langle \vec{v}\pm\vec{w},\vec{v}\pm\vec{w}\rangle\\
=&\langle \vec{v},\vec{v}\rangle \pm \langle \vec{v},\vec{w}\rangle \pm \langle \vec{w},\vec{v}\rangle + \langle \vec{w},\vec{w}\rangle\\
=&\langle\vec{v},\vec{v}\rangle + \langle \vec{w},\vec{w}\rangle
$$
```

Using the Pythegorean theorem, we can proof the Cauchy-Schwarz theorem by using the idea of projection.

```{admonition} **Proof (Cauchy-Schwarz)**
:class: dropdown, seealso

Let $\vec{x} = \vec{v} - \frac{\langle\vec{v},\vec{w}\rangle}{\langle \vec{w},\vec{w}\rangle}\vec{w}$, and $\vec{y}=\frac{\langle\vec{v},\vec{w}\rangle}{\langle \vec{w},\vec{w}\rangle}\vec{w}$. By construction $\langle \vec{x},\vec{y}\rangle = 0$. Apply Pythagorean theorem:

$$
\langle\vec{x},\vec{x}\rangle + \langle \vec{y},\vec{y}\rangle &=  \langle \vec{x}+\vec{y},\vec{x}+\vec{y}\rangle\\
 \langle \vec{y},\vec{y}\rangle &\leq \langle \vec{x}+\vec{y},\vec{x}+\vec{y}\rangle
$$
The last line translates to:

$$
\frac{|\langle \vec{v},\vec{w}\rangle|^2}{\langle\vec{w},\vec{w}\rangle} \leq \langle \vec{v},\vec{v}\rangle
$$

which we can rearrange to obtain: 

$$|\langle \vec{v},\vec{w}\rangle|^2 \leq \langle\vec{w},\vec{w}\rangle \langle \vec{v},\vec{v}\rangle$$

In particular, the equality holds only when $\vec{x}=0$, which immediately implies $\vec{v}=\lambda \vec{w}$
```

## Application of Cauchy-Schwarz inequality
The cauchy-schwarz inequality is one of the most useful inequalities in maths. For example, in statistics 
