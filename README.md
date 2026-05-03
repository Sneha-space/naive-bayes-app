# 🧮 Naive Bayes Learning App

> An interactive, browser-based web application that teaches the **Naive Bayes classification algorithm** step by step — from raw CSV upload to full model evaluation — with visual explanations, mathematical walkthroughs, and zero installation required.

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

This project was built as a **CIA-1 Assignment** for the course *Introduction to Machine Learning* (BTech CSE AI/ML, 2nd Year).

The aim was to design a web-based learning tool that helps engineering students **understand, visualize, and experiment** with the Naive Bayes algorithm entirely from scratch — without needing to install Python, Jupyter, or any libraries.

The interface is inspired by **Google Colab's notebook style** — collapsible cells, step-by-step execution flow, and inline explanations alongside every computation.

---

## 🌐 Live Demo

>https://sneha-space.github.io/naive-bayes-app/
> Open `index.html` directly in any modern browser — no server, no backend, no installation needed.

```bash
# Just download and open
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5 + CSS3** | Structure and dark-theme UI |
| **Vanilla JavaScript** | All ML logic, state management, UI interactions |
| **Papa Parse 5.4** | CSV file parsing (CDN) |
| **Chart.js 4.4** | All data visualizations — histograms, bar charts, line charts, doughnuts (CDN) |
| **Google Fonts** | JetBrains Mono + IBM Plex Sans typography |

> No npm. No Node.js. No frameworks. No build step. Everything runs in a single `index.html` file.

---

## ✨ Features

- **Drag-and-drop CSV upload** with instant dataset preview
- **Full preprocessing pipeline** — missing values, encoding, scaling, feature selection
- **EDA visualizations** — class distribution, feature histograms, Pearson correlation heatmap
- **Step-by-step NB math** — prior, likelihood, independence assumption, posterior — all shown with real numbers from your data
- **Gaussian NB** with PDF curve overlays per class per feature
- **Multinomial NB** with Laplace smoothing and zero-frequency problem highlighting
- **Train/Test split** with adjustable slider (50–90%)
- **k-Fold Cross Validation** with fold-wise accuracy chart
- **Custom sample prediction** with full log-space walkthrough
- **Confusion matrix** + Precision / Recall / F1 per class + Macro average
- **Persistent help drawer** — Glossary, Why Each Step, Common Mistakes, Formula Sheet


---

## 🔢 Pipeline Stages

The app is structured as a **9-stage notebook pipeline** — each stage builds on the previous one:

| Stage | Name | What Happens |
|---|---|---|
| **1** | Dataset Input | Upload CSV, preview data, detect column types, select target column |
| **2** | Preprocessing | Handle nulls, encode categoricals, scale features, select features |
| **3** | EDA | Class distribution chart, feature histograms by class, correlation heatmap |
| **4** | NB Learning Module | Prior table, likelihood estimation, independence assumption, full posterior walkthrough for sample[0] |
| **5** | Training Configuration | Train/test split slider, k-fold CV toggle, Fisher-Yates shuffle, train the model |
| **6** | Model Visualization | Learned parameters table, Gaussian PDF curves / Multinomial bar charts |
| **7** | Prediction & Inference | Enter custom sample, see step-by-step log-space computation, get prediction with class probabilities |
| **8** | Evaluation Metrics | Confusion matrix, per-class TP/FP/FN/TN/P/R/F1, macro average, optional k-fold chart |
| **9** | Educational Summary | Recap of all four NB steps, next steps for research and GATE preparation |

---

## ▶️ How to Run

**Option 1 — Download and open directly**

```bash
git clone https://github.com/your-username/naive-bayes-learning-system.git
cd naive-bayes-learning-system
open index.html
```

1. Download or clone this repository
2. Open `index.html` in **Google Chrome** or **Firefox**
3. Upload any labeled CSV file
4. Work through the 9 stages top to bottom

**Option 2 — Host on GitHub Pages**

1. Push to a GitHub repository
2. Go to **Settings → Pages → Source: main branch / root**
3. Your app gets a public URL:
   ```
