## 🏥 Data Anonymization Case Study — Hospital Patient Records

### 🔍 Overview

This project demonstrates how standard **data anonymization techniques** can be applied to protect sensitive information in a healthcare dataset.
The main goal is to **reduce the risk of re-identification** while maintaining data utility for analysis and research.

Techniques like **k-Anonymity**, **l-Diversity**, and **Tokenization** were implemented and compared using Python in a Jupyter Notebook (`main.ipynb`).

---

### 🎯 Objectives

* To anonymize a hospital patient dataset containing personal identifiers.
* To apply and compare anonymization methods such as k-Anonymity, l-Diversity, and Tokenization.
* To analyze privacy–utility trade-offs using metrics like **Information Loss**, **Re-identification Risk**, and **Records Retained**.
* To generate visual and tabular summaries of anonymization performance.

---

### 🧠 Key Concepts

* **k-Anonymity** – Ensures that each individual cannot be distinguished from at least *k–1* others.
* **l-Diversity** – Ensures diversity in sensitive attributes within each anonymized group.
* **Tokenization** – Replaces real values with random tokens (can be reversible if needed).
* **Encryption / Masking** – Protects data by transforming or hiding original information.

---

### 🧩 Project Structure

```
📁 Data-Anonymization-Case-Study/
│
├── main.ipynb               # Main Jupyter notebook with code, analysis, and outputs
│
├── 📁 outputs/               # Folder containing generated CSV results
│   ├── anonymised_metrics.csv
│   ├── before_after_metrics.csv
│   ├── kl_metrics.csv
│   └── method_comparison.csv
│
├── 📁 graphs/                # Folder containing generated plots
│   ├── info_loss_vs_k.png
│   ├── reid_risk_vs_k.png
│   └── records_retained_vs_k.png
│
└── README.md
```

---

### 📊 Description of Output Files

| File Name                    | Description                                                                                                                              |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **method_comparison.csv**    | Compares Tokenization, Encryption, and Masking methods based on reversibility, uniqueness, and length of transformed data.               |
| **kl_metrics.csv**           | Records anonymization metrics for various *k* and *l* values — including re-identification risk, information loss, and records retained. |
| **before_after_metrics.csv** | Compares dataset statistics before and after anonymization (records, risk, info loss, diversity retention, etc.).                        |
| **anonymised_metrics.csv**   | Contains final metrics of the chosen anonymization setup (*k=3*, *l=2*), showing optimal privacy–utility balance.                        |

---

### 📈 Graphs Generated

The analysis includes three key visualizations to show the impact of *k* and *l* on data privacy and utility:

1. **Information Loss vs k**

   * Shows how information loss increases as *k* increases.
   * Higher privacy → higher information loss.

2. **Re-identification Risk vs k**

   * Displays how re-identification risk decreases with larger *k* values.
   * Follows the relation *risk = 1/k*.

3. **Records Retained vs k**

   * Tracks the number of records retained after anonymization.
   * A small reduction occurs with higher *k* or *l* due to generalization/suppression.

---

### 🧮 Results Summary

| Metric                  | Before | After |
| ----------------------- | ------ | ----- |
| Total Records           | 55500  | 55427 |
| Unique QI Combinations  | 539    | 491   |
| Unique Sensitive Values | 6      | 6     |
| Re-identification Risk  | 1.00   | 0.33  |
| Information Loss (%)    | 0.0    | 8.91  |
| Record Retention (%)    | 100    | 99.87 |
| Diversity Retention (%) | 100    | 100   |

✅ **Best configuration:** *k = 3, l = 2*
✅ **Re-identification Risk:** 0.33
✅ **Information Loss:** 8.91%
✅ **Records Retained:** 55427

---

### 🔐 Comparison of Anonymization Methods

| Method       | Unique Ratio | Avg. Length | Reversible    |
| ------------ | ------------ | ----------- | ------------- |
| Tokenization | 1.000        | 8.0         | Yes (vault) |
| Encryption   | 1.000        | 10.0        | No          |
| Masking      | 0.005        | 36.0        | No          |

➡️ **Observation:**

* Tokenization maintains the best balance between reversibility and data utility.
* Masking leads to the most distortion, making data nearly unusable for analysis.
* Encryption provides strong privacy but is irreversible.

---

### 💡 Key Learnings

* Increasing *k* improves privacy but slightly reduces data quality.
* Maintaining diversity (*l*) ensures that sensitive data can’t be inferred even in the same group.
* Tokenization provides practical anonymization with easy reversibility when needed.

---

### 🚀 Scope for Improvement

* Apply to larger, real-world healthcare datasets.
* Automate the selection of optimal *k* and *l* values.
* Implement **Differential Privacy** for stronger guarantees.
* Create a simple **web dashboard or API** for anonymization.
* Add interactive visualizations using Plotly or Dash.

---

### 🧰 Technologies Used

* **Python 3.x**
* **Libraries:** pandas, numpy, matplotlib, sklearn
* **Jupyter Notebook** for implementation and analysis

---

### 📜 License

This project is for **educational and academic purposes** only.
The dataset used in this project is synthetic and does not contain any real patient information.

---

### 👤 Author

**Yash Agrawal**
Undergraduate Student – Vellore Institute of Technology, Vellore
Data Privacy & Security Case Study
