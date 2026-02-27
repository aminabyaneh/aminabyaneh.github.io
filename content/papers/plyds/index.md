---
title: 'Learning Lyapunov-Stable Polynomial Dynamical Systems through Imitation'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Hsiu-Chin Lin

date: '2023-10-12T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2023-10-12'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In Annual Conference on Robot Learning, 2023
publication_short: In CoRL'23

abstract: Imitation learning is a paradigm to address complex motion planning problems by learning a policy to imitate an expert's behavior. However, relying solely on the expert's data might lead to unsafe actions when the robot deviates from the demonstrated trajectories. Stability guarantees have previously been provided utilizing nonlinear dynamical systems, acting as high-level motion planners, in conjunction with the Lyapunov stability theorem. Yet, these methods are prone to inaccurate policies, high computational cost, sample inefficiency, or quasi stability when replicating complex and highly nonlinear trajectories. To mitigate this problem, we present an approach for learning a globally stable nonlinear dynamical system as a motion planning policy. We model the nonlinear dynamical system as a parametric polynomial and learn the polynomial's coefficients jointly with a Lyapunov candidate. To showcase its success, we compare our method against the state of the art in simulation and conduct real-world experiments with the Kinova Gen3 Lite manipulator arm. Our experiments demonstrate the sample efficiency and reproduction accuracy of our method for various expert trajectories, while remaining stable in the face of perturbations.


# Summary. An optional shortened abstract.
summary: We present an approach for learning policies represented by globally stable nonlinear dynamical systems. We model the nonlinear dynamical system as a parametric polynomial and learn the polynomial's coefficients jointly with a learnable Lyapunov candidate to guarantee stability and predictability of the policy.

tags:
  - Conference on Robot Learning (CoRL'23)
  - Imitation Learning
  - Robot Learning
  - Lyapunov theory

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/abs/2310.20605'
url_code: 'https://github.com/aminabyaneh/stable-imitation-policy'
url_dataset: ''
url_poster: 'https://drive.google.com/file/d/1QBMQVzuocySfURW1INlJKVGvjVH9fj3G/view?usp=sharing'
url_project: 'https://sites.google.com/view/stable-planning-policy/home'
url_slides: 'https://docs.google.com/presentation/d/14Eg5DkXPMrhJQa8rMqGuZFRG36uDOLWD/edit?usp=sharing&ouid=113296321850592254083&rtpof=true&sd=true'
url_source: ''
url_video: 'https://drive.google.com/file/d/1SqdKfHae_cefYmPxDGgcGPt5HX2ZpJSX/view'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Real-world experiments on Kinova Gen3 Lite'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
  - plyds

---
<br>

### Design overview

Our method (PLYDS) benefits from trainable polynomial for both the planning policy and the safety certificate, providing adaptable complexity for different expert demonstrations.

![PLYDS design overview](plyds_overview.png)

### Summary of results
PLYDS is shown to improve over some baselines despite the simple formulation and computation efficiency for 2-dimensional motion planning problems.

![PLYDS results summary](plyds_results.png)
