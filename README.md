# 🏨 Executive Hotel Booking & Guest Analytics Suite (with Python AI Predictor)

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit_Learn-Random_Forest-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0%2B-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Power BI](https://img.shields.io/badge/Power_BI-Executive_Theme-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Web BI](https://img.shields.io/badge/Web_BI-AI_Powered-06B6D4?style=for-the-badge&logo=html5&logoColor=white)](http://localhost:8080)

An executive-style **Hotel Booking Analytics & AI Machine Learning Suite** designed for hotel general managers, revenue directors, and operations leads. This end-to-end intelligence platform combines traditional BI dashboards with an easy-to-use **Python AI Cancellation Risk Predictor engine**.

---

## 🤖 New Feature: Easy Python AI Machine Learning Engine

The project includes an easy-to-understand **Random Forest AI Classifier** (`scripts/ai_cancellation_predictor.py`) built with `scikit-learn` that predicts booking cancellations and quantifies financial risk factors:

- **AI Model**: Random Forest Classifier trained on 15,000 reservation records.
- **Risk Scoring**: Scores every reservation with an **AI Cancellation Probability (0%–100%)** and assigns a risk tier (*Low Risk*, *Medium Risk*, *High Risk*).
- **Feature Importance Ranking**:
  - **Average Daily Rate (ADR)** (`26.8%` influence): Higher room rates increase cancellation sensitivity.
  - **Lead Time** (`24.8%` influence): Bookings created far in advance have the highest cancellation rates.
  - **Hotel Type** (`12.4%` influence): City Hotels experience higher drop-off rates than Resort Hotels.
  - **Total Stay Nights** (`11.6%` influence): Longer stay durations increase booking volatility.
  - **Booking Changes** (`4.2%` influence): Frequent modifications signal potential cancellation.

---

## 🎯 Business Goal & Primary Questions

The primary objective of this dashboard is to answer core commercial and operational questions:
- **Revenue Drivers**: Which hotel types (*City Hotel* vs *Resort Hotel*), room tiers, customer groups, and booking periods generate the most realized revenue?
- **Cancellation Hotspots**: Where, when, and among which customer segments are cancellations occurring, and what is the estimated monetary revenue loss?
- **AI Risk Forecasting**: Which individual reservations are at highest risk of cancelling, and what proactive actions should hotel management take?
- **Relationship Dynamics**: How do booking channels and customer segments connect to cancellation outcomes?

---

## 📊 Executive Core KPIs & Formulas

| Core Metric | Calculation / Logic | Accent Color | Description |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | `SUM(ADR * (stays_in_week_nights + stays_in_weekend_nights))` | Cyan `#06B6D4` | Gross potential value of all reservations |
| **Realized Revenue** | `SUM(Revenue)` WHERE `is_canceled = 0` | Emerald `#10B981` | Revenue collected from completed check-outs |
| **Revenue Lost** | `SUM(Revenue)` WHERE `is_canceled = 1` | Rose `#EF4444` | Financial leakage from cancelled bookings |
| **Total Bookings** | `COUNT(booking_id)` | Blue `#3B82F6` | Total volume of reservations generated |
| **Cancelled Bookings** | `COUNT(booking_id)` WHERE `is_canceled = 1` | Coral `#F43F5E` | Count of cancellations and no-shows |
| **Cancellation Rate** | `Cancelled Bookings / Total Bookings` | Crimson `#DC2626` | Percentage of total reservations cancelled |
| **Average Daily Rate (ADR)** | `AVERAGE(adr)` | Amber `#F59E0B` | Average price paid per room night |
| **Avg Length of Stay** | `AVERAGE(stays_in_week_nights + stays_in_weekend_nights)` | Purple `#8B5CF6` | Average stay duration in nights |
| **Repeat Guest Rate** | `COUNT(is_repeated_guest = 1) / Total Bookings` | Indigo `#6366F1` | Percentage of returning loyal guests |

---

## 🛠️ Toolstack & Project Workflow

The project follows a multi-tier analytics and machine learning pipeline:
