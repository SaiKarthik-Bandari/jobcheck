# 🛡️ JobShield AI – Fake Job Detection System

JobShield AI is a **machine learning–powered web application** that helps users **identify fake and real job postings**.
It uses **Natural Language Processing (NLP), Machine Learning, rule-based analysis, and JWT authentication** to provide a secure and intelligent job verification platform.

This project is developed as part of an **Internship / Academic Requirement** and includes **Admin Dashboard, Model Retraining, Analytics, and Downloadable Reports**.

---

## 🚀 Features

### 👤 User Features

* User Signup & Login
* Secure authentication using **JWT (Cookies)**
* Analyze job posts using:

  * Text input
  * Image upload (OCR)
* View **Prediction History**
* Download prediction history as CSV
* Logout securely

### 🛠️ Admin Features

* Admin Dashboard with analytics
* View total users, admins, and predictions
* Fake vs Real job statistics
* Daily prediction logs
* View high-risk (flagged) fake jobs
* Promote/Demote users
* **Retrain Machine Learning Model**
* Download all users’ prediction history (CSV)

---

## 🧠 Machine Learning Details

* **Model:** Logistic Regression
* **Vectorizer:** TF-IDF Vectorizer
* **Approach:** Hybrid (Rule-Based + ML)
* **Accuracy Boost:**

  * Scam keywords → Fake Job
  * Government / Trusted keywords → Real Job
* **Retraining:** Admin can retrain model using stored prediction data

---

## 🏗️ Tech Stack

### Backend

* Python
* Flask
* Flask-JWT-Extended
* MySQL
* Pickle

### Frontend

* HTML
* CSS
* Chart.js

### Libraries

* scikit-learn
* pytesseract
* OpenCV
* Pillow
* NumPy

---

## 📂 Project Structure

```
jobcheck_website/
│
├── app.py
├── model/
│   ├── fake_real_job_model.pkl
│   └── tfidf_vectorizer.pkl
│
├── templates/
│   ├── login.html
│   ├── signup.html
│   ├── predict.html
│   ├── user_dashboard.html
│   └── admin_dashboard.html
│
├── static/
│   └── css/
│       ├── admin_dashboard.css
│       └── style.css
│
├── README.md
└── requirements.txt
```

---

## 🗄️ Database Schema

### users

| Column   | Type                 |
| -------- | -------------------- |
| id       | INT (PK)             |
| username | VARCHAR              |
| email    | VARCHAR              |
| password | VARCHAR              |
| role     | ENUM('user','admin') |

### predictions

| Column     | Type     |
| ---------- | -------- |
| id         | INT (PK) |
| user_id    | INT (FK) |
| job_text   | TEXT     |
| prediction | VARCHAR  |
| confidence | FLOAT    |
| source     | VARCHAR  |
| created_at | DATETIME |

---

## ⚙️ Installation & Setup

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/jobcheck.git
cd jobcheck_website
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Setup MySQL Database

```sql
CREATE DATABASE jobcheck_db;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100),
    email VARCHAR(100),
    password VARCHAR(100),
    role VARCHAR(10)
);

CREATE TABLE predictions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    job_text TEXT,
    prediction VARCHAR(50),
    confidence FLOAT,
    source VARCHAR(10),
    created_at DATETIME
);
```

### 4️⃣ Run Application

```bash
python app.py
```

Open in browser:

```
http://127.0.0.1:5000
```

---

## 🔐 Authentication

* JWT tokens stored in **HTTP-only cookies**
* Role-based access (Admin/User)
* Secure logout implemented

---

## 📊 Analytics

* Pie chart: Fake vs Real jobs
* Bar chart: Prediction distribution
* Daily logs table
* Flagged high-confidence fake jobs

---

## 🔁 Model Retraining (Admin)

* Uses stored prediction data
* Improves accuracy over time
* No vectorizer mismatch
* Internship-level real-world feature

---

## 📥 Download Reports

* Users can download **their prediction history**
* Admins can download **all system predictions**
* CSV format supported

---

## 🧪 Testing

* JWT authentication tested
* Admin access control verified
* OCR text extraction tested
* SQL queries validated
* Model retraining validated

---

## 📌 Internship Relevance

✔ Machine Learning integration
✔ Secure authentication
✔ Admin dashboard
✔ Retrainable ML model
✔ Real-world problem solving

---

## 🔮 Future Enhancements

* Email-based password reset
* Deep learning models (BERT / LSTM)
* REST API version
* Cloud deployment
* Real-time job scraping

---

## 👨‍💻 Author

**Bandari Sai Karthik Yadav**
Internship Project – JobShield AI

---

