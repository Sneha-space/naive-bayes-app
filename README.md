# 🧮 Naive Bayes Learning App

> An interactive, browser-based web application that teaches the **Naive Bayes classification algorithm** step by step — from raw CSV upload to full model evaluation — with visual explanations, mathematical walkthroughs, and zero installation.

![HTML](https://img.shields.io/badge/HTML-5-orange?style=flat-square&logo=html5)
![CSS](https://img.shields.io/badge/CSS-3-blue?style=flat-square&logo=css3)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow?style=flat-square&logo=javascript)
![Chart.js](https://img.shields.io/badge/Chart.js-4.4-pink?style=flat-square)
![No Install](https://img.shields.io/badge/No%20Install-Just%20Open-brightgreen?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-success?style=flat-square)

---

## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Live Demo](#-live-demo)
- [Tech Stack](#-tech-stack)
- [Features](#-features)
- [Pipeline Stages](#-pipeline-stages)
- [How to Run](#-how-to-run)
- [Dataset Compatibility](#-dataset-compatibility)
- [Project Structure](#-project-structure)
- [Educational Design](#-educational-design)
- [Future Improvements](#-future-improvements)
- [References](#-references)
- [Author](#-author)

---

## 📖 About the Project

This app was built as a **CIA‑1 assignment** for the course *Introduction to Machine Learning* (B.Tech CSE AI/ML, 2nd Year).

The goal is to provide a web-based learning tool that helps engineering students **understand, visualize, and experiment** with Naive Bayes from scratch — without installing Python, Jupyter, or any external libraries.

The interface is inspired by **Google Colab / notebook‑style** workflows: collapsible stages, top‑to‑bottom execution flow, and inline explanations next to every computation.

---

## 🌐 Live Demo

> **Live URL:**  
> https://sneha-space.github.io/naive-bayes-app/

Open that link in any modern browser and start using the app — no server, no backend, no installation.

You can also run it locally:

```bash
# Just download/clone and open
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

---

## 🛠️ Tech Stack

| Technology            | Purpose                                                   |
|-----------------------|-----------------------------------------------------------|
| **HTML5 + CSS3**      | Structure, layout, and dark‑theme UI                     |
| **Vanilla JavaScript**| ML logic, state management, UI interactions              |
| **Papa Parse 5.4**    | CSV parsing in the browser (CDN)                         |
| **Chart.js 4.4**      | Histograms, bar charts, line charts, doughnut charts     |
| **Google Fonts**      | JetBrains Mono + IBM Plex Sans typography                |

> No npm. No Node.js. No frameworks. No build step. Everything runs in a single `index.html` file.

---

## ✨ Features

- **Drag‑and‑drop CSV upload** with instant dataset preview
- **Full preprocessing pipeline** — missing values, encoding, scaling, feature selection
- **EDA visualizations** — class distribution, feature distributions, correlation heatmap
- **Step‑by‑step NB math** — priors, likelihoods, independence assumption, posterior
- **Gaussian NB** with Gaussian PDF curve overlays per class per feature
- **Multinomial NB** with Laplace smoothing and zero‑frequency problem highlighting
- **Train/Test split** with adjustable slider (e.g. 50–90%)
- **k‑Fold cross‑validation** with fold‑wise accuracy summaries
- **Custom sample prediction** with full log‑space computation walkthrough
- **Confusion matrix** + Precision / Recall / F1 per class + macro averages
- **Persistent help drawer** — Glossary, Why Each Step, Common Mistakes, Formula Sheet

---

## 🔢 Pipeline Stages

The app is structured as a **9‑stage learning pipeline** — each stage builds on the previous one:

| Stage | Name                   | What Happens                                                                 |
|-------|------------------------|------------------------------------------------------------------------------|
| **1** | Dataset Input          | Upload CSV, preview data, detect column types, select target column         |
| **2** | Preprocessing          | Handle nulls, encode categoricals, scale features, select features          |
| **3** | EDA                    | Class distribution chart, feature distributions by class, correlation heatmap |
| **4** | NB Learning Module     | Priors, likelihoods, independence assumption, posterior walkthrough         |
| **5** | Training Configuration | Train/test split slider, k‑fold toggle, shuffling, dataset split            |
| **6** | Model Visualization    | Learned parameters table, Gaussian curves / multinomial bar charts          |
| **7** | Prediction & Inference | Enter custom sample, see log‑space calculations and predicted class         |
| **8** | Evaluation Metrics     | Confusion matrix, TP/FP/FN/TN, Precision/Recall/F1, macro averages          |
| **9** | Educational Summary    | Recap of NB steps, tips for further study and exam preparation              |

---

## ▶️ How to Run

### Option 1 — Run locally

```bash
git clone https://github.com/Sneha-space/naive-bayes-app.git
cd naive-bayes-app
open index.html       # or start / xdg-open depending on OS
```

1. Download or clone this repository.  
2. Open `index.html` in **Chrome** or **Firefox**.  
3. Upload any labeled CSV file.  
4. Work through the 9 stages from top to bottom.

### Option 2 — Host on GitHub Pages (already done for this repo)

If you fork or reuse this project:

1. Push your code to a GitHub repository.  
2. Go to **Settings → Pages → Source: `main` branch / `/root`**.  
3. GitHub will give you a public URL like:

```text
https://<your-username>.github.io/<your-repo-name>/
```

> **Requirements:** Any modern browser (Chrome recommended). After the first load of CDN scripts, the app can run fully offline with your CSV.

---

## 📁 Dataset Compatibility

The app works with **any labeled CSV dataset**.

Recommended starter datasets:

| Dataset         | Features      | Classes            | Source |
|----------------|---------------|--------------------|--------|
| **Iris**       | 4 numeric     | 3 species          | [Kaggle](https://www.kaggle.com/datasets/uciml/iris) |
| **Play Tennis**| 4 categorical | Yes / No           | ML textbooks |
| **Titanic**    | Mixed         | Survived / Not     | [Kaggle](https://www.kaggle.com/c/titanic) |
| **SMS Spam**   | Text / vectors| Spam / Ham         | [Kaggle](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) |
| **Wine Quality**| 11 numeric   | Quality 3–8        | [UCI](https://archive.ics.uci.edu/ml/datasets/wine+quality) |

**CSV Requirements:**

- Must have a **header row**.  
- One column must be the **class/target label**.  
- Supports both numeric and categorical features.  
- Missing values can be handled interactively in Stage 2.

---

## 🗂️ Project Structure

```text
naive-bayes-app/
├── index.html    # Complete application — HTML, CSS, and JS in one file
└── README.md     # Project documentation
```

> The entire app is self‑contained in `index.html`. External libraries are loaded from CDNs.

---

## 🎓 Educational Design

This app is designed for **students learning ML for the first time**. The focus is on transparency and intuition, not black‑box automation.

### Mathematical transparency

Formulas are shown with **real numbers substituted in**, not just symbols. You see things like:

- `P(setosa) = 50 / 150 = 0.3333`  
- `log P(setosa) = log(0.3333) = −1.0986`

instead of only \( P(C) \) or \( \log P(C) \).

### Log‑space computation

All posterior calculations are done in **log‑space** and exposed in the UI, so students learn:

- Why multiplying many small probabilities causes numerical underflow.  
- How log‑probabilities turn products into sums and avoid underflow.

### Laplace smoothing visualisation

In the Multinomial NB view:

- Zero‑count cells in the frequency tables are clearly highlighted.  
- Students can see exactly which values would cause the zero‑frequency problem.  
- The effect of “+1” smoothing on the probabilities is made explicit.

### Before/After comparisons

Every major preprocessing step in Stage 2 shows **before vs after**:

- Missing value handling  
- Encoding (Label / One‑Hot)  
- Scaling (Min–Max / Z‑score)  

This makes the impact of each transformation concrete.

### Persistent help system

A `?` button is always visible in the bottom‑right corner. The help drawer includes:

- A **glossary** of key terms.  
- A **“Why this step?”** explanation for each stage.  
- A list of **common mistakes** (e.g., using Gaussian NB on count data).  
- A **formula sheet** for quick revision.

---

## 🚀 Future Improvements

| Improvement             | Description                                        |
|-------------------------|----------------------------------------------------|
| Bernoulli NB support    | Handle binary feature datasets natively            |
| Sample dataset gallery  | One‑click loading for Iris, Titanic, Play Tennis  |
| Animated computation    | Animate the posterior calculation step by step    |
| Comparison mode         | Run Gaussian vs Multinomial side‑by‑side          |
| Export model            | Download learned parameters as JSON               |
| Report export           | Export evaluation summary as PDF                  |
| Mobile layout           | Improved responsiveness for tablets/phones        |
| Light theme toggle      | Optional light theme for accessibility            |

---

## 📚 References

- Mitchell, T. (1997). *Machine Learning*. McGraw‑Hill — Chapter 6: Bayesian Learning  
- Rish, I. (2001). *An Empirical Study of the Naive Bayes Classifier*. IJCAI Workshop on Empirical Methods in AI  
- Scikit‑learn — [Naive Bayes Documentation](https://scikit-learn.org/stable/modules/naive_bayes.html)  
- StatQuest (Josh Starmer) — [Naive Bayes, Clearly Explained](https://www.youtube.com/watch?v=O2L2Uv9pdDA)  
- 3Blue1Brown — [Bayes’ Theorem](https://www.youtube.com/watch?v=HZGCoVF3YvM)  
- NPTEL IIT Kharagpur — *Introduction to Machine Learning* (Prof. Sudeshna Sarkar)

---

## 👩‍💻 Author

**Sneha**  
B.Tech CSE (AI & ML) — 2nd Year  

*CIA‑1 Assignment: Design and Development of an Interactive Web-Based Learning System for Naive Bayes Classification*

---

<div align="center">
  <sub>Built with vanilla JavaScript — no frameworks, no backend, no installation. Just open and learn.</sub>
</div>
