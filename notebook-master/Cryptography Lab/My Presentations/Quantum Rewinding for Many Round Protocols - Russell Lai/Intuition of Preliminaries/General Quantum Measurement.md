>**Definition** General Measurement
>A *general measurement* is a CPTP map $M: S(\mathcal{H}) \to S(\mathcal{H} \otimes \mathcal{O})$ where $\mathcal{O}$ is an ancilla register holding a classical outcome. Specifically, given measurement operators $\{M_i\}_{i=1}^N$ such that $\sum\limits_{i=1}^n M_iM_i^\dagger = \bf{I}$ and $\{|i\rangle\}_{i=1}^N$ for $\mathcal{O}$, $$M(\rho) = \sum\limits_{i=1}^N(M_i\rho M_i^\dagger \otimes |i\rangle\langle i|^\mathcal{O})$$

$\mathcal{O}$: The *"outcome register"*

This is an *ancillary Hilbert space* that stores which classical outcome you get when you measure.

It has an orthonormal basis $\{|i\rangle\}_{i=1}^N$, one for each measurement outcome