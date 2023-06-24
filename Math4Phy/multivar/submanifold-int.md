---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

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


````{admonition} **Example: Surface area of a n-sphere** 
:class: tip
A n-sphere is a surface defined by the following implicit equation:

$$
x_1^2 + x_2^2 + \cdots + x_n^2 = R^2
$$

To simply the notation, we first rescale all variables by $R$ (i.e. Let $x_i = R u_i$). This cast our defining equation into the following form:
$$
u_1^2 + u_2^2 + \cdots + u_n^2 = 1
$$

We want to proceed by mathematical induction. To do that, we observe that for any fixed $u_n$, the equation above defines a $n-1$ dimensional sphere of radius $1 - u_n^2$, Hence, the spherical coordinates in $n-1$ dimension can be used. Therefore, we can recursively define a parameterization for a $n$-sphere:

$$
u_1 & = \sin \alpha_{n-1} S^{n-1}_1\left(\alpha_{1}, \alpha_2, \cdots, \alpha_{n-2}\right)\\
&\cdots\\
u_{n-1} & = \sin \alpha_{n-1} S^{n-1}_{n-1}\left(\alpha_{1}, \alpha_2, \cdots, \alpha_{n-2}\right)\\
u_n &= \cos \alpha_{n-1}
$$

where $S^{n}_{i}$ is the spherical coordinate element for an unit $n$-sphere. We will also introduce the notation $\mathbf{S}_n$, which is defined to be:

$$\mathbf{S}_{n} = \left(S^{n}_1, S^{n}_2, \cdots, S^{n-1}_{n}\right)$$

Because $\mathbf{S}_n$ is a vector on the unit $n$-sphere, $\mathbf{S}_n^\dagger \mathbf{S}_n = 1$.

Now, $T_n$ be the jacobian for an unit $n$-sphere under the spherical coordinates, by definition:

$$
T_n &= \begin{bmatrix}
\frac{\partial u_1}{\partial{\alpha_{n-1}}} & \frac{\partial u_1}{\partial{\alpha_{n-2}}} & \cdots & \frac{\partial u_1}{\partial{\alpha_{1}}}\\
\frac{\partial u_2}{\partial{\alpha_{n-1}}} & \frac{\partial u_2}{\partial{\alpha_{n-2}}} & \cdots & \frac{\partial u_2}{\partial{\alpha_{1}}}\\
\cdots & \cdots & \cdots & \cdots\\
\frac{\partial u_n}{\partial{\alpha_{n-1}}} & \frac{\partial u_n}{\partial{\alpha_{n-2}}} & \cdots & \frac{\partial u_n}{\partial{\alpha_{1}}}\\
\end{bmatrix}\\
&= \begin{bmatrix}
\frac{\partial u_1}{\partial{\alpha_{n-1}}} & \frac{\partial u_1}{\partial{\alpha_{n-2}}} & \cdots & \frac{\partial u_1}{\partial{\alpha_{1}}}\\
\frac{\partial u_2}{\partial{\alpha_{n-1}}} & \frac{\partial u_2}{\partial{\alpha_{n-2}}} & \cdots & \frac{\partial u_2}{\partial{\alpha_{1}}}\\
\cdots & \cdots & \cdots & \cdots\\
\frac{\partial u_n}{\partial{\alpha_{n-1}}} & 0 & \cdots & 0 \\
\end{bmatrix}\\
&= \begin{bmatrix}
\cos \alpha_{n-1} \mathbf{S}_{n-1} & \sin \alpha_{n-1} T_{n-1} \\
-\sin \alpha_{n-1} & \mathbf{0}
\end{bmatrix}
$$

By direct computation, the product $T_n^\dagger T_n$ is:


$$
T_n^\dagger T_n = \begin{bmatrix}
1 & \cos\alpha_{n-1} \sin \alpha_{n-1} \mathbf{S}_{n-1}^\dagger T_{n-1}\\
\cos\alpha_{n-1} \sin \alpha_{n-1} T_{n-1}^\dagger \mathbf{S}_{n-1} & \sin^2 \alpha_{n-1} T_{n-1}^\dagger T_{n-1}
\end{bmatrix}
$$

Using the formula for the determinant of block matricies:

$$
\det \begin{bmatrix}
A & B \\
C & D
\end{bmatrix} = \det\left(A-BD^{-1}C\right)\det\left(D\right)
$$

