# Robust In-Context Learning via Multi-Armed Bandit-Based Partition Selection

**Authors:** Varul Srivastava, Sankarshan Damle, Manisha Padala

**Paper:** [Link to Paper](https://github.com/vs666/RobustICL_MAB/blob/main/workshop_paper.pdf)

**Poster:**
![ICLR Workshop poster](https://github.com/vs666/RobustICL_MAB/blob/main/In_page-0001.jpg)
## 📌 Overview
In-context learning (ICL) enables Large Language Models (LLMs) to adapt to new tasks without parameter updates, relying solely on exemplar selection. However, noisy labels in real-world data partitions can significantly degrade ICL performance.

This paper introduces a **Multi-Armed Bandit (MAB)-based partition selection** strategy using the **Upper Confidence Bound (UCB)** algorithm. By treating each partition as an arm in a bandit problem, the model iteratively selects the most reliable partitions, improving the robustness of ICL against noisy data.

📄 **Accepted at:** DATA-FM Workshop @ ICLR 2025

---

## 🚀 Key Contributions
- **Problem Formulation:** We model **ICL partition selection** as a **Multi-Armed Bandit (MAB) problem**, where each evaluation sample serves as a pull.
- **UCB-Based Strategy:** We employ the **Upper Confidence Bound (UCB)** algorithm to dynamically refine partition selection.
- **Improved ICL Robustness:** Our approach restores ICL accuracy to near clean-data performance levels.
- **Extensive Benchmarking:** We validate our method on **AG-News, MMLU, MMLU-Pro, and synthetic datasets** using **LLaMA-3 and Phi-3.5 models**.

---

## 🛠️ Methodology
### 1️⃣ In-Context Learning (ICL) with Noisy Data
- ICL adapts to new tasks using **exemplar demonstrations** without fine-tuning.
- Noisy or adversarial partitions degrade ICL performance.
- We propose selecting **high-quality partitions dynamically**.

### 2️⃣ Multi-Armed Bandit (MAB) Formulation
- **Arms:** Data partitions
- **Pull:** Selecting a partition for exemplar sampling
- **Reward:** Correct prediction by LLM
- **Objective:** Minimize cumulative regret by selecting optimal partitions

### 3️⃣ UCB-Based Partition Selection
- Uses the **Upper Confidence Bound (UCB)** algorithm:
  \[ \text{UCB}_i = \hat{r}_i + c \sqrt{\frac{\ln(t)}{n_i}} \]
- Prioritizes partitions with **higher reliability** over time.
- Recovers performance comparable to **clean-data settings**.

🚀 **Algorithm Implementation:** [Github Link](https://github.com/vs666/RobustICL_MAB)

---

## 📊 Experimental Setup
### 📌 Datasets
| Dataset | Description |
|---------|-------------|
| **AG-News** | 4-class text classification benchmark |
| **MMLU** | Massive Multitask Language Understanding benchmark |
| **MMLU-Pro** | More challenging MMLU variant |
| **Synthetic** | Custom classification dataset |

### 🏗️ Models
- **LLaMA-3.2-3B, LLaMA-3.1-8B, LLaMA-3.1-70B**
- **Phi-3.5-mini**

### 🎯 Evaluation Metrics
- **Accuracy** on ICL tasks with varying noise levels
- **Impact of UCB selection vs. uniform/random selection**

---

## 📈 Results
### 📌 Performance of LLaMA-3.2-3B on Different Datasets
| Dataset | Zero-Shot | Worst-Case | No-Noise | Uniform | UCB-d1 | UCB-d2 |
|---------|-----------|------------|----------|---------|--------|--------|
| AG-News | 58.38±1.9 | 61.68±3.8  | 74.25±1.39 | 64.67±3.86 | 73.45±1.64 | 69.93±1.82 |
| MMLU | 34.13±2.22 | 45.84±0.11 | 49.23±1.26 | 46.31±0.53 | 48.77±1.17 | 48.70±0.34 |
| MMLU-Pro | 19.36±0.72 | 27.41±1.02 | 29.21±1.02 | 29.67±0.5 | 30.27±0.41 | 26.95±0.91 |
| Synthetic | 20.95±1.69 | 25.75±0.28 | 39.02±2.11 | 29.84±2.40 | 39.22±1.83 | 31.74±2.26 |

### 📌 Performance Comparison Across Model Sizes on AG-News
| Model | Zero-Shot | Worst-Case | No-Noise | Uniform | UCB-d1 | UCB-d2 |
|--------|-----------|------------|----------|---------|--------|--------|
| phi-3.5-mini | 47.70 | 48.70 | 69.86 | 53.69 | 69.36 | 61.88 |
| LLaMA-3.2-3B | 58.38 | 61.68 | 74.25 | 64.67 | 73.45 | 69.93 |
| LLaMA-3.1-8B | 80.08 | 63.38 | 84.11 | 75.78 | 83.92 | 81.31 |
| LLaMA-3.1-70B | 86.69 | 86.65 | 87.76 | 87.76 | 87.55 | 87.37 |

---

## 📜 Citation
If you use this work, please cite:
```bibtex
@inproceedings{srivastava2025robustICL,
  title={Robust In-Context Learning via Multi-Armed Bandit-Based Partition Selection},
  author={Varul Srivastava, Sankarshan Damle, Manisha Padala},
  booktitle={2nd Workshop on Navigating and Addressing Data Problems for Foundation Models at ICLR},
  year={2025}
}
```

---

## 🛠️ Code & Reproducibility
📂 **Coming Soon**: [Github Link](https://github.com/vs666/RobustICL_MAB)

---

## 📞 Contact
For questions, feel free to open an issue or contact the authors.

📧 **Email:** varul [dot] srivastava [at] gmail.com 

---

⚡ *Star this repo if you find it useful!* ⭐

