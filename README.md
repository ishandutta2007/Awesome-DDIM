# Awesome-DDIM
## Variants of the DDIM Algorithm

**Denoising Diffusion Implicit Models (DDIM)** are a class of accelerated diffusion algorithms. While they share the exact same training objective as standard Denoising Diffusion Probabilistic Models (DDPM), they introduce a non-Markovian forward process. This modification bypasses the strict step-by-step chain, allowing for significantly faster inference times and deterministic sample trajectories.

The fundamental characteristic of the DDIM algorithm is a hyperparameter $\eta$ (eta) which controls the stochasticity (random noise) injected during sampling. By tuning this parameter, you unlock several key variations:

## 1. Pure Deterministic DDIM ($\eta = 0$)
When $\eta = 0$, the backward diffusion process becomes entirely deterministic. 

* **How it works:** Instead of adding random Gaussian noise at each step, the model follows a fixed ordinary differential equation (ODE) trajectory.
* **Benefits:** Allows for exact latent-space inversion (perfectly encoding an image back into noise and reconstructing it) and smooth semantic image interpolation.
* **Use Case:** Best for applications requiring frame-to-frame consistency (e.g., video synthesis) or reproducible image generation.

## 2. Stochastic Interpolation ($0 < \eta < 1$)
This variant represents a hybrid spectrum between traditional DDPM and pure DDIM. 

* **How it works:** The variance of the noise added at each step is scaled by $\eta^2$. 
* **Benefits:** Provides a tunable trade-off between the speed of DDIM and the creative variability of DDPM.
* **Use Case:** Useful when you want to accelerate the generation process but still retain a degree of stochastic variation for creative exploration.

## 3. Accelerated Trajectory Sampling (Skipped Steps)
Standard diffusion models require hundreds or thousands of steps to generate an image. Because DDIM formulates the generative process as a subsequence of the original diffusion steps (represented as $\tau$), you can sample from any arbitrary subset of timesteps.

* **How it works:** The scheduler steps through a defined interval (e.g., every $10^{\text{th}}$ or $20^{\text{th}}$ step) instead of evaluating every single timestep sequentially.
* **Benefits:** Drastically reduces computational overhead, generating high-quality results 10× to 50× faster. 
* **Use Case:** Critical for reducing latency in large models (like Stable Diffusion) for real-time or interactive applications.

## 4. Continuous-Time gDDIM (Generalized DDIM)
As diffusion research evolved, methods like Generalized DDIM (gDDIM) were introduced to treat the discrete steps of DDIM as a continuous-time probability flow ODE.

* **How it works:** Maps the transition probabilities to continuous differential equation equations.
* **Benefits:** Provides a clearer mathematical foundation that allows advanced numerical solvers (e.g., Runge-Kutta, Heun's method) to further optimize step trajectories and quality. 
* **Use Case:** Forms the backbone of state-of-the-art continuous text-to-image pipelines.
