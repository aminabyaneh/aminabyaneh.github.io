---
title: "Learning Lyapunov-Stable Polynomial Dynamical Systems through Imitation"
date: 2023-10-15
tags: ["robotics","imitation learning","dynamical systems", "semi-definite programming"]
author: "Amin Abyaneh, Hsiu-Chin Lin"
description: "We present an approach for learning policies represented by globally stable nonlinear dynamical systems."
symmary: " We present an approach for learning policies represented by globally stable nonlinear dynamical systems. We model the nonlinear dynamical system as a parametric polynomial and learn the polynomial's coefficients jointly with a learnable Lyapunov candidate to guarantee stability and predictability of the policy."
cover:
    image: "featured.png"
    alt: "Learning polynomial dynamical systems with parametric ODEs for imitation."
    relative: true

---

---

### Links

+ [Paper]('https://openreview.net/pdf?id=lILEtkWOXD')
+ [Project page](https://sites.google.com/view/contractive-dynamical-policies)
+ [Slides](https://gamma.app/docs/Contractive-Dynamical-Imitation-Policies-for-Efficient-Out-of-Sam-lvmoigk6846tu9a)

---


### Missing my first conference 
Unfortunately, I couldn't attend my first conference paper presentation at CoRL'23 due to US visa processing delays. I applied for a visa well in advance, but faced significant backlog issues that unfortunately persisted beyond the conference date. As of now (several months later), I'm still awaiting visa approval, which has been pending since October 2023.

### Summary of the approach 
Imitation learning is a paradigm to address complex motion planning problems by learning a policy to imitate an expert's behavior. However, relying solely on the expert's data might lead to unsafe actions when the robot deviates from the demonstrated trajectories. Stability guarantees have previously been provided utilizing nonlinear dynamical systems, acting as high-level motion planners, in conjunction with the Lyapunov stability theorem. Yet, these methods are prone to inaccurate policies, high computational cost, sample inefficiency, or quasi stability when replicating complex and highly nonlinear trajectories. To mitigate this problem, we present an approach for learning a globally stable nonlinear dynamical system as a motion planning policy. We model the nonlinear dynamical system as a parametric polynomial and learn the polynomial's coefficients jointly with a Lyapunov candidate. To showcase its success, we compare our method against the state of the art in simulation and conduct real-world experiments with the Kinova Gen3 Lite manipulator arm. Our experiments demonstrate the sample efficiency and reproduction accuracy of our method for various expert trajectories, while remaining stable in the face of perturbations.

### Design overview

Our method (PLYDS) benefits from trainable polynomial for both the planning policy and the safety certificate, providing adaptable complexity for different expert demonstrations.

![PLYDS design overview](plyds_overview.png)

### Summary of results
PLYDS is shown to improve over some baselines despite the simple formulation and computation efficiency for 2-dimensional motion planning problems.

![PLYDS results summary](plyds_results.png)

### Conference

This work was published at the **Conference on Robot Learning (CoRL)** 2023, a premier venue for research in robot learning and autonomous systems.


### Citation

"Contractive Diffusion Policies: Robust Action Diffusion via Contractive Score-Based Sampling with Differential Equations." ICLR 2026, under review.

```latex
@inproceedings{abyaneh2023learning,
  title={Learning Lyapunov-Stable Polynomial Dynamical Systems Through Imitation},
  author={Abyaneh, Amin and Lin, Hsiu-Chin},
  booktitle={7th Annual Conference on Robot Learning},
  year={2023}
}

```
