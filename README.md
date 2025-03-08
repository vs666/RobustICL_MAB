# Robust In-Context Learning via Multi-Armed Bandit-Based Partition Selection

**Authors:** Varul Srivastava, Sankarshan Damle, Manisha Padala

**Paper:** [Link to Paper](https://github.com/vs666/RobustICL_MAB/blob/main/workshop_paper.pdf)

## 📌 Overview
In-context learning (ICL) enables Large Language Models (LLMs) to adapt to new tasks without parameter updates, relying solely on exemplar selection. However, noisy labels in real-world data partitions can significantly degrade ICL performance.

This paper introduces a **Multi-Armed Bandit (MAB)-based partition selection** strategy using the **Upper Confidence Bound (UCB)** algorithm. By treating each partition as an arm in a bandit problem, the model iteratively selects the most reliable partitions, improving the robustness of ICL against noisy data.

📄 **Accepted at:** DATA-FM Workshop @ ICLR 2025 (Under Review)

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

🚀 **Algorithm Implementation:** [Provide GitHub repo link]

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

🖼 **Add performance tables & plots here**

---

## 📈 Results
- **Noise Hurts ICL:** Performance drops significantly when labels are corrupted.
- **UCB-Based Selection Recovers Performance:** Near clean-data accuracy is achieved using our method.
- **Larger Models Are More Robust:** Bigger LLMs generalize better against noise.

📊 **Add experimental results & comparison charts here**

---

## 🔮 Future Work
- Extend to **adversarially corrupted** partitions.
- Explore **Combinatorial Bandits** for non-IID data distributions.
- Apply method to **real-world settings** like healthcare or finance.

---

## 📜 Citation
If you use this work, please cite:
```bibtex
@inproceedings{srivastava2025robustICL,
  title={Robust In-Context Learning via Multi-Armed Bandit-Based Partition Selection},
  author={Varul Srivastava, Sankarshan Damle, Manisha Padala},
  booktitle={DATA-FM Workshop @ ICLR 2025},
  year={2025}
}
```

---

## 🛠️ Code & Reproducibility
📂 **Coming Soon**: [Provide GitHub repo link]

---

## 📞 Contact
For questions, feel free to open an issue or contact the authors.

📧 **Email:** [Add contact email]

💬 **Discussion:** [Add link to discussion thread]

---

⚡ *Star this repo if you find it useful!* ⭐

