# 🌾 Agricultural Record & Farmer Segmentation System
> **Unsupervised Machine Learning | K-Means Clustering | PCA | Feature Contribution Analysis | Streamlit Web App**

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/ML-K--Means%20%7C%20PCA-green.svg)](https://scikit-learn.org/)
[![Dashboard](https://img.shields.io/badge/Streamlit-Interactive%20App-red.svg)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

An enterprise-grade Unsupervised Machine Learning workflow that segments over 240,000 Indian agricultural records into distinct farming profiles based on land scale (`area`), output volume (`production`), and productivity (`yield_per_hectare`).

---

## 🎯 Executive Summary & Objectives

Agricultural decision-making often relies on aggregate regional statistics, ignoring the vast diversity of farm scales and productivity levels across districts. 

This project applies **K-Means Clustering** and **Principal Component Analysis (PCA)** to uncover hidden patterns in agricultural data without ground-truth labels. It identifies distinct farm clusters—ranging from smallholder subsistence crops to high-tech intensive agriculture—and features a production-ready **Streamlit Interactive Dashboard** for real-time policy and business analytics.

---

## 🏢 Why This Project Matters for Private Agritech & Companies

Private sector organizations in the agriculture ecosystem can leverage these segment profiles for precision targeting, risk management, and market expansion:

### 1. 🚜 Agritech & Equipment Manufacturers
- **Targeted Equipment Sales:** Small-landholding clusters require micro-machinery and affordable tools, whereas large-scale commercial clusters are prime markets for heavy machinery, harvesters, and automated drones.
- **Service Customization:** Tailor tech-enabled farm advisory services (weather, pest alerts) based on regional productivity clusters.

### 2. 🧪 Seed, Fertilizer & Chemical Companies
- **Productivity-Based Sales Pipeline:** High-yield clusters have higher purchasing power for premium hybrid seeds and bio-fertilizers.
- **Demand Forecasting:** Predict regional demand for specific inputs based on seasonal and crop-cluster distributions.

### 3. 🏦 Banks, NBFCs & Microfinance Institutions
- **Credit Risk Profiling:** Assess loan default risks based on a cluster’s historical `yield_per_hectare` stability rather than land size alone.
- **Customized Loan Products:** Offer low-interest micro-loans for subsistence clusters and commercial credit facilities for high-production clusters.

### 4. 🚛 Supply Chain, Warehousing & E-Commerce
- **Logistics Infrastructure:** Position cold-storage units, grain silos, and fulfillment centers near high-volume commercial clusters.
- **Direct Procurement:** Enable farm-to-fork e-commerce platforms to directly contract with high-productivity clusters, cutting out middlemen.

---

## 🏛️ Why This Project is Critical for Government & Policy Makers

For governments and public sector agencies, data-driven farmer segmentation transforms blanket policies into precision governance:

### 1. 💰 Targeted Subsidies & Direct Benefit Transfer (DBT)
- **Eliminating Leakages:** Ensure government subsidies (PM-KISAN, fertilizer subsidies) reach vulnerable smallholder subsistence clusters rather than being over-absorbed by commercial farms.

### 2. 🌊 Irrigation & Infrastructure Allocation
- **Water Management:** Direct public funds for canal networks, micro-irrigation, and solar pumps to low-yield but high-area clusters to unlock their full potential.

### 3. 🛡️ Crop Insurance & PMFBY (Pradhan Mantri Fasal Bima Yojana)
- **Accurate Premium Pricing:** Calculate fair insurance premiums by analyzing cluster-level yield volatility instead of district-level averages.
- **Faster Claim Settlement:** Use cluster yield benchmarks to audit disaster relief and loss assessments efficiently.

### 4. 🍏 Food Security & Price Stabilization
- **Buffer Stock Planning:** Monitor essential food-crop clusters (Rice, Wheat, Pulses) in real time to prevent regional shortages and manage price inflation.

---

## 📊 Dataset & Feature Architecture

The model is trained on public Indian crop production data (~246,000 records).

| Feature Name | Type | Description | Strategic Importance |
| :--- | :--- | :--- | :--- |
| `state_name` | Categorical | State location | Regional governance & policy scope |
| `district_name` | Categorical | District location | Local administration & logistics routing |
| `crop_year` | Temporal | Year (1997–2015) | Trend analysis & climate impact evaluation |
| `season` | Categorical | Farming season | Seasonal input demand & market planning |
| `crop` | Categorical | Crop type (124 crops) | Crop-specific intervention & market linkage |
| `area` | Numerical | Cultivated Area (Hectares) | Measures land scale |
| `production` | Numerical | Total Output (Metric Tons) | Measures volume scale |
| **`yield_per_hectare`** | **Engineered** | $\frac{\text{Production}}{\text{Area}}$ | **Measures true land productivity & efficiency** |

---

## 🔄 Machine Learning & Web Architecture

```mermaid
flowchart TD
    A["Raw Crop Dataset (246K+ Records)"] --> B["Data Cleaning & Preprocessing"]
    B --> C["Feature Engineering (Yield / Ha)"]
    C --> D["StandardScaler Normalization"]
    D --> E1["K-Means Clustering Optimization"]
    D --> E2["PCA 2D Dimensionality Reduction"]
    E1 --> F["Elbow Curve & Silhouette Evaluation"]
    E2 --> G["Feature Loadings & Separation Analysis"]
    F & G --> H["Export Clustered Dataset (CSV)"]
    H --> I["Streamlit Web App (app.py)"]
    I --> J["Interactive Filters, KPIs & Visualizations"]
