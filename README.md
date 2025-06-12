# 🧠 Interpreting Biomedical VLMs on High-Imbalance Out-of-Distributions  
## An Insight into BiomedCLIP on Radiology

![BiomedCLIP](https://img.shields.io/badge/BiomedCLIP-Vision--Language--Model-blueviolet)  
![IU-Xray](https://img.shields.io/badge/Dataset-IU--Xray-lightgrey)  
![Status](https://img.shields.io/badge/Status-Research--In--Progress-yellow)

---

## 📌 Abstract

This repository accompanies the study **"Interpreting Biomedical VLMs on High-Imbalance Out-of-Distributions: An Insight into BiomedCLIP on Radiology"**, where we evaluate the performance and interpretability of **BiomedCLIP**, a vision-language model trained on biomedical data.

We pursue two main research objectives:
1. **Explore the embedding space** of BiomedCLIP to analyze meaningful class separations.
2. **Quantify limitations** of the model when applied to a highly imbalanced, out-of-distribution (OOD), multi-label medical dataset — **IU-Xray**.

We evaluate the model in three experimental settings:
- **Zero-shot inference**
- **Full fine-tuning**
- **Linear probing**

Our findings show that:
- In **zero-shot**, the model over-predicts all labels, leading to poor precision and weak class separability.
- **Full fine-tuning** improves discrimination between diseases.
- **Linear probing** enables detection of overlapping disease features.

Interpretability is enhanced through **Grad-CAM** visualizations, which are validated against **15 radiologist annotations**. These results call for **careful adaptation** of general VLMs to the specific characteristics of real-world medical datasets.

---

## 🧪 Experiments & Dataset

- **Dataset**: [IU-Xray](https://openi.nlm.nih.gov/)
  - Multi-label
  - High class imbalance
  - Small-scale
- **Model**: [BiomedCLIP](https://github.com/microsoft/BiomedCLIP)
- **Evaluation Protocols**:
  - Zero-shot
  - Linear probing (frozen encoder)
  - Full fine-tuning (unfrozen encoder)

---

## 📊 Results Summary

| Setting       | Precision | Recall | F1-Score | Notes                         |
|---------------|-----------|--------|----------|-------------------------------|
| Zero-shot     | ↓ Low     | ↑ High | ↓ Poor   | Over-predicts all labels      |
| Linear Probe  | → Medium  | → Medium | → Medium | Overlapping feature capture   |
| Fine-tuning   | ↑ High    | ↑ High | ↑ Best   | Strong disease separation     |

Grad-CAM results reveal differences in attention localization across the three modes, further aiding in interpretability.

---

## 📷 Visualization Examples

- ✅ Visual heatmaps using **Grad-CAM**
- 📌 Layer-wise attention comparisons
- 🔍 Side-by-side with radiologist annotations

---

## 📁 Repository Structure

```bash
📦 Interpreting-BiomedCLIP/
├── data/                    # IU-Xray dataset setup
├── models/                  # BiomedCLIP loading & config
├── experiments/
│   ├── zero_shot/
│   ├── linear_probe/
│   └── fine_tune/
├── visualizations/         # Grad-CAM outputs and scripts
├── notebooks/              # Jupyter notebooks for analysis
├── requirements.txt
└── README.md
```

---

## 🛠️ Setup

```bash
# Clone the repo
git clone https://github.com/yourusername/Interpreting-BiomedCLIP.git
cd Interpreting-BiomedCLIP

# Install dependencies
pip install -r requirements.txt
```

---

## 📢 Citation

If you use this work or the codebase, please cite:

```bibtex
@misc{yourbib2025,
  title={Interpreting Biomedical VLMs on High-Imbalance Out-of-Distributions: An Insight into BiomedCLIP on Radiology},
  author={Your Name et al.},
  year={2025},
  note={Work in progress},
}
```

---

## 👩‍⚕️ Why This Matters

This work bridges **computer science** and **clinical relevance** by:
- Assessing the real-world **limitations of zero-shot VLMs** on small, imbalanced datasets.
- Stressing the **importance of interpretability** for deployment in healthcare.
- Offering insights into how models can mislead without explicit adaptation.

---

## 📬 Contact

Have questions or feedback? Reach out to: **your.email@domain.com**
