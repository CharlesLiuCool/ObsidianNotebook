>**Definition** Trace Distance
>The *trace distance* between states $\rho$, $\sigma$, denoted $d(\rho,\sigma)$, is defined as
>$$d(\rho,\sigma) = \frac{1}{2}\text{Tr}\left(\sqrt{(\rho-\sigma)^2}\right)$$

### **What We Want From Distance**

When we define the distance from two quantum states, or a measure of *how different* two quantum states $\rho$ and $\sigma$ are, it should be
1. Non-negative, zero only if $\rho = \sigma$
2. Symmetric: $d(\rho,\sigma) = d(\sigma,\rho)$
3. Satisfy the *triangle inequality*
4. Have operational meaning: quantify how well we can tell $\rho$ and $\sigma$ apart in an experiment
5. Be contractive under quantum operations (you can't increase the distinguishability by applying a quantum process)

We see that the square root and square effect helps create *non-negativity*. The $1/2$ constant then normalizes the distance.



>*Takeaway*:
>The trace is defined as $\frac{1}{2}\text{Tr}\left(\sqrt{(\rho-\sigma)^2}\right)$ because it is the *unique measure* of distance that
>1. Generalizes classical probability distance
>2. Captures physical distinguishability
>3. Behaves correctly under quantum operations