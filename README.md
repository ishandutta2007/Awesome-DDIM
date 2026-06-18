<div align="center">
<img src="./assets/banner.svg" alt="Awesome DDIM Banner" width="100%" />

# 🚀 Awesome-DDIM

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/badge.svg)](https://github.com/ishandutta2007/Awesome-Awesome-Awesome)
<a href="https://github.com/ishandutta2007"><img alt="GitHub followers" src="https://img.shields.io/github/followers/ishandutta2007?label=Follow" /></a>

**Accelerating Diffusion Models with Denoising Diffusion Implicit Models (DDIM)**

[Overview](#-overview) • [Variants](#-variants-of-the-ddim-algorithm) • [Documentation](./docs) • [Contributing](#-contributing)

</div>

## 📖 Overview

**Denoising Diffusion Implicit Models (DDIM)** are a class of accelerated diffusion algorithms. While they share the exact same training objective as standard Denoising Diffusion Probabilistic Models (DDPM), they introduce a non-Markovian forward process. This modification bypasses the strict step-by-step chain, allowing for significantly faster inference times and deterministic sample trajectories.

![DDIM Sampling Process](https://raw.githubusercontent.com/jiamings/ddim/master/images/ddim.gif)

## 🛠️ Variants of the DDIM Algorithm

The fundamental characteristic of the DDIM algorithm is a hyperparameter $\eta$ (eta) which controls the stochasticity (random noise) injected during sampling. By tuning this parameter, you unlock several key variations:

| Type | Year | Paper | Details |
| :--- | :--- | :--- | :--- |
| **Pure Deterministic DDIM** ($\eta = 0$) | 2020 | [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502) | [View Docs](./docs/deterministic-ddim.md) |
| **Stochastic Interpolation** ($0 < \eta < 1$) | 2020 | [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502) | [View Docs](./docs/stochastic-interpolation.md) |
| **Accelerated Trajectory Sampling** (Skipped Steps) | 2020 | [Denoising Diffusion Implicit Models](https://arxiv.org/abs/2010.02502) | [View Docs](./docs/accelerated-sampling.md) |
| **Continuous-Time gDDIM** (Generalized DDIM) | 2022 | [g-DDIM: Generalized denoising diffusion implicit models](https://arxiv.org/abs/2206.05564) | [View Docs](./docs/gddim.md) |