we can show that

$$
\det T_n^\dagger T_n &= \det \left(\sin^2 \left(\alpha_{n-1}\right) T_{n-1}^\dagger T_{n-1}\right) \det\left(T_{n-1}^\dagger T_{n-1}\right)\\
&= \sin^{2(n-2)}\left(\alpha_{n-1}\right) \det\left(T_{n-1}^\dagger T_{n-1}\right)
$$

Therefore, 

$$
\sqrt{\det T_n^\dagger T_n} = \left|\sin^{n-2} \left(\alpha_{n-1}\right)\right| \sqrt{\det\left(T_{n-1}^\dagger T_{n-1}\right)}
$$

and we have shown that the surface area element of a unit $n$-sphere takes the form:

$$
dS_n = \sin^{n-2}\left(\alpha_{n-1}\right)\sin^{n-3}\left(\alpha_{n-2}\right) \cdots \sin\left(\alpha_{2}\right) d\alpha_1 d\alpha_2 \cdots d\alpha_{n-1}
$$

This can be directly integrated to give the following surface area for a unit $n$-sphere:

$$
S_n = \frac{2\pi^{n/2}}{\Gamma(n/2)}
$$

For a $n$-sphere with radius $R$, we simply multiply $R^{n-1}$ to $S_n$
````


````{admonition} **Example: Arc length of an ellipse** 
:class: tip
The ellipse is defined using the parametric equation $\vec \gamma: t\in [0,2\pi] \to \mathbb{R}^2$:

$$
\vec \gamma(t) = \left(a \cos t, b \sin t\right) 
$$

By {eq}`parallelepiped_volume_k`, the arc length $s$ is given by the following integral:

$$
s = \int_0^{2\pi} |\vec \gamma^{'}(t)| \,dt = \int_{0}^{2\pi} \sqrt{a^2 \sin^2 t + b^2 \cos^2 t} \,dt
$$

By restricting the domain to $[0,\pi/2]$ and applying the double angle formula, we obtain:

$$
s = 4 \sqrt{\frac{a^2+b^2}{2}} \int_{0}^{\pi/2} \sqrt{1-\kappa \cos 2t} \, dt
$$

where $\kappa=\frac{a^2-b^2}{a^2+b^2} \leq 1$. We can proceed by writing our integral in terms of special functions or make an approximation by Taylor expansion, we will choose the latter.

$$
s &= 2 \sqrt{\frac{a^2+b^2}{2}} \int_{0}^{\pi} \sqrt{1-\kappa \cos t} \, dt\\
&\approx 2\pi \sqrt{\frac{a^2+b^2}{2}} \left[1-\left(\frac{\kappa}{4}\right)^2\right]
$$


Here is a plot comparing the approximated result with the analytical calculation:

```{glue} arc_length_integral
```

````

```{code-cell} ipython3
:tags: [remove-stderr,remove-cell]
from myst_nb import glue
import numpy as np
import matplotlib.pyplot as plt

kappa = np.linspace(0,1,1000)

def integral(kappa):
    tb = np.linspace(0,np.pi,5001)
    tm = 0.5*(tb[1:]+tb[:-1])
    dt = tb[1:]-tb[:-1] 
    return np.sum(np.sqrt(1-kappa*np.cos(tm))*dt)

integral = np.vectorize(integral)

analy = integral(kappa)
appro = np.pi*(1-(kappa/4)**2)

fig, axs = plt.subplots(nrows=2,sharex=True,gridspec_kw = {'wspace':0, 'hspace':0},dpi=100)
axs[0].plot(kappa,analy,label='Analytical')
axs[0].plot(kappa,appro,label='Approximate')
axs[0].legend()
axs[0].set_ylabel(r'$I(\kappa)$')
axs[0].set_title(r'Approximating $I(\kappa) = \int_{0}^{\pi} \sqrt{1-\kappa \cos t} \, dt$')
axs[0].grid()

axs[1].plot(kappa,appro/analy)
axs[1].set_ylabel(r'Error')
axs[1].set_xlabel(r'$\kappa$')
axs[1].axhline(1,ls='--',color='grey',alpha=0.8)
axs[1].set_ylim(0.99,1.05)
axs[1].grid()

glue("arc_length_integral",fig)
```






## References
```{bibliography}
:filter: docname in docnames
```