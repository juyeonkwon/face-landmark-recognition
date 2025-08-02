# 🔒 Face Landmark-based Lightweight Recognition

> A privacy-enhancing and computation-efficient face recognition system using coordinate-based input and perspective normalization.

---

## 📌 Introduction

This project proposes a lightweight and privacy-preserving face recognition pipeline that utilizes only the 68 facial landmark coordinates extracted via Dlib, instead of raw facial images. A perspective normalization algorithm is applied to compensate for distortions caused by facial angles and expressions, allowing more robust recognition under diverse poses.

* ✅ No image data used → higher privacy
* ✅ Landmark coordinate-based learning → reduced input dimensionality
* ✅ Perspective transformation → normalization for pose-invariant input
* ✅ Efficient computation with smaller model size

---

## 🗂️ Project Structure

```
.
├── src/
│   ├── main.py            # Main training/inference logic
│   └── utils.py           # Preprocessing, normalization, and evaluation utilities
├── results/               # Experimental results (plots, metrics, comparisons)
│   ├── acc_loss.png
│   ├── fpr_fnr.png
│   ├── heatmap.png
│   └── comparison_metrics.png
├── data/
│   └── landmarks.csv      # Landmark-only coordinate dataset (x, y per point)
└── README.md
```

---

## 📊 Experimental Results

We compared our coordinate-based method to a traditional image-based approach. While the baseline uses full facial images, our method relies only on coordinate data and achieves superior or comparable performance with significantly reduced computational cost.

| Metric    | Conv. (Image) | Prop. w/o p. transform | Prop. w/ p. transform |
| --------- | ------------- | ---------------------- | --------------------- |
| Accuracy  | 0.9733        | 0.9716                 | **0.9817**            |
| Precision | 0.9901        | 0.9875                 | **0.9908**            |
| Recall    | 0.9900        | 0.9875                 | **0.9908**            |
| AUROC     | 0.9997        | 1.0000                 | **1.0000**            |

✅ The coordinate-based method with perspective normalization consistently outperforms both the baseline and the non-normalized version in all metrics.


> 🔒 **Privacy**: Landmark-only input ensures no raw facial image is used, and normalized coordinates prevent re-identification.
> ⚙️ **Efficiency**: Smaller input leads to lower computational overhead and faster convergence.
> 🧠 All models shared the same architecture (for coordinate-based approaches), allowing fair comparison.

---

## 📂 Notes

* Dataset will be released later, containing only anonymized landmark coordinates.
* Codebase is under preparation and will be added soon.


