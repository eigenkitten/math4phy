# Differentiation

````{admonition} **Definition (Differentiability)** 
:class: tip
Loosly speaking, a function is **differentiable** at a point if it is well approximated by a linear function around the point. More precisely, let $f:U\subset\mathbb{R}^{m} \to \mathbb{R}^n$ and $\mathbf{a} \in U$. The function $f$ is differentiable at $\mathbf{a}$ if there exist a linear map $L\in \mathbb{R}^{m\times n}$ so that the following limit exist:

```{math} \lim_{\mathbf{h} \to \mathbf{0}} \frac{f(\mathbf{a}+\mathbf{h}) - f(\mathbf{a}) - L \mathbf{h}}{|\mathbf{h}|} = \mathbf{0}
    :label: def_differentiability
```
where $\mathbf{h} \in \mathbb{R}^{n}$
````

We can also define the **directional derivative**, which is the derivative along a particular direction. 

````{admonition} **Definition (Directional Derivative)** 
:class: tip
Directional derivative is the derivative of a multivariable function along a given direction $\mathbf{h} \in \mathbb{R}^{n}$, which can be formalized as 

```{math} D_\mathbf{h}f(\mathbf{a}) = \lim_{t \to \mathbf{0}} \frac{f(\mathbf{a}+t\mathbf{h}) - f(\mathbf{a})}{t|\mathbf{h}|} 
    :label: def_directional_derivative
```
where $t\in \mathbb{R}$
````

We shall also introduce the notion of $C^{n}$ functions. A function $f$ is said to be in class $C^{n}$ if all $k\leq n$ partial of the function exist and are continuous.