# Assignment 1

Using k-Nearest Neighbours, predict if a student will **Pass (1)** or **Fail (0)** based on:

- $X_1$ = Hours Studied
- $X_2$ = Sleep Hours

---

## Training Data (10 Students)

| Student | Hours Studied $X_1$ | Sleep Hours $X_2$ | Pass/Fail (Y) |
| ------- | ------------------- | ----------------- | ------------- |
| 1       | 1.0                 | 5.0               | 0 (Fail)      |
| 2       | 2.0                 | 5.5               | 0 (Fail)      |
| 3       | 3.0                 | 6.0               | 0 (Fail)      |
| 4       | 4.5                 | 5.0               | 0 (Fail)      |
| 5       | 5.0                 | 6.5               | 1 (Pass)      |
| 6       | 5.5                 | 7.0               | 1 (Pass)      |
| 7       | 6.0                 | 6.0               | 1 (Pass)      |
| 8       | 7.0                 | 7.0               | 1 (Pass)      |
| 9       | 8.0                 | 6.0               | 1 (Pass)      |
| 10      | 9.0                 | 7.5               | 1 (Pass)      |

---

## Task

A new student studied **4 hours** and slept **6 hours**.  
We want to predict whether they **Pass** or **Fail** using **KNN with k = 3**.

---

## 1. Plot all data points using a scatter plot (10 points)

- Use a circle 🔵 for students who failed.
- Use a square 🟥 for students who passed.
- Use a star ⭐ for the unknown data point.

<img width="567" height="432" alt="image" src="https://github.com/user-attachments/assets/e908c609-bfce-4ab4-adb1-0f98a62b7abc" />

---

## 2. Compute Distances (10 points)

**Note:** Please show all solutions

For the new student, compute the **Euclidean distance** from all data points:

$$
d = \sqrt{(X_1 - 4)^2 + (X_2 - 6)^2}
$$

Fill in the table below:

| Student | Hours Studied (X1) | Sleep Hours (X2) | Pass/Fail (Y) | Euclidean Distance |
| ------- | ------------------ | ---------------- | ------------- | ------------------ |
| 1       | 1.0                | 5.0              | 0             | 3.16               |
| 2       | 2.0                | 5.5              | 0             | 2.06               |
| 3       | 3.0                | 6.0              | 0             | 1.00               |
| 4       | 4.5                | 5.0              | 0             | 1.12               |
| 5       | 5.0                | 6.5              | 1             | 1.12               |
| 6       | 5.5                | 7.0              | 1             | 1.8                |
| 7       | 6.0                | 6.0              | 1             | 2.00               |
| 8       | 7.0                | 7.0              | 1             | 3.16               |
| 9       | 8.0                | 6.0              | 1             | 4.00               |
| 10      | 9.0                | 7.5              | 1             | 5.22               |

<img width="953" height="1920" alt="image" src="https://github.com/user-attachments/assets/79414e7b-4a39-4966-bf18-e730d91b7a9c" />

---

## 2. Find the 3 Nearest Neighbors (3 points)

- Highlight the rows with the **3 smallest distances**.

| Student | Hours Studied (X1) | Sleep Hours (X2) | Pass/Fail (Y) | Euclidean Distance |
| ------- | ------------------ | ---------------- | ------------- | ------------------ |
| 1       | 1.0                | 5.0              | 0             | 3.16               |
| 2       | 2.0                | 5.5              | 0             | 2.06               |
| **3🔺**    | **3.0**                | **6.0**              | **0**             | **1.00**               | 
| **4🔺**    | **4.5**                | **5.0**              | **0**             | **1.12**               | 
| **5🔺**    | **5.0**                | **6.5**              | **1**             | **1.12**               | 
| 6       | 5.5                | 7.0              | 1             | 1.8                |
| 7       | 6.0                | 6.0              | 1             | 2.00               |
| 8       | 7.0                | 7.0              | 1             | 3.16               |
| 9       | 8.0                | 6.0              | 1             | 4.00               |
| 10      | 9.0                | 7.5              | 1             | 5.22               |

---

## 3. Majority Vote (2 points)

- Count how many are **Pass (1)** and how many are **Fail (0)**.
- Predict the outcome for the new student.

| Student | Hours Studied (X1) | Sleep Hours (X2) | Pass/Fail (Y) | Euclidean Distance |
| ------- | ------------------ | ---------------- | ------------- | ------------------ |
| 1       | 1.0                | 5.0              | 0             | 3.16               |
| 2       | 2.0                | 5.5              | 0             | 2.06               |
| **3🔺**    | **3.0**                | **6.0**              | **0**             | **1.00**               | 
| **4🔺**    | **4.5**                | **5.0**              | **0**             | **1.12**               | 
| **5🔺**    | **5.0**                | **6.5**              | **1**             | **1.12**               | 
| 6       | 5.5                | 7.0              | 1             | 1.8                |
| 7       | 6.0                | 6.0              | 1             | 2.00               |
| 8       | 7.0                | 7.0              | 1             | 3.16               |
| 9       | 8.0                | 6.0              | 1             | 4.00               |
| 10      | 9.0                | 7.5              | 1             | 5.22               |

**Prediction:** A new student who studied 4 hours and slept 6 hours will **FAIL** the exam.

---

## 4. Discussion Questions (5 points)

1. What was your final prediction? ***The prediction was the new student who studied 4 hours and slept 6 hours would have FAILED the exam***
2. How would the prediction change if we used **k = 5** instead of **k = 3**? ***The prediction would result in a PASS, due to the neighbors majority is PASS***

---
