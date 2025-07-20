# Employee_Salary_Prediction_Using_Classification_Algo
A machine learning project to predict whether an employee earns more than $50K annually using demographic and job-related features. Includes data preprocessing, model training, and a Streamlit web app for real-time salary classification.
# 💼 Employee Salary Classification Web Application

This repository contains a machine learning project that predicts whether an employee earns **more than 50K (>50K)** or **less than or equal to 50K (<=50K)** based on demographic and work-related attributes. The model is integrated with a user-friendly **Streamlit web application** for both single and batch predictions.

---

## 📌 Table of Contents

1. [Project Overview](#1-project-overview)  
2. [Dataset](#2-dataset)  
3. [Data Preprocessing](#3-data-preprocessing)  
4. [Model Training and Evaluation](#4-model-training-and-evaluation)  
5. [Web Application (Streamlit)](#5-web-application-streamlit)  
6. [How to Run the Application](#6-how-to-run-the-application)  
7. [Future Improvements](#7-future-improvements)  
8. [Tech Stack](#8-tech-stack)  
9. [Author](#9-author)

---

## 1️⃣ Project Overview

This project is part of a **machine learning internship** and was created with guidance from **Internet Ambulation**. It demonstrates:

- Supervised classification using real-world data
- End-to-end machine learning pipeline (data preprocessing ➝ model training ➝ evaluation)
- Model deployment using **Streamlit**

---

## 2️⃣ Dataset

- 📂 **Dataset Name**: `adult.csv`
- 📊 **Total Records**: 48,842 rows × 15 columns
- 🎯 **Target Column**: `income` (`>50K` or `<=50K`)

**Key Features**:
- `age`, `workclass`, `education`, `educational-num`, `marital-status`, `occupation`, `relationship`, `race`, `gender`, `capital-gain`, `capital-loss`, `hours-per-week`, `native-country`

---

## 3️⃣ Data Preprocessing

- ✅ Replaced missing values marked as `'?'` in `workclass` and `occupation` with `'Others'`
- 🚫 Removed rows where `workclass` is `'Without-pay'` or `'Never-worked'`
- 📉 Removed outliers from:
  - `age` (kept between 17 and 75)
  - `educational-num` (kept between 5 and 16)
- 🧹 Dropped `education` column (duplicate of `educational-num`)
- 🔢 Applied **Label Encoding** to categorical columns:
  - `workclass`, `marital-status`, `occupation`, `relationship`, `race`, `gender`, `native-country`
- 📐 Final cleaned data shape: **46,720 rows × 14 columns**

---

## 4️⃣ Model Training and Evaluation

- 🔀 **Train-Test Split**: 80% train / 20% test (`random_state=42`)
- 🧠 **Algorithms Used**:
  - Logistic Regression
  - Random Forest
  - K-Nearest Neighbors (KNN)
  - Support Vector Machine (SVC)
  - Gradient Boosting Classifier

**Model Performance (Accuracy Score)**:
| Model               | Accuracy   |
|--------------------|------------|
| Logistic Regression| 81.49%     |
| Random Forest      | **85.08%** |
| KNN                | 82.45%     |

✅ **Best Model**: Random Forest Classifier  
💾 Saved as: `best_model.pkl` using `joblib`

---

## 5️⃣ Web Application (Streamlit)

An interactive web app built using **Streamlit** for real-time salary predictions.

### 🔹 Features:
- 📥 Single employee prediction via sidebar form
- 📁 Batch predictions by uploading a CSV
- 📊 Real-time prediction display and downloadable output

### 🔹 Important Note:
- The app must use features consistent with the model (`educational-num` not `education`, no `experience` column unless added during training)

---

## 6️⃣ How to Run the Application

### Step-by-step:
Install required libraries

bash
Copy
Edit
pip install pandas scikit-learn matplotlib streamlit joblib
Place the files

Ensure adult.csv is in the correct path or update the path in your code

Make sure best_model.pkl is in the same folder as app.py

Run the app

bash
Copy
Edit
streamlit run app.py

7️⃣ Future Improvements
🔁 Add more evaluation metrics like ROC-AUC

🌎 Expand dataset for better accuracy

🔐 Integrate user login functionality for secure access

📊 Improve UI and add data visualization to the web app

8️⃣ Tech Stack
Tool/Library	Purpose
Python	Programming Language
Pandas	Data manipulation
Scikit-learn	ML Models and Preprocessing
Matplotlib	Data visualization
Joblib	Model saving and loading
Streamlit	Web app development

9️⃣ Author
👩‍💻 Jagrati 
🎓 Computer Science Engineering (CSE)
📈 CGPA: 9.0 +
🚀 Passionate about Java, ML, and Full Stack Development

