---
title: 'Globally Stable Neural Imitation Policies'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Mariana Sosa
  - Hsiu-Chin Lin


date: '2024-05-10T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2024-05-10'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In IEEE International Conference on Robotic and Automation, 2024
publication_short: In ICRA'24

abstract: Imitation learning presents an effective approach to alleviate the resource-intensive and time-consuming nature of policy learning from scratch in the solution space. Even though the resulting policy can mimic expert demonstrations reliably, it often lacks predictability in unexplored regions of the state-space, giving rise to significant safety concerns in the face of perturbations. To address these challenges, we introduce the Stable Neural Dynamical System (SNDS), an imitation learning regime which produces a policy with formal stability guarantees. We deploy a neural policy architecture that facilitates the representation of stability based on Lyapunov theorem, and jointly train the policy and its corresponding Lyapunov candidate to ensure global stability. We validate our approach by conducting extensive experiments in simulation and successfully deploying the trained policies on a real-world manipulator arm. The experimental results demonstrate that our method overcomes the instability, accuracy, and computational intensity problems associated with previous imitation learning methods, making our method a promising solution for stable policy learning in complex planning scenarios.


# Summary. An optional shortened abstract.
summary: In this project, we developed the Stable Neural Dynamical System (SNDS) to improve imitation policies by ensuring stability of the trained policy. Our approach uses a neural policy architecture based on the Lyapunov theorem to provide formal stability guarantees. We jointly train the policy and a Lyapunov candidate to ensure global stability.

tags:
  - IEEE International Conference on Robotics and Automation (ICRA'2024)
  - Safe Learning
  - Robot Learning
  - Lyapunov theory

# Display this page in the Featured widget?
featured: true

url_pdf: 'https://arxiv.org/abs/2403.04118'
url_code: 'https://github.com/aminabyaneh/stable-imitation-policy'
url_dataset: ''
url_poster: 'https://drive.google.com/file/d/1ISWTZKnMWd9HYHaERS7XUEJ4XqioasLh/view?usp=sharing'
url_project: 'https://sites.google.com/view/stable-planning-policy/home'
url_slides: 'https://docs.google.com/presentation/d/14Eg5DkXPMrhJQa8rMqGuZFRG36uDOLWD/edit?usp=sharing&ouid=113296321850592254083&rtpof=true&sd=true'
url_source: ''
url_video: 'https://drive.google.com/file/d/1VvL_3jUzKsEpYfk4YgiQYbo9jbtV4Yqf/view?usp=sharing'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Image credit: kinovarobotics.com'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
  - snds

---
<br>

### Design overview

Our approach uses a neural policy architecture based on the Lyapunov theorem to provide formal stability guarantees, using projection at each step, and a cost function tailored to yield reliable policy rollouts by adding both a state and action term in the overall loss function.

![SNDS design overview](snds_overview.png)

### Summary of results
Through extensive simulations and real-world tests on a manipulator arm, we demonstrated that SNDS addresses instability, accuracy, and computational challenges better than previous imitation learning methods, making it a promising solution for stable policy learning in complex scenarios.

![SNDS results summary](snds_results.png)
