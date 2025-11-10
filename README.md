---

# 🦵 Multi-Class Classification and Detection of Knee Osteoarthritis from X-Rays

## 📘 Abstract

Knee Osteoarthritis (KOA) is a **degenerative joint disease** that reduces mobility and quality of life.
This project presents a **multi-class classification system** using **deep learning** to automate the **detection and grading of KOA** from X-ray images based on the **Kellgren–Lawrence (KL) scale**.
Using **transfer learning** and **fine-tuned CNN models** (HRNet and ConvNeXt), the system performs both **single-level** and **multi-level classification**.
The proposed **hierarchical approach** achieved an overall accuracy of **73.94%** for abnormal severity grading and **80.62%** for binary classification (normal vs abnormal), outperforming conventional CNN architectures.

---

## 🎯 Objectives

* Detect and classify **KOA severity** automatically from X-ray images.
* Improve early diagnosis by distinguishing between subtle OA grades.
* Employ **multi-level deep learning** to boost accuracy and interpretability.

---

## 🧠 Key Concepts

| Aspect             | Description                                                           |
| ------------------ | --------------------------------------------------------------------- |
| **Disease Focus**  | Knee Osteoarthritis (KOA)                                             |
| **Dataset**        | *Knee Osteoarthritis Severity Grading Dataset (Mendeley)*             |
| **Grading System** | Kellgren–Lawrence (KL) Grades 0–4                                     |
| **Models Used**    | HRNet, ConvNeXt, VGG16, ResNet50, EfficientNetB0                      |
| **Techniques**     | Transfer Learning, Multi-Level Classification, CNN Feature Extraction |
| **Metrics**        | Accuracy, Precision, Recall, F1-Score                                 |

---

## 🧩 Methodology

### 1️⃣ Single-Level Classification

* Classifies X-rays directly into **five KL grades (0–4)**.
* Utilizes CNN models pre-trained on ImageNet and fine-tuned for KOA dataset.
* **ConvNeXt** achieved the highest performance:

  > Accuracy: 71.26%, Precision: 71.56%, F1-Score: 69.38%

### 2️⃣ Multi-Level (Hierarchical) Classification

* Step 1: **Binary Model** — separates Normal (KL-0) vs Abnormal (KL 1–4)
* Step 2: **Abnormal Model** — classifies abnormal images into Grades 1–4
* **Results**:

  * Binary (ConvNeXt): Accuracy 80.62%, F1-Score 84.26%
  * Abnormal (ConvNeXt): Accuracy 73.94%, F1-Score 74.22%

### 🧬 ConvNeXt Architecture

* Combines **ResNet-style residual blocks** with **depthwise convolutions**.
* Uses **Layer Normalization** and **GELU activation** for training stability.
* Achieves multi-scale feature extraction for superior OA detection.

---

## 🧮 Dataset Overview

| KL Grade | Description | Train | Test | Validation | Total |
| -------- | ----------- | ----- | ---- | ---------- | ----- |
| 0        | Normal      | 2286  | 639  | 328        | 3253  |
| 1        | Doubtful OA | 1046  | 296  | 153        | 1495  |
| 2        | Minimal OA  | 1516  | 447  | 212        | 2175  |
| 3        | Moderate OA | 757   | 223  | 106        | 1086  |
| 4        | Severe OA   | 173   | 51   | 27         | 251   |

---

## 📊 Results Summary

| Model                   | Task         | Accuracy   | Precision  | F1-Score   |
| ----------------------- | ------------ | ---------- | ---------- | ---------- |
| **VGG16**               | Single-Level | 63.77%     | 61.83%     | 60.64%     |
| **ResNet50**            | Single-Level | 59.36%     | 63.59%     | 60.92%     |
| **EfficientNetB0**      | Single-Level | 62.86%     | 62.49%     | 61.21%     |
| **HRNet**               | Single-Level | 64.73%     | 65.05%     | 64.49%     |
| **ConvNeXt**            | Single-Level | **71.26%** | **71.56%** | **69.38%** |
| **ConvNeXt (Binary)**   | Multi-Level  | **80.62%** | 80.53%     | **84.26%** |
| **ConvNeXt (Abnormal)** | Multi-Level  | **73.94%** | 74.29%     | **74.22%** |

> 💡 The hierarchical framework achieved better sensitivity for early detection —
> especially improving Grade 1 recall from 16.55% → **66.55%**

---

## 🧭 Workflow Overview

1. **Data Loading** → X-ray preprocessing, resizing, augmentation
2. **Model Selection** → ConvNeXt & HRNet for feature extraction
3. **Training (Level 1 & 2)** → Binary + Multi-class
4. **Evaluation** → Metrics: Accuracy, F1-Score, Confusion Matrix
5. **Visualization** → Grad-CAM for heatmap analysis

---

## 🧠 Insights

* Multi-level learning **balances sensitivity & specificity**, outperforming single-level CNNs.
* The approach captures **fine-grained abnormalities**, improving early-stage OA detection.
* HRNet and ConvNeXt models provide **robust spatial feature learning**.

---

## 🚀 Future Enhancements

* Integration with **Streamlit / Flask dashboard** for radiologist interaction.
* Apply **ensemble learning** for stronger grade prediction.
* Incorporate **Grad-CAM explainability** in final deployment.

---

## 📚 References

The methodology and metrics were inspired and validated through research papers including:

* Farooq *et al.*, *DC-AAE for KL-grade Classification*, 2023
* Wang *et al.*, *Learning from High-Confidence Samples*, IEEE, 2022
* Jain *et al.*, *OsteoHRNet*, 2024
* Chen *et al.*, *Fully Automatic KOA Grading*, 2019
* Lee *et al.*, *Plug-in Deep Learning Modules for KOA*, 2024

---

## 👨‍💻 Author

**Santhosh Dulam**
📍 Coimbatore, India
🎓 B.Tech – Amrita Vishwa Vidyapeetham
📧 [santhosh.dulam45@gmail.com](mailto:santhosh.dulam45@gmail.com)
🔗 [LinkedIn](https://linkedin.com/in/santhosh-dulam-94b8b9242)

---

## 🪪 License

This project is open-source under the **MIT License**.
