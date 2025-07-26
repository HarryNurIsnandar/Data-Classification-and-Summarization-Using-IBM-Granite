## 📌 Project Overview
This project leverages a large language model (LLM) — specifically IBM Granite-3.3-8B-Instruct — to predict the likelihood of hypertension in patients based on multiple lifestyle and medical factors. The system doesn't just give predictions, but also provides explanations for each case using natural language generation, which enhances interpretability for non-technical stakeholders.

Using a small sample from a structured dataset, each patient's record is passed as input to the LLM, prompting it to:

Predict whether the patient has hypertension (Yes/No)

Justify the prediction using available features like age, BMI, medication, exercise level, etc.

## 📂 Raw Dataset Link
Dataset used in this project is hosted on Google Drive:

📎 Hypertension Dataset (CSV)

https://www.kaggle.com/datasets/miadul/hypertension-risk-prediction-dataset/data

## 🔍 Insights & Findings
Based on experimental runs using the model:

The LLM can accurately infer correlations between hypertension and factors like age, family history, exercise level, and sleep duration.

When features are contradictory (e.g., normal BMI but high salt intake), the model still attempts to balance the reasoning, mimicking a medical decision-making process.

Output is explainable, with clear statements such as:

"Pasien memiliki riwayat hipertensi, tingkat stres yang tinggi, serta aktivitas fisik rendah — ketiganya merupakan indikator risiko hipertensi."

Demonstrated how generative AI can enhance interpretability of structured tabular data.

## 🤖 AI Support Explanation
This project integrates with the Replicate API to access IBM's Granite 3.3 8B Instruct model via langchain_community.llms.Replicate. Here's how it works:

Each row of the dataset (except the target column) is converted into a JSON input.

The JSON is wrapped in a prompt instructing the model to predict hypertension and explain the rationale.

The model’s response is printed for each patient, demonstrating its reasoning process.

The project uses the following advanced LLM parameters to optimize output:

top_k = 50, top_p = 0.95 for response diversity

repetition_penalty = 1.2 to avoid looping phrases

max_new_tokens = 300 to allow for rich explanation

This setup showcases how LLMs can be integrated with healthcare-related tabular data for explainable AI applications — even without retraining the model.

