# Susmit Kumar Sahu — Personal Academic Website

[![al-folio](https://img.shields.io/badge/theme-al--folio-blue)](https://github.com/alshedivat/al-folio)
[![Jekyll](https://img.shields.io/badge/built%20with-Jekyll-red)](https://jekyllrb.com/)
[![GitHub Pages](https://img.shields.io/badge/hosted%20on-GitHub%20Pages-green)](https://pages.github.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

Personal academic/portfolio website for **Susmit Kumar Sahu**, Applied AI/ML Engineer at TCS Research.
Built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme.

🌐 **Live site:** [susmitkumarsahu.github.io](https://susmitkumarsahu.github.io) *(update after deployment)*

---

## 👤 About

- **Name:** Susmit Kumar Sahu
- **Role:** Applied AI/ML Engineer | GenAI & LLM Systems | Scientific ML & Digital Twin
- **Organization:** TCS Research, Pune, India
- **Education:** B.Tech + M.Tech, Mechanical Engineering (Product Design), IIITDM Kancheepuram (CGPA: 8.55)

---

## 📁 Repository Structure

```
susmit-portfolio/
├── _bibliography/
│   └── papers.bib              # BibTeX entries for publications
├── _data/
│   ├── socials.yml             # Social media links
│   └── repositories.yml        # GitHub repos to display
├── _news/                      # News/announcement items
│   ├── 2026-03-01-azure-workshop.md
│   ├── 2026-01-15-acs-paper.md
│   ├── 2025-11-01-ip-award.md
│   ├── 2025-06-01-imbrs-talk.md
│   ├── 2025-05-20-patent-filed.md
│   └── 2024-12-01-compflu-talk.md
├── _pages/
│   ├── about.md                # Home / About page
│   ├── blog.md                 # Blog listing
│   ├── cv.md                   # CV page
│   ├── projects.md             # Projects listing
│   ├── publications.md         # Publications (auto from BibTeX)
│   └── repositories.md         # GitHub repos
├── _posts/
│   ├── 2025-08-15-pinns-battery-modeling.md
│   └── 2025-11-10-agentic-parameter-estimation.md
├── _projects/
│   ├── 01_agentic_digital_twin.md
│   ├── 02_multi_agent_personalization.md
│   ├── 03_pinns_battery.md
│   ├── 04_battery_physics_modeling.md
│   └── 05_cfd_simulations.md
├── assets/
│   ├── img/
│   │   └── prof_pic.jpg        # ← ADD YOUR PHOTO HERE
│   ├── json/
│   │   └── resume.json         # JSONResume / CV data
│   └── pdf/
│       └── susmit_kumar_sahu_cv.pdf  # ← ADD YOUR CV PDF HERE
├── _config.yml                 # Main Jekyll configuration
├── Gemfile                     # Ruby gem dependencies
└── README.md
```

---

## 🚀 Quick Start: Deploying to GitHub Pages

### Step 1: Use the al-folio template

1. Go to [github.com/alshedivat/al-folio](https://github.com/alshedivat/al-folio)
2. Click **"Use this template"** → **"Create a new repository"**
3. Name your repository: `susmitkumarsahu.github.io` (replace with your GitHub username)
4. Set visibility to **Public**

### Step 2: Replace content files

Copy the files from this repository into your new al-folio repo, replacing the defaults:

```bash
# Clone your new repo
git clone https://github.com/susmitkumarsahu/susmitkumarsahu.github.io
cd susmitkumarsahu.github.io

# Copy files from this package (adjust paths as needed)
cp path/to/this-package/_config.yml .
cp path/to/this-package/_pages/* _pages/
cp path/to/this-package/_bibliography/papers.bib _bibliography/
cp path/to/this-package/_data/* _data/
cp path/to/this-package/_news/* _news/
cp path/to/this-package/_projects/* _projects/
cp path/to/this-package/_posts/* _posts/
cp path/to/this-package/assets/json/resume.json assets/json/
```

### Step 3: Add your personal assets

Place these files in the correct locations:

| File | Location | Notes |
|------|----------|-------|
| Your photo | `assets/img/prof_pic.jpg` | Square or portrait, min 400×400px |
| Your CV PDF | `assets/pdf/susmit_kumar_sahu_cv.pdf` | Optional |
| Project images | `assets/img/projects/` | Referenced in `_projects/*.md` |

### Step 4: Update `_config.yml`

Open `_config.yml` and update the following fields:

```yaml
url: https://susmitkumarsahu.github.io   # your GitHub Pages URL
github_username: susmitkumarsahu          # your GitHub username
google_scholar_userid: XXXXXXXX           # your Google Scholar ID
```

### Step 5: Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. The al-folio template includes a pre-configured `.github/workflows/deploy.yml`
4. Push your changes — GitHub Actions will build and deploy automatically

```bash
git add .
git commit -m "Customize al-folio with Susmit's content"
git push origin main
```

Your site will be live at: `https://susmitkumarsahu.github.io` ✅

---

## 🛠️ Local Development

### Prerequisites

- Ruby ≥ 3.0
- Bundler: `gem install bundler`
- ImageMagick (for image processing): `brew install imagemagick` or `apt install imagemagick`

### Run locally

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve --livereload

# Visit: http://localhost:4000
```

### Using Docker (recommended)

```bash
# Using the al-folio Docker image
docker run -it --rm \
  --volume="$PWD:/srv/jekyll" \
  -p 4000:4000 \
  amirpourmand/al-folio:latest \
  jekyll serve --watch --livereload --host 0.0.0.0
```

---

## ✏️ Customization Guide

### Adding a new publication

Edit `_bibliography/papers.bib` and add a BibTeX entry:

```bibtex
@article{sahu2026newpaper,
  title   = {Your Paper Title},
  author  = {Sahu, Susmit Kumar and others},
  journal = {Journal Name},
  year    = {2026},
  selected = {true}   # shows on homepage
}
```

### Adding a news item

Create a new file in `_news/`:

```markdown
---
layout: post
date: 2026-04-01
inline: true
---
Your news announcement here. Supports **Markdown**.
```

### Adding a project

Create a new file in `_projects/`:

```markdown
---
layout: page
title: My New Project
description: Short description shown on the projects grid.
img: assets/img/projects/my_project.jpg
importance: 1
category: GenAI & Agentic AI
---

Full project description with Markdown...
```

### Changing theme color

In `_sass/_themes.scss` (from the al-folio base repo), update the `$theme-color` variable:

```scss
$theme-color: #4285f4;  // Google Blue — or any hex color you prefer
```

### Updating the CV

Edit `assets/json/resume.json` to update work, education, skills, and certifications.
The CV page renders automatically from this file.

---

## 📚 Content Summary

### Publications
| Title | Venue | Year |
|-------|-------|------|
| Multiscale Electro-Mechanical Modeling of Hard-Carbon Anodes in Sodium-Ion Batteries | ACS Applied Energy Materials | 2026 |
| Method and System for Composite Electrode Design for Enhanced Battery Performance | Patent Filed | 2025 |
| Commercial Hexapod Hydroponic System for Urban Farming | Patent Filed | 2023 |

### Projects
| Project | Category |
|---------|----------|
| GenAI Agentic System for Digital Twin & Parameter Estimation | GenAI & Agentic AI |
| Multi-Agent GenAI System for Personalization | GenAI & Agentic AI |
| PINNs for Battery Pack Modelling | Scientific ML & Digital Twin |
| Physics-Based Battery Modeling & System Integration | Scientific ML & Digital Twin |
| Large-Scale CFD Simulations & Flow Optimization | CFD & Scientific Computing |

### Blog Posts
| Title | Date |
|-------|------|
| Physics-Informed Neural Networks: Bridging PDEs and Deep Learning for Battery Modeling | Aug 2025 |
| Building Agentic AI Workflows for Scientific Parameter Estimation | Nov 2025 |

---

## 🔗 TODOs After Deployment

- [ ] Add `prof_pic.jpg` to `assets/img/`
- [ ] Add CV PDF to `assets/pdf/`
- [ ] Add project images to `assets/img/projects/`
- [ ] Update `github_username` in `_config.yml`
- [ ] Update `google_scholar_userid` in `_config.yml`
- [ ] Update `linkedin_username` in `_config.yml`
- [ ] Add real GitHub repo names in `_data/repositories.yml`
- [ ] Enable GitHub Pages in repo Settings → Pages
- [ ] (Optional) Set up Google Analytics in `_config.yml`

---

## 📄 License

This website content is © 2026 Susmit Kumar Sahu.
The al-folio theme is open source under the [MIT License](https://github.com/alshedivat/al-folio/blob/main/LICENSE).
