Because amplitudes are complex, probabilities can interfere.

Consider the two-slit electron experiment, with two slits A and B.

Traditional probability tells us since events electron pass through $A$ and $B$ are mutually exclusive,
$$P(A) + P(B)$$

In the quantum world, however the total *amplitude* at any point $x$ on the screen that catches the electron is the sum of two path amplitudes:
$$\Psi(x) = \psi_A(x) + \psi_B(x)$$
Each path $i$ contributes:
$$\psi_i(x) = |\psi_i(x)|e^{i\theta_i(x)}$$
where
- $|\psi_i|$ is the *magnitude* (how much of the wave reaches that point from slit $i$)
- $\theta_i$ is the phase accumulated along that path.

From here, we can compute *observable probability* to detect the electron at point $x$. This is the magnitude squared of the total amplitude:
$$\begin{align}P(x) &= (\Psi(x))^2 = (\psi_A + \psi_B)(\psi_A^* + \psi_B^*) \\ &= |\psi_A|^2 + |\psi_B|^2 + \psi_A\psi_B^* + \psi_A^*\psi_B\end{align}$$

Using the polar form, we can write $\psi_A = |\psi_A|e^{i\theta_1}$ and $\psi_B = |\psi_B|e^{i\theta_2}$.

So,
$$\psi_A\psi_B^* = |\psi_A||\psi_B|e^{i(\theta_1-\theta_2)}= |\psi_A||\psi_B|e^{-i\Delta\theta}$$
and
$$\psi_A^*\psi_B = |\psi_A||\psi_B|e^{i(\theta_1-\theta_2)}= |\psi_A||\psi_B|e^{i\Delta\theta}$$

So,
$$P(x) = |\psi_A|^2 + |\psi_B|^2 + 2|\psi_A||\psi_B|\cos(\Delta \theta)$$