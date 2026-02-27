---
title: 'Contractive Dynamical Imitation Policies for Efficient Out-of-Sample Recovery'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Mahrokh G. Boroujeni
  - Hsiu-Chin Lin
  - Giancarlo Ferrari-Trecate

date: '2024-08-22T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2025-02-12'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In International Conference on Learning Representations, ICLR 2025
publication_short: In ICLR'25

abstract: Imitation learning is a data-driven approach to learning policies from expert behavior, but it is prone to unreliable outcomes in out-of-sample (OOS) regions. While previous research relying on stable dynamical systems guarantees convergence to a desired state, it often overlooks transient behavior. We propose a framework for learning policies modeled by contractive dynamical systems, ensuring that all policy rollouts converge regardless of perturbations, and in turn, enable efficient OOS recovery. By leveraging recurrent equilibrium networks and coupling layers, the policy structure guarantees contractivity for any parameter choice, which facilitates unconstrained optimization. We also provide theoretical upper bounds for worst-case and expected loss to rigorously establish the reliability of our method in deployment. Empirically, we demonstrate substantial OOS performance improvements for simulated robotic manipulation and navigation tasks. See sites.google.com/view/contractive-dynamical-policies for our codebase and highlight of the results.


# Summary. An optional shortened abstract.
summary: We introduce a class of contractive imitation policies with theoretical guarantees and out-of-sample error bounds for robot learning.

tags:
  - ICLR
  - Imitation Learning
  - Robot Learning
  - Contraction Theory
  - Neural ODE

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://openreview.net/pdf?id=lILEtkWOXD'
url_code: 'https://github.com/aminabyaneh/scds-contractive-imitation/tree/master'
url_dataset: ''
url_poster: 'https://drive.google.com/file/d/1rL2TkjTVCcltNQyCe2cifav97HbHrFZO/view?usp=sharing'
url_project: 'https://sites.google.com/view/contractive-dynamical-policies'
url_slides: 'https://gamma.app/docs/Contractive-Dynamical-Imitation-Policies-for-Efficient-Out-of-Sam-lvmoigk6846tu9a'
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Contraction theory enables efficient out-of-sample recovery'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
  - scds

---
<br>

### Design overview
The contraction property enables efficient out-of-sample recovery, especially in the face of perturbations. By utilizing contractive policies, we extend beyond the typical convergence guarantees of stable dynamical systems, offering certificates on the transient behavior of induced trajectories in addition to global convergence guarantees. We achieve notable improvements in out-of-sample recovery for various robots in navigation and manipulation tasks.

There are three main steps in learning contractive policies with SCDS:


 - Initial conditions are passed to the differentiable Neural ODE solver to generate state trajectories.

 - A tailor-made loss penalizes the discrepancy of the generate and expert trajectories, and updates the policy parameters.

 - Within the contractive policy, the REN module ensures contraction, the linear transformation adjusts the dimension of the latent space, and the bijection block boosts the policy's expressive power while preserving contraction properties.

![SCDS design overview](scds_overview.png)

### Summary of results
After training on expert demonstrations, the policy can be deployed with a low-level controller. The contractivity and, in turn, global stability of the policy facilitates reliable execution and out-of-sample recovery.

![SCDS results summary](scds_lasa_policies.png)

Theoretically, our method can be deployed for planning in various robotics systems and scenarios. We explore such use case for manipulation and navigation on Franka Panda and Clearpath Jackal robots, respectively.

![SCDS simulation in Isaac Lab](scds_simreal.png)