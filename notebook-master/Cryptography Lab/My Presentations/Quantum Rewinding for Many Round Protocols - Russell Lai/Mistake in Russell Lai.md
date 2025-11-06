We know a general measurement looks like this:

$$M(\rho) = \sum\limits_{i=1}^N(M_i\rho M_i^\dagger \otimes |i\rangle\langle i|^\mathcal{O})$$

Russell Lai in his paper writes this condition:
$$\sum\limits_i M_iM_i^{\dagger} = \bf{I}$$

Suppose we take the trace to see if probability is conserved:
$$\begin{align} \text{Tr}(M(\rho)|i\rangle \langle i |^{\mathcal{O}}) &= \text{Tr}\left(\sum\limits_{i=1}^N(M_i\rho M_i^\dagger)\right) \\ &= \sum\limits_{i}^{N}\text{Tr}(M_i \rho M_i^{\dagger}) = \text{Tr}(M_i^{\dagger}M_i \rho) \\ &= \text{Tr}(\rho M_i^{\dagger}M_i)\end{align}$$

Notice that whichever way you use the cyclic property of trace, the identity doesn't resolve!