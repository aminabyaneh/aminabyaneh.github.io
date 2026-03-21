---
title: "Contractive Dynamical Imitation Policies for Efficient Out-of-Sample Recovery"
date: 2025-01-15
tags: ["robotics","reinforcement learning","diffusion policies","contraction theory","stochastic differential equations"]
venue: "ICLR 2025"
author: "Amin Abyaneh*, Mahrokh Boroujeni*, Hsiu-Chin Lin, Giancarlo Ferrari-Trecate"
description: "Learning contractive dynamical systems with neural ODEs for imitation."
summary: "Imitation learning policies often fail when robots drift out-of-sample. We propose SCDS, a framework that models policies as contractive dynamical systems, ensuring all rollouts converge regardless of perturbations. The architecture guarantees contractivity by construction, enabling unconstrained optimization. We also provide formal bounds on worst-case and expected loss, and demonstrate strong out-of-sample recovery on manipulation and navigation tasks."
cover:
    image: "scds_overview.png"
    alt: "SCDS design overview"
    relative: true

---

---

### Links

+ [Paper](https://openreview.net/pdf?id=lILEtkWOXD)
+ [Project page](https://sites.google.com/view/contractive-dynamical-policies)
+ [Slides](https://gamma.app/docs/Contractive-Dynamical-Imitation-Policies-for-Efficient-Out-of-Sam-lvmoigk6846tu9a)

---

### A summer at NCCR and EPFL

This work grew out of a research visit to EPFL, made possible by [NCCR's Visiting Researcher's Fellowship](https://nccr-automation.ch/research-fellowship). The collaboration with [Mahrokh G. Boroujeni](https://people.epfl.ch/mahrokh.ghoddousiboroujeni?lang=en) and Prof. [Giancarlo Ferrari-Trecate](https://www.epfl.ch/labs/decode/) at EPFL's Laboratoire d'Automatique was central to everything here, as equal contributors in the truest sense.

### The problem: imitation learning breaks out-of-sample

Imitation learning policies learn from expert demonstrations and work well near the training distribution. But robots get perturbed. When they drift out-of-sample, most policies have no recovery guarantee, not even on *how fast* they return, let alone whether they do at all.

Prior work using stable dynamical systems guarantees eventual convergence to a goal, but says nothing about **transient behavior**: how the robot moves on its way back. This gap matters in practice.

### Our approach: contractivity as a stronger guarantee

We model the policy as a **contractive dynamical system**, a stronger condition than stability. Contraction means that any two trajectories starting from different initial conditions (or after a perturbation) actively pull toward each other over time. This gives certificates on both convergence *and* transient behavior.

The policy architecture has three components that work together:

- **REN module:** a recurrent equilibrium network that enforces contractivity by construction, for any choice of parameters
- **Linear transformation:** adjusts the dimensionality of the latent space
- **Bijection block:** boosts expressive power while preserving the contraction property

Because contractivity is baked into the architecture, training is **unconstrained optimization** with no projection steps or Lyapunov feasibility checks needed.

![SCDS design overview](scds_overview.png)

> We also derive theoretical upper bounds on worst-case and expected loss, grounding the empirical results in formal guarantees.

### Results

After training on expert demonstrations, SCDS policies can be deployed directly with a low-level controller. Contractivity ensures reliable execution and efficient recovery from perturbations across the board.

![SCDS results on LASA benchmark](scds_lasa_policies.png)

We evaluate on manipulation and navigation tasks using Franka Panda and Clearpath Jackal robots in Isaac Lab, demonstrating that the approach scales to realistic robotic settings.

![SCDS simulation in Isaac Lab](scds_simreal.png)

---

### Peer review

Curious about the review process? The full discussion is public on [**OpenReview**](https://openreview.net/forum?id=lILEtkWOXD&referrer=%5BAuthor%20Console%5D(%2Fgroup%3Fid%3DICLR.cc%2F2025%2FConference%2FAuthors%23your-submissions)).

### What is ICLR?
ICLR is the premier venue for research on representation learning and deep learning. [**Check out their website!**](https://iclr.cc/)

### Citation

`* equal contribution`

```latex
@inproceedings{abyaneh2025contractive,
title={Contractive Dynamical Imitation Policies for Efficient Out-of-Sample Recovery},
author={Amin Abyaneh and Mahrokh Ghoddousi Boroujeni and Hsiu-Chin Lin and Giancarlo Ferrari-Trecate},
booktitle={The Thirteenth International Conference on Learning Representations},
year={2025},
url={https://openreview.net/forum?id=lILEtkWOXD}
}
```
