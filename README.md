# Awesome-DDIM
## Variants of the DDIM Algorithm

**Denoising Diffusion Implicit Models (DDIM)** are a class of accelerated diffusion algorithms. While they share the exact same training objective as standard Denoising Diffusion Probabilistic Models (DDPM), they introduce a non-Markovian forward process. This modification bypasses the strict step-by-step chain, allowing for significantly faster inference times and deterministic sample trajectories.

The fundamental characteristic of the DDIM algorithm is a hyperparameter $\eta$ (eta) which controls the stochasticity (random noise) injected during sampling. By tuning this parameter, you unlock several key variations:

| Type | Year | Paper | Details |
| :--- | :--- | :--- | :--- |
| **Pure Deterministic DDIM** ($\eta = 0$) | 2020 | [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502) | [View Docs](./docs/deterministic-ddim.md) |
| **Stochastic Interpolation** ($0 < \eta < 1$) | 2020 | [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502) | [View Docs](./docs/stochastic-interpolation.md) |
| **Accelerated Trajectory Sampling** (Skipped Steps) | 2020 | [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502) | [View Docs](./docs/accelerated-sampling.md) |
| **Continuous-Time gDDIM** (Generalized DDIM) | 2022 | [g-DDIM: Generalized denoising diffusion implicit models](https://arxiv.org/abs/2206.05564) | [View Docs](./docs/gddim.md) |
