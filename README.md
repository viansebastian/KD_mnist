# 🧠 Knowledge Distillation on MNIST

This project is a self-learning experiment exploring **Knowledge Distillation (KD)** — a technique where a smaller *student network* learns to mimic a larger *teacher network* while retaining strong performance.

---

## 🎯 Objective

To demonstrate how **model compression** through knowledge distillation can significantly **reduce model size and inference time** while maintaining (or even improving) predictive performance.

---

## ⚙️ Experimental Setup

| Model | Size | Parameters | Avg. Inference Time (ms) | Avg Accuracy|
|:------|------:|------------:|-------------------------:|------:|
| 🧑‍🏫 Teacher | 0.85 MB | 70,851 | 42.76 | 0.99 |
| 👩‍🎓 Student | 0.17 MB | 11,875 | 40.83 | 0.99 |

> Both models were trained on the **MNIST** dataset using a standard KD loss that combines soft and hard labels.

---

## 📈 Performance Comparison

### Teacher Model
| Class | Precision | Recall | F1-Score | Support |
|:------|-----------:|--------:|----------:|--------:|
| 0 | 0.99 | 1.00 | 0.99 | 588 |
| 1 | 0.99 | 1.00 | 0.99 | 681 |
| 2 | 1.00 | 0.97 | 0.98 | 619 |

**Accuracy:** 0.99  
**Macro Avg:** Precision = 0.99 | Recall = 0.99 | F1 = 0.99  

---

### Student Model
| Class | Precision | Recall | F1-Score | Support |
|:------|-----------:|--------:|----------:|--------:|
| 0 | 1.00 | 0.98 | 0.99 | 588 |
| 1 | 1.00 | 1.00 | 1.00 | 681 |
| 2 | 0.98 | 1.00 | 0.99 | 619 |

**Accuracy:** 0.99  
**Macro Avg:** Precision = 0.99 | Recall = 0.99 | F1 = 0.99  

---

## 🖼️ Visualizations

<div align="center"> <img src="images\teacher-student-acc.png?raw=true" alt="Train Curves" width="750"></div>

---

## 🔍 Insights

Despite having **6× fewer parameters**, the student model:

- Achieved **identical accuracy (0.99)** to the teacher.  
- Improved **F1-score** for **classes 1 and 2**.  
- Increased **recall** for **class 0**, even with fewer parameters.  
- Reduced **inference time** (37.84 → 35.72 ms).

> 🧩 This suggests that the distilled model not only compressed effectively but also generalized better for certain classes — a good sign of successful KD.


