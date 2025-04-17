---
title: 🎉 New publication at ICLR 2025!
summary: Our paper on contractive dynamical imitation policies will be a part of ICLR 2025 in Singapore. If you're in Singapore around that time, come to our poster session, 10:30–12 in Hall 3/2B, no. 39 to talk safe robotics 🤖!
date: 2025-04-16

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption:

authors:
  - admin

tags:
  - Academic
  - Publication
  - Robotics
  - Neural ODEs
---

We will be presenting our work "Contractive dynamical imitation policies for efficient out-of-sample recovery" at ICLR 2025 in Singapore!

{{< toc mobile_only=true is_open=true >}}

## Summer at NCCR and EPFL
This work is the result of an amazing collaboration with EPFL and NCCR Automation. The project's success is owed to dedicated work of senior PhD candidate, [Mahrokh G. Boroujeni](https://people.epfl.ch/mahrokh.ghoddousiboroujeni?lang=en), and Prof. [Giancarlo Ferrari-Trecate](https://www.epfl.ch/labs/decode/), both from EPFL. And of course my supervisor Prof. Hsiu-Chin Lin!

## Abstract

Imitation learning is a data-driven approach to learning policies from expert behavior, but it is prone to unreliable outcomes in out-of-sample (OOS) regions. While previous research relying on stable dynamical systems guarantees convergence to a desired state, it often overlooks transient behavior. We propose a framework for learning policies modeled by contractive dynamical systems, ensuring that all policy rollouts converge regardless of perturbations, and in turn, enable efficient OOS recovery. By leveraging recurrent equilibrium networks and coupling layers, the policy structure guarantees contractivity for any parameter choice, which facilitates unconstrained optimization. We also provide theoretical upper bounds for worst-case and expected loss to rigorously establish the reliability of our method in deployment. Empirically, we demonstrate substantial OOS performance improvements for simulated robotic manipulation and navigation tasks.

## Project website

👉 [**Check out the project website**](https://sites.google.com/view/contractive-dynamical-policies) for our codebase and highlight of the results.

## Review
In case you are interested in the review process, check [**this page**](https://openreview.net/forum?id=lILEtkWOXD&referrer=%5BAuthor%20Console%5D(%2Fgroup%3Fid%3DICLR.cc%2F2025%2FConference%2FAuthors%23your-submissions)).

## What is ICLR?
ICLR is the premier gathering of professionals dedicated to the advancement of the branch of artificial intelligence called representation learning. [**Check out their website for detailed info of ICLR in recent years!**](https://iclr.cc/)