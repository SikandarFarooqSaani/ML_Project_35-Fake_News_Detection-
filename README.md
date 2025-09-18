# 📰 Fake News Detection using Machine Learning

> ⚠️ **Note:** This response is AI-generated (except images) for clarity and ease of explanation 😊  


## 📌 Project Overview
This project focuses on detecting **fake vs. true news** using machine learning models.  
The dataset was vectorized using **TF-IDF** (max 5000 features) and multiple algorithms were tested, including hyperparameter tuning with **Optuna**.  

📂 **Dataset Link:** [Kaggle - Fake News Detection](https://www.kaggle.com/datasets/emineyetm/fake-news-detection-datasets)

---

## 📊 Dataset Details
- Concatenated and shuffled data  
- Selected columns: `title`, `text`, `subject`, `date`  
- Added **label feature**:  
  - **0 → Fake News**  
  - **1 → True News**  

---

## ⚙️ Models and Results

### 1️⃣ K-Nearest Neighbors (KNN)
- Preprocessing: StandardScaler + KNN (k=3, p=1 Manhattan)  
- Accuracy: **0.52** (weak baseline)  

---

### 2️⃣ Logistic Regression
- Accuracy: **0.9850**  
- Errors: 86 FP, 49 FN  
- <img width="518" height="393" alt="35-1" src="https://github.com/user-attachments/assets/8fa7e44d-956c-49b6-bb54-2acd10d47919" />


---

### 3️⃣ Multinomial Naïve Bayes
- Accuracy: **0.92**  
- Errors: 321 FP, 340 FN  
- <img width="518" height="393" alt="35-6" src="https://github.com/user-attachments/assets/c6a67ec1-7dd2-4d77-a6e1-ed0c92e07186" />


---

### 4️⃣ XGBoost
- Accuracy: **0.997** 🎯 (Best single model)  
- Errors: 14 FP, 10 FN  
- <img width="518" height="393" alt="35-2" src="https://github.com/user-attachments/assets/14c35435-fddc-4b58-b684-65dcf7def4da" />

---

### 5️⃣ Decision Tree
- Accuracy: **0.995**  
- Errors: 14 FP, 24 FN  
- <img width="518" height="393" alt="35-3" src="https://github.com/user-attachments/assets/b22c54c0-d6de-4745-85e5-f4b8956be065" />


---

### 6️⃣ Random Forest
- Accuracy: **0.996**  
- Errors: 13 FP, 15 FN  
- <img width="518" height="393" alt="35-4" src="https://github.com/user-attachments/assets/7f749189-a451-415e-af99-f650a57d6833" />


---

## 🔧 Hyperparameter Tuning with Optuna

### Logistic Regression (Optuna Tuned)
- Accuracy: **0.994**  
- Errors: 18 FP, 29 FN  
- <img width="518" height="393" alt="35-5" src="https://github.com/user-attachments/assets/bd909396-0f3d-46be-b566-e421d675372b" />


---

### Decision Tree (Optuna Tuned)
- Accuracy: **0.994**  
- Errors: 29 FP, 19 FN  
- <img width="518" height="393" alt="35-5" src="https://github.com/user-attachments/assets/453e97fd-aa3f-4d2d-9207-1b1ff55036d3" />


---

## 📊 Model Comparison

| Model                  | Accuracy | False Positives | False Negatives |
|-------------------------|----------|-----------------|-----------------|
| KNN                    | 0.52     | –               | –               |
| Logistic Regression     | 0.985    | 86              | 49              |
| MultinomialNB           | 0.92     | 321             | 340             |
| XGBoost                | 0.997    | 14              | 10              |
| Decision Tree           | 0.995    | 14              | 24              |
| Random Forest           | 0.996    | 13              | 15              |
| Logistic (Optuna)       | 0.994    | 18              | 29              |
| Decision Tree (Optuna)  | 0.994    | 29              | 19              |

---

## 🏁 Key Takeaways
- **XGBoost** achieved the highest accuracy (**99.7%**) with the fewest errors.  
- **Random Forest** was very close behind (**99.6%**).  
- **Logistic Regression** performed surprisingly well (98.5%) even without complex ensembles.  
- **Naïve Bayes** was not competitive due to its simplifying assumptions.  
- **Optuna tuning** improved Logistic and Decision Tree slightly but didn’t beat XGBoost or Random Forest.  

---

## 🙌 Conclusion
This project shows that **ensemble methods (XGBoost, Random Forest)** are extremely effective in detecting fake news.  
Final recommendation:  
- **Best Model:** `XGBoost (0.997)`  
- Balanced trade-off of **high accuracy** and **low false predictions**.  

---
