# 🏠 EstateMate: AI-Powered Real Estate Valuation and Affordability Decision Support System

**Course:** Artificial Intelligence for Business Decisions and Transformation  

---

## 📘 Overview

This project demonstrates how **AI and Machine Learning** can be applied to **real estate markets** to improve **decision-making** for buyers, sellers, lenders, and policymakers.  
It introduces an **AI-powered decision support system (DSS)** capable of:

1. Predicting fair housing prices using historical property data.  
2. Evaluating housing affordability based on local income levels.  
3. Supporting policy analysis and housing strategy through affordability scoring.  

The solution aligns with the course’s goal: using **AI to drive transparent, data-backed business transformation**.

---

## 🧠 Problem Definition

The real estate market often lacks transparency, leaving homebuyers uncertain about fair value and affordability.  
This project tackles that by developing a **data-driven pricing and affordability tool** that integrates machine learning with economic affordability metrics.

### Business Challenges Addressed
- Difficulty in evaluating **fair property value** across regions.  
- Lack of standardized **affordability benchmarks** for policymakers.  
- Limited **decision support tools** for housing market stakeholders.

---

## ⚙️ System Architecture

The system consists of four modules:

| Module | Description |
| ------- | ------------ |
| **1. Data Processing** | Cleans and prepares real estate data (City, Province, Latitude, Longitude, Price, Bedrooms, Bathrooms, Acreage, Property Type, Square Footage). |
| **2. Price Prediction Model** | Uses ML models (Random Forest, XGBoost) to predict property prices based on features. |
| **3. Affordability Analyzer** | Calculates affordability using median household income and price predictions. |
| **4. Dashboard/Insights** | Presents predictions and affordability insights to users for informed decisions. |

---

## 🧩 Datasets

| Feature | Description |
| -------- | ------------ |
| City | City where the property is located |
| Province | Province or region |
| Latitude / Longitude | Geospatial data |
| Price | Sale or listing price |
| Bedrooms / Bathrooms | Property features |
| Acreage | Lot size |
| Property Type | Detached, Condo, etc. |
| Square Footage | Living area size |

**Source:**  
Dataset derived from Canadian real estate listings (e.g., Kaggle’s *Canada Real Estate Market Dataset*).

---

## 🤖 Implementation

Two prototype versions were developed and compared:

| Version | Description | Tools Used |
| -------- | ------------ | ----------- |
| **1. Without Generative AI** | Traditional ML workflow: data preprocessing, feature engineering, Random Forest regression, and affordability scoring. | Pandas, Scikit-learn, Matplotlib |
| **2. With Generative AI** | Integrates **AutoGluon pretrained AutoML models**, leveraging automated hyperparameter optimization, validation handling, and ensemble learning for price prediction. | AutoGluon, Pandas, Python |

Both versions implement:
- **Train/Validation/Test split:** 80/10/10  
- **Performance Metrics:** MAE, MSE, R²  
- **Affordability Labeling:** Affordable / At Risk / Unaffordable  

---

## 📈 Affordability Scoring Formula

\[
\text{Affordability Score} = \frac{\text{Predicted Annual Housing Cost}}{\text{Median Household Income}}
\]

| Score Range | Label |
| ------------ | ------ |
| < 0.50 | ✅ Affordable |
| 0.50–0.80 | ⚠️ At Risk |
| > 0.80 | 🚫 Unaffordable |

---

## 🧮 Example Output

```text
Random Sample from Toronto, Ontario
Predicted Price: $750,000
Affordability Score: 0.48 → ✅ Affordable
