# 🛡️ Tamper Detection in Academic Credentials

**Project Title:** Tamper Detection in Academic Credentials  
**Submission:** GitHub + Google Drive  
**Candidate:** Umesh Chandra 

---

## 📌 Objective

This project aims to develop a lightweight system that automatically detects tampered academic certificates based on structured data analysis. We focus on verifying Great Learning certificates submitted by users and identifying entries that deviate from known valid formats and patterns.

---

## 🧠 Approach & Methodology

### 🔍 Assumptions
- Valid certificate IDs follow the format `GL-XXXXX`
- Approved course names include:
  - AI Foundations
  - Machine Learning
  - Data Science
  - Python Basics
  - Cloud Fundamentals
- Valid issue years fall between 2020 and 2025
- Names that have appeared in the authentic list are considered legitimate

### ⚙️ Model Workflow
1. **Simulated Dataset**: Mix of valid and tampered certificates
2. **Feature Extraction**:
   - `valid_id_format`: Checks if ID format matches expected pattern
   - `valid_course`: Course name match
   - `valid_date`: Checks date range
   - `name_encoded`: Label-encoded user name
3. **Model**: Random Forest Classifier (`sklearn`)
4. **Prediction Output**:
   - Valid Certificate ✅
   - Tampered/Invalid ❌

---

## 📊 Results

- Model was tested on a simulated test set
- Achieved high precision and recall
- Accurately flagged modified or fake entries

### 🔍 Sample Predictions:
```python
predict_certificate("GL-23456", "Jane Smith", "Machine Learning", "2023-07-15")  
# ➜ Valid Certificate ✅

predict_certificate("FAKE-999", "Hacker Man", "Malware Engineering", "2029-01-01")  
# ➜ Tampered/Invalid ❌