[(https://sneha-space.github.io/naive-bayes-app/)]
   ```

> **Requirements:** Any modern browser (Chrome recommended). No internet needed after the initial CDN load.

---

## 📁 Dataset Compatibility

The app works with **any labeled CSV dataset**. Recommended test datasets to get started:

| Dataset | Features | Classes | Source |
|---|---|---|---|
| **Iris** | 4 numeric | 3 species | [Kaggle](https://www.kaggle.com/datasets/uciml/iris) |
| **Play Tennis** | 4 categorical | Yes / No | ML textbooks |
| **Titanic** | Mixed | Survived / Not | [Kaggle](https://www.kaggle.com/c/titanic) |
| **Spam SMS** | Text (pre-vectorized) | Spam / Ham | [Kaggle](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) |
| **Wine Quality** | 11 numeric | Quality 3–8 | [UCI ML Repo](https://archive.ics.uci.edu/ml/datasets/wine+quality) |

**CSV Requirements:**
- Must have a header row
- One column must be the class/target label
- Supports both numeric and categorical features
- Missing values are handled automatically in Stage 2

---

## 🗂️ Project Structure

```
naive-bayes-learning-system/
│
├── index.html          # Complete application — all HTML, CSS, JS inline
└── README.md           # Project documentation
```

> The entire application is self-contained in a single `index.html` file (~1,600 lines). All external dependencies load from CDN.

---

## 🎓 Educational Design

This app was designed specifically for **engineering students learning ML for the first time**. Every decision prioritises understanding over black-box convenience:

**Mathematical transparency**
Every formula is shown with actual numbers substituted in — not just abstract symbols. You see `log P(setosa) = log(0.3333) = −1.0986`, not just `log P(C)`.

**Log-space computation**
The posterior walkthrough uses log-probabilities throughout, teaching students why multiplying many small probabilities causes numerical underflow and how log-space addition solves it.

**Laplace smoothing visualisation**
Zero-count cells in the Multinomial frequency table are highlighted in amber, showing exactly which values would have caused the zero-frequency problem and how adding 1 to the numerator fixes them.

**Before/After comparisons**
Every preprocessing step in Stage 2 shows the data state before and after the transformation, making the impact of each step concrete and measurable.

**Persistent help system**
The `?` button is always visible in the bottom-right corner. The help drawer contains a full glossary, stage-by-stage "Why this step?" explanations, a list of common student mistakes, and a formula reference card — accessible without leaving the current stage.

---

## 🚀 Future Improvements

| Improvement | Description |
|---|---|
| Bernoulli NB support | Handle binary feature datasets |
| Sample dataset gallery | One-click load for Iris, Titanic, Play Tennis |
| Animated computation | Animate the posterior calculation step by step |
| Comparison mode | Run Gaussian vs Multinomial side-by-side |
| Export model | Download learned parameters as JSON |
| Report export | Download full evaluation as PDF |
| Mobile layout | Improved responsiveness for tablet/phone |
| Light theme toggle | Accessibility option |

---

## 📚 References

- Mitchell, T. (1997). *Machine Learning*. McGraw-Hill. — Chapter 6: Bayesian Learning
- Rish, I. (2001). *An empirical study of the naive Bayes classifier*. IJCAI Workshop on Empirical Methods in AI.
- Scikit-learn — [Naive Bayes Documentation](https://scikit-learn.org/stable/modules/naive_bayes.html)
- StatQuest with Josh Starmer — [Naive Bayes, Clearly Explained](https://www.youtube.com/watch?v=O2L2Uv9pdDA)
- 3Blue1Brown — [Bayes Theorem](https://www.youtube.com/watch?v=HZGCoVF3YvM)
- NPTEL IIT Kharagpur — Introduction to Machine Learning (Prof. Sudeshna Sarkar)

---

## 👩‍💻 Author

**Sneha**
B.Tech CSE (AI & ML) — 2nd Year
*CIA-1 Assignment: Design and Development of an Interactive Web-Based Learning System for Naive Bayes Classification*

---

<div align="center">
  <sub>Built with vanilla JavaScript — no frameworks, no backend, no installation. Just open and learn.</sub>
</div>
