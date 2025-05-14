# 🏠 House Price Prediction with Feature Engineering

<div align="center">
  
  ![Python](https://img.shields.io/badge/Python-3.8+-blue)
  ![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-orange)
  ![License](https://img.shields.io/badge/License-MIT-green)
  ![Accuracy](https://img.shields.io/badge/R%C2%B2%20Score-60.65%25-brightgreen)
  
</div>

---

## 📋 Project Overview

> **This project demonstrates comprehensive feature engineering techniques for predicting house prices using machine learning.**

Through **careful data preprocessing**, **feature creation**, and **model evaluation**, we achieve **60.65%** accuracy in predicting house prices.

---

## 🎯 Objectives

<table>
<tr>
<td>🔧</td>
<td><strong>Apply advanced feature engineering</strong> techniques to improve model performance</td>
</tr>
<tr>
<td>📊</td>
<td><strong>Demonstrate the impact</strong> of data preprocessing on prediction accuracy</td>
</tr>
<tr>
<td>🧠</td>
<td><strong>Create meaningful features</strong> using domain knowledge</td>
</tr>
<tr>
<td>📈</td>
<td><strong>Build an interpretable</strong> linear regression model for house price prediction</td>
</tr>
</table>

---

## 📊 Dataset Overview

<div align="center">
  <img src="https://img.shields.io/badge/Records-538%20Houses-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Features-13%20Original-green?style=for-the-badge">
</div>

### 📈 **Numerical Features**
- `area` - Total area of the house (sq ft)
- `bedrooms` - Number of bedrooms
- `bathrooms` - Number of bathrooms
- `stories` - Number of stories/floors
- `parking` - Number of parking spaces

### 🏷️ **Categorical Features**
- `mainroad` - Located on main road (yes/no)
- `guestroom` - Has guestroom (yes/no)
- `basement` - Has basement (yes/no)
- `hotwaterheating` - Has hot water heating (yes/no)
- `airconditioning` - Has air conditioning (yes/no)
- `prefarea` - In preferred area (yes/no)
- `furnishingstatus` - Furnished/Semi-furnished/Unfurnished

---

## 🔧 Feature Engineering Pipeline

### ✨ **1. Data Cleaning**
```
📍 Outlier Detection: Z-score method (threshold=3)
📍 Outliers Removed: 7 properties with extreme area values
📍 Missing Values: None found (clean dataset)
```

### 🔄 **2. Feature Encoding**
```
📍 Binary Encoding: yes/no → 1/0 for 6 categorical features
📍 One-Hot Encoding: furnishingstatus → 2 binary columns (drop_first=True)
```

### ⚖️ **3. Feature Scaling**
```
📍 StandardScaler: Applied to price and area features
📍 Result: Mean ≈ 0, Standard Deviation ≈ 1
```

### 🆕 **4. Feature Creation**
<table>
<tr>
<th>Feature</th>
<th>Formula</th>
<th>Purpose</th>
</tr>
<tr>
<td><code>total_rooms</code></td>
<td>bedrooms + bathrooms</td>
<td>Overall space indicator</td>
</tr>
<tr>
<td><code>price_area_ratio</code></td>
<td>price / area</td>
<td>Price per unit area</td>
</tr>
<tr>
<td><code>luxury_score</code></td>
<td>AC + (parking≥1) + prefarea</td>
<td>Amenity composite score</td>
</tr>
<tr>
<td><code>size_category</code></td>
<td>Binned area (4 categories)</td>
<td>Small, Medium, Large, XLarge</td>
</tr>
</table>

---

## 📈 Model Performance

<div align="center">
  
  | Metric | Training | Testing |
  |--------|----------|---------|
  | **R² Score** | 🟢 69.52% | 🎯 **60.65%** |
  | **RMSE** | 0.5228 | 0.7396 |
  | **Overfitting** | ✅ **None Detected** |
  
</div>

### 🎉 **Key Achievement**
- **Algorithm**: Linear Regression  
- **No Overfitting**: Difference < 10%  
- **Solid Performance**: 60.65% real-world accuracy

---

## 🏆 Top 10 Feature Importance

<div align="center">

| 🏅 Rank | Feature | Importance | Type |
|:-------:|---------|-----------|------|
| 🥇 **1** | `size_xlarge` | **0.598** | 🆕 *Engineered* |
| 🥈 **2** | `size_large` | **0.379** | 🆕 *Engineered* |
| 🥉 **3** | `bathrooms` | **0.302** | 📊 *Original* |
| **4** | `airconditioning` | **0.291** | 📊 *Original* |
| **5** | `guestroom` | **0.245** | 📊 *Original* |
| **6** | `mainroad` | **0.233** | 📊 *Original* |
| **7** | `luxury_score` | **0.214** | 🆕 *Engineered* |
| **8** | `furnishingstatus_unfurnished` | **0.211** | 📊 *Encoded* |
| **9** | `stories` | **0.208** | 📊 *Original* |
| **10** | `size_medium` | **0.199** | 🆕 *Engineered* |

</div>

### 💡 **Key Insights**
- 🎯 **Size dominates** pricing (top 2 features)
- 🚀 **Engineered features excel**: 4 out of top 10
- 🏠 **Amenities matter**: AC and guestroom impact price
- 📍 **Location premium**: Main road houses cost more
