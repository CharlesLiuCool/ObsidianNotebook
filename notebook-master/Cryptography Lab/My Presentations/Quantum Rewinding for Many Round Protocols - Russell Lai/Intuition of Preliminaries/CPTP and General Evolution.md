### **Isolated Systems: Unitary Evolution**

If a system is *closed* (no interaction with an environment), its time evolution is *unitary*.
$$\rho' = U\rho U^\dagger$$
where $U$ is a *unitary matrix* ($U^\dagger U = I$)

This evolution preserves both:
- *trace*: $\text{Tr}(\rho') = 1$
- *purity*: pure states remain pure

### **Open Systems: General (Non-Unitary) Evolution**

In reality, quantum systems often interact with an environment, they are *open* systems.

This evolution is not necessarily unitary when viewed only on the system.

Examples include:
- decoherence
- noise
- measurement
- dissipation
- partial observation

To describe these processes, we use a *completely positive trace-preserving (CPTP) map*, often called a *quantum channel* or *quantum operation*.

### **Breaking Down the CPTP Acronym**

>*Completely Positive*:
>A map $T$ is positive if it sends positive operators to positive operators.
$$\rho \ge 0 \implies T(\rho) \ge 0$$
 Completely positive means this still holds even if the system is entangled with something else.

>*Trace Preserving*
>This means probabilities remain normalized:
>$$\text{Tr}(T(\rho)) = \text{Tr}(\rho) = 1$$
>for all density matrices $\rho$

### **Kraus Representation (Concrete Form)**

Every CPTP map can be written in the *Kraus form*:
$$T(\rho) = \sum\limits_i K_i \rho K_i^\dagger$$
where the Kraus operators $K_i$ satisfy:
$$\sum\limits_i K_i^\dagger K_i = \textbf{I}$$
This condition guarantees trace preservation.