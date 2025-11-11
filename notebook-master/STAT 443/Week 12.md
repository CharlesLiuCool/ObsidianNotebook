### **Limiting Theorem for Sums**

>**Theorem.** Central Limit Theorem
>If $X_1, ..., X_n$ is a random sample from distribution with mean $\mu$ and variance $\sigma^2 < \infty$ then the limiting distribution of
>$$Z_n = \frac{\sum\limits_{i=1}^n X_i - n\mu}{\sqrt{n}\sigma} = \frac{\sum\limits_{i=1}^n X_i/n - \mu}{\sigma/\sqrt{n}} = \frac{\overline{X}_n - \mu}{\sigma/\sqrt{n}}$$
>is the standard normal distribution; that is $Z_n \xrightarrow{d} Z \sim N(0,1)$ as $n \to \infty$

![[Week 12 2025-11-06 13.38.49.excalidraw|center]]

### **Approximations**

Let $X_1,...X_n$ be a random sample from a Bernoulli distribution, $X_i \sim \text{BIN}(1,p)$, and  consider the sum $Y_n = \sum\limits_{i-1}^nX_i$ that has binomial distribution $\text{BIN}(n,p)$

Let $\overline{Y}_n - \sum\limits_{i=1}^n X_i/n$ denote the sample proportion.

- First-Order Limit (no constraint, no scaling):
$$\overline{Y}_n \xrightarrow{d} p$$
- Second-Order Limit (Poisson Approximation; under the constraint $np = \mu$):
$$n\overline{Y}_n = Y_n \xrightarrow{d} Y$$
where $Y$ has the Poisson distribution with mean $\mu$.

### **Second-Order: Normal Approximation**

Let $X_1,...,X_n$ be a random sample from a Bernoulli distribution $X_i \sim \text{BIN}(1,p)$, and consider the sum $Y_n = \sum\limits_{i=1}^n X_i \sim \text{BIN}(n,p)$, under the constraint that $np > 5$, $nq >5$, where $q = 1-p$.
- $\mu_n = E(Y_n) = np$ and $\sigma_n^2 = \text{Var}(Y_n) = np(1-p) = npq$
- Standardization: $Z_n = (Y_n - np)/\sqrt{npq}$
- $Z_n \xrightarrow{d} Z$, where $Z$ has the distribution $N(0,1)$. That is, when $n$ is large,
$$P(Y \le np + x \sqrt{npq}) = P\left(\frac{Y_n - np}{\sqrt{npq}} \le x\right) \approx \Phi(x)$$
where $\Phi(x)$ is the CDF of $N(0,1)$.

### **Continuity Correction Factor**
For histogram with interval $1$,
- $P(2 \le X < 4) = P(1.5 \le X \le 3.5)$
- $P(2 < X \le 4) = P(2.5 \le x \le 4.5)$

As we see, we need to adjust interval since the we're using the continuous normal distribution to approximate the discrete values (from histogram).

### **Normal Approximation**

Let $Y_\mu$ be a random variable from a Poisson distribution $\text{POI}(\mu)$
- $E(Y_\mu) = \mu$ and $\text{Var}(Y_\mu) = \mu$
- Standardization:
$$Z_\mu = \frac{Y_\mu - \mu}{\sqrt{\mu}}$$
- Central limit theorem implies that $Z_\mu \xrightarrow{d} Z$, as $\mu \to \infty$, where $Z$ has the distribution $N(0,1)$
- The idea of the direct proof: Using the moment generating functions.