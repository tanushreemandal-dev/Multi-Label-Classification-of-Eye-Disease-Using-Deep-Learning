# 👁️ Multi-Label Classification of Eye Disease Using Deep Learning

> Diagnose multiple retinal diseases from a single fundus image — and actually trust the result, even on data the model has never seen before.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red)
![Model](https://img.shields.io/badge/Model-Swin--Tiny-6A5ACD)
![Status](https://img.shields.io/badge/Status-Published%20%40%20IEEE-brightgreen)

📄 Published in: 2026 9th International Conference on Electronics, Materials Engineering & Nano-Technology (IEMENTech) — [Read the paper](https://ieeexplore.ieee.org/document/11434265) 

---

## 📌 Overview

Most retinal disease classifiers are trained and tested on a single dataset — and quietly fall apart the moment they see an image from a different hospital, camera, or population. This is called **domain shift**, and it's one of the biggest blockers between a promising research model and a real clinical tool.

This project tackles that problem head-on. Instead of relying on one dataset, we **fuse two independent public datasets** at the data level, rigorously **benchmark 11 different architectures** to find the true best performer, and then put that model through the hardest test of all: diagnosing a **completely unseen external dataset**, without any retraining.

---

## ✨ Features

- 🧬 **Generalized dataset** — ODIR-5K and RFMiD are merged into one unified training set, exposing the model to diverse cameras, populations, and disease presentations
- 🏆 **11-architecture comparative study** — CNNs, efficient nets, and vision transformers are all benchmarked under identical conditions, so the winning model is chosen on evidence, not convention
- 🥇 **Swin-Tiny selected as top performer** — the strongest discriminative ability across disease classes, out of all 11 candidates
- 🔄 **Zero-retraining domain adaptation** — a lightweight threshold-adaptation technique recalibrates the model for a brand-new dataset without touching a single model weight
- 🌍 **External validation on APTOS 2019** — a dataset never seen during training, used purely to prove real-world generalization
- 🔍 **Grad-CAM integration** — every prediction comes with a heatmap showing exactly which part of the retina influenced the diagnosis

---

## 🛠️ How It Works

1. **Data-Level Fusion** — ODIR-5K and RFMiD are merged into a single dataset with a patient-aware split, so no patient's images leak across train/val/test.
2. **Data-Driven Problem Enhancement & Preprocessing** — a class-frequency analysis narrows the label set down to the diseases with enough real support to learn from, followed by resizing, normalization, and augmentation.
3. **Comparative Training** — 11 architectures are trained and evaluated under identical data, loss, and optimizer settings; each is scored on accuracy, precision, recall, F1, and AUROC per disease class.
4. **Explainable AI (Grad-CAM)** — the winning model, Swin-Tiny, gets a Grad-CAM heatmap generated for every predicted disease, overlaying the "why" on top of the original image.
5. **Cross-Dataset Validation** — Swin-Tiny is evaluated on APTOS 2019 using per-class threshold adaptation instead of retraining, to measure genuine generalization to unseen data.

---

## 🧬 Datasets Used

| Dataset | Role |
|---|---|
| **ODIR-5K** | Training (fused) |
| **RFMiD** | Training (fused) |
| **APTOS 2019** | External validation only — never used in training |

---

## 💡 Why This Matters

- A model that only works on its own training data isn't clinically useful — **this one is explicitly tested on data it has never seen**
- Picking an architecture "because it's popular" isn't science — **this one was chosen from an 11-way empirical shootout**
- A black-box prediction isn't trustworthy in healthcare — **every prediction here comes with a visual explanation**
- Retraining for every new hospital/camera isn't practical — **this framework adapts with a simple threshold tweak**

---

## 🚀 Possible Extensions

- Extend the comparative study to newer transformer/hybrid backbones
- Add support for additional disease classes as more labeled data becomes available
- Package the trained model behind a simple web/clinical demo interface
- Explore full fine-tuning-based domain adaptation as a comparison to threshold adaptation

---

## 📄 Citation

If you use this work, please cite the published paper:

> *[Tanushree Mandal; Monisha Kar; Susovan Jana; Pulak Baral], "[Multi-Label Classification of Eye Disease Using Deep Learning]," [9th International Conference on Electronics, Materials Engineering & Nano-Technology (IEMENTech)], [2026].*
> Paper link: [https://ieeexplore.ieee.org/document/11434265]

---

## 🤝 Connect

Have questions, feedback, or ideas for collaboration? Feel free to reach out or open an issue on this repo!

- 💼 LinkedIn: [Tanushree Mandal](https://linkedin.com/in/tanushree-mandal-aba24b286)
- 📧 Email: [tanushreemandal235@gmail.com](tanushreemandal235@gmail.com)
