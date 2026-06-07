---
title: "Toward Hardware-Agnostic Quadrupedal World Models via Morphology Conditioning"
date: 2026-04-01
tags: ["robotics", "world models", "quadrupedal locomotion", "morphology", "reinforcement learning", "zero-shot transfer"]
venue: "Preprint 2026"
author: "Mohamad H. Danesh, Chenhao Li, Amin Abyaneh, Anas Houssaini, Kirsty Ellis, Glen Berseth, Marco Hutter, Hsiu-Chin Lin"
description: "QWM conditions a quadrupedal world model on robot morphology, enabling zero-shot locomotion transfer to unseen hardware without retraining."
summary: "A single world model trained across eight quadrupeds that generalizes zero-shot to new robot morphologies by explicitly conditioning on physical specifications rather than baking in a fixed embodiment."
cover:
    image: "project_assets/thumbnail.gif"
    alt: "QWM zero-shot locomotion transfer"
    relative: true
---

---

### Links

+ [arXiv](https://arxiv.org/abs/2604.08780)
+ [Paper](https://arxiv.org/pdf/2604.08780)
+ [Project page](https://modanesh.github.io/papers/qwm/)

---

### The problem

World models are powerful but brittle. A model trained on one quadruped fails on another the moment the leg lengths, actuator specs, or mass distribution shift. Every new robot means a new model, which defeats the point of having a learned world model at all.

### QWM

QWM extends DreamerV3 with explicit morphology conditioning so the same model can reason about multiple robots at once. Three additions do the work:

- A **Physical Morphology Encoder** that turns kinematic, geometric, and actuation specs into a compact embedding
- **Morphology-conditioned recurrent dynamics** that inject this embedding at each step so predictions are robot-aware
- An **Adaptive Reward Normalizer** to handle the different reward scales that come with heterogeneous hardware

![QWM concept](project_assets/concept.png)

Training runs across eight distinct quadrupeds in parallel using Hetero-Isaac, a custom extension of NVIDIA Isaac Lab built for this purpose.

### Results

A single QWM generalizes zero-shot to Unitree Go1 and ANYmal-D, both held out during training, with zero falls across 20 trials and no fine-tuning. It outperforms DreamerV3, PWM, and TWISTER on the full heterogeneous robot cohort.

![Experiment results](project_assets/exps_results.png)

![Real-world deployment](project_assets/results_gif.png)

---

### Citation

```latex
@article{danesh2026qwm,
  author    = {Danesh, Mohamad H. and Li, Chenhao and Abyaneh, Amin and Houssaini, Anas and Ellis, Kirsty and Berseth, Glen and Hutter, Marco and Lin, Hsiu-Chin},
  title     = {Toward Hardware-Agnostic Quadrupedal World Models via Morphology Conditioning},
  journal   = {Preprint},
  year      = {2026},
}
```
