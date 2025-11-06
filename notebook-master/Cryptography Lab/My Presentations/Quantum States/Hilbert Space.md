
>**Definition** Vector Space
>$V$ is a vector space if for all vectors $u,v,w \in V$ and scalars $a,b$:
>*Vector Addition:* $u + v$ is a vector
>*Scalar Property:* $au$ is a vector
>*Associativity of Addition:* $u + (v + w) = (u+v) + w$ 
>*Commutativity of Addition:* $u + v = v+ u$
>*Existence of Zero Vector:* $0$ vector exists
>*Compatability of Scalar Multiplication*
>*Identity Element of Multiplication:* $1u = u$
>*Distributivity:*
>- $au + av$
>- $(a+b)u = au + bu$
>- In other words, $V$ is a vector space if it is an abelian group under addition and its scalar multiplication is compatible (distribute + associative)

>**Definition** Hilbert Space
>A Hilbert space $H$ over a field $\Bbb{F}$ (usually $\Bbb{R}$ or $\Bbb{C}$) is a vector space with
>1. **Inner Product**
>$H$ is a Hilbert space if it is equipped with an inner product
>$$\langle .,.\rangle : H \times H \to \Bbb{F}$$
>satisfying the following properties for all $u,v,w \in H$ and $\alpha \in \Bbb{F}$:
>	1. *Linearity*
>	$\langle \alpha u + v, w \rangle = \alpha \langle u,w \rangle + \langle v,w \rangle$
>	2. *Conjugate Symmetry*
>	$\langle u,v \rangle = \overline{\langle v, u \rangle}$
>	3. *Positive-definiteness*
>	$\langle v,v \rangle \ge 0$ and $\langle v,v \rangle = 0 \iff v = 0$
>	
>2. **Cauchy-Completeness**
>The inner product defines a norm on $H$:
>$$||v|| := \sqrt{\langle v,v \rangle}$$
>$H$ is a Hilbert space if it is complete with respect to its norm. That is, for every Cauchy sequence $(v_n) \subset H$,
>$$\lim_{n \to \infty} v_n = v \in H$$
>exists in the norm induced by the inner product:
>$$\lim_{n \to \infty} || v_n - v || = 0$$
> 
> To recap, a Hilbert space is a **vector space** + **inner product** + **Cauchy complete**