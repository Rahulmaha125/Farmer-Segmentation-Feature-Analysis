# 🌾 Farmer & Agricultural Segmentation using Unsupervised Learning
> **K-Means Clustering + Principal Component Analysis (PCA) + Feature Contribution Analysis**

An end-to-end Unsupervised Machine Learning project designed to segment Indian agricultural records into distinct farming profiles based on land scale, crop production, and yield productivity.

---

## 🎯 Project Overview & Objective (प्रोजेक्टचा मुख्य उद्देश)

* **English:** The goal of this project is to partition over 240,000 crop records into distinct agricultural segments using land scale (`area`), output volume (`production`), and engineered productivity (`yield_per_hectare`) without relying on any predefined target label.
* **मराठी:** या प्रोजेक्टचा मुख्य उद्देश भारतातील विविध राज्यांतील व जिल्ह्यांतील शेती डेटाचा वापर करून शेतकऱ्यांचे व पिकांचे त्यांच्या जमिनीचा आकार, एकूण उत्पादन आणि प्रति हेक्टरी उत्पादकतेनुसार स्वयंचलित गट (Clusters/Segments) पाडणे हा आहे.

---

## 🛠️ Tech Stack & Libraries

- **Language:** Python 3.10+
- **Data Manipulation:** `pandas`, `numpy`
- **Data Visualization:** `matplotlib`, `seaborn`
- **Machine Learning & Analytics:** `scikit-learn` (`StandardScaler`, `KMeans`, `PCA`, `silhouette_score`)

---

## 📊 Dataset Description

The analysis uses the Indian Agricultural Crop Production dataset (~246,000 records).

| Feature Name | Type | Description |
| :--- | :--- | :--- |
| `state_name` | Categorical | State where crop is cultivated |
| `district_name` | Categorical | District location |
| `crop_year` | Numerical | Year of crop record (1997–2015) |
| `season` | Categorical | Farming season (Kharif, Rabi, Whole Year, etc.) |
| `crop` | Categorical | Type of crop grown (124 unique crops) |
| `area` | Numerical | Cultivated land area (in Hectares) |
| `production` | Numerical | Total crop output (in Metric Tons / Units) |
| **`yield_per_hectare`** | **Engineered** | $\text{Yield} = \frac{\text{Production}}{\text{Area}}$ (Productivity measure) |

---

## 🔄 Machine Learning Workflow

```mermaid
flowchart LR
    A["Raw Crop Data"] --> B["Data Cleaning & Preprocessing"]
    B --> C["Feature Engineering (Yield / Ha)"]
    C --> D["StandardScaler Normalization"]
    D --> E["K-Means Clustering"]
    E --> F["Elbow Method & Silhouette Evaluation"]
    D --> G["PCA (2D Reduction)"]
    G --> H["Cluster Visualization"]
    E --> I["Feature Contribution Analysis"]
