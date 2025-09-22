<h1 align="center" style="color:#2E5984;">
🏆 BigQuery ML Competition – Kaggle Notebook
</h1>

<p align="center">
  <em>Exploring, modeling, and deploying with <strong>BigQuery ML</strong> in a Kaggle competition setting</em>
</p>

---

## 📖 Overview
This repository contains my work for the **Kaggle BigQuery Machine Learning competition**.  
The main notebook [`notebook.ipynb`](Civic_Proof_Notebook.ipynb) demonstrates:

- 🔍 Exploratory analysis  
- 🛠️ Feature engineering  
- 🤖 Model training & evaluation with **BigQuery ML**

---

## 📂 Dataset
- Hosted directly on **Google BigQuery**.  
- Accessed through the Kaggle competition environment.  
- Queries are executed natively in **SQL with ML extensions**.

---

## 🔬 Methodology
1. 📊 **Exploration & Cleaning** — inspect data quality and distribution.  
2. 🧩 **Feature Engineering** — SQL transformations to create meaningful signals.  
3. 🤖 **Model Training** — leveraging `ML.LINEAR_REG`, `ML.BOOSTED_TREE_CLASSIFIER`, and more.  
4. 📈 **Evaluation** — standard metrics such as AUC, accuracy, and log loss.  
5. 🚀 **Submission** — predictions generated via BigQuery and submitted on Kaggle.

---

## ✅ Results
- Baseline model established in the initial notebook.  
- Iterative improvements through **feature selection** & **hyperparameter tuning**.  
- Final submission derived from optimized BigQuery ML predictions.

---

## ⚙️ Requirements
- Python **3.x**  
- Dependencies listed in [`requirements.txt`](requirements.txt)  

---

## 🚀 Usage
Clone the repository and navigate inside:
```bash
git clone https://github.com/<your-username>/bigquery-ml-competition.git
cd bigquery-ml-competition
