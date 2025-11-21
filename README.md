# Glasgow Snow Prediction Project ❄️

**Author:** Shreyas Gowda B  
**Documentation & Comments:** ChatGPT (GPT‑5) assisted with structuring and clarity.

---

## 📌 Overview

This project analyses **35 years of historical weather data (1990–2024)** for Glasgow using the **Open‑Meteo Archive API** to answer:

### **1. Will it snow in Glasgow this winter?**  
### **2. When does snow usually *start* in Glasgow winters?**  
### **3. What are the predicted snowy days based on climatology + ML models?**

The notebook performs an end‑to‑end data‑science workflow:

- Data collection (Open‑Meteo API)  
- Feature & label engineering  
- EDA on yearly and monthly snow patterns  
- Daily snow prediction models (Logistic Regression + Random Forest)  
- Winter‑level probability of snow  
- First‑snow‑date statistical analysis  
- Derived prediction window for when snow *typically* arrives  

This project is designed to be transparent, reproducible, and interview‑ready.

---

## 📂 Files in This Project

| File | Description |
|------|-------------|
| `glasgow_snow_openmeteo_prediction.ipynb` | Full notebook with modelling + first‑snow predictions |
| `README.md` | This documentation file |

---

## 🌤 Data Source

All weather data used in this project comes from:

- **Open‑Meteo Historical Weather API**  
  Daily variables retrieved:  
  - `temperature_2m_max`  
  - `temperature_2m_min`  
  - `precipitation_sum`  
  - `snowfall_sum`  

Time Range: **1990–01–01 → 2024–12–31**  
Location: **Glasgow (55.86°N, –4.25°W)**  

---

## 🧠 Methodology Summary

### **1. Label Creation – Snow vs No Snow**
A "snow day" is defined as:
```
snow_today = 1 if snowfall_sum > 0 else 0
```

### **2. Features Used**
- Max Temperature  
- Min Temperature  
- Daily Precipitation  
- Month  
- Day‑of‑Year  

### **3. ML Models**
- **Logistic Regression** (baseline)  
- **Random Forest Classifier** (non‑linear model)

Outputs include classification reports + confusion matrices.

---

## ❄️ Winter‑Level Analysis

### **Probability of at least one snow day per winter**
Winters are defined as:
- **December (Year Y)**  
- **January–February (Year Y+1)**  

Output computed:
- Percentage of winters with **≥1 snowy day**
- List of winters with **zero snow**
- Variation across the decades

---

## 📅 First Snow‑Date Analysis

For each winter, the notebook computes:

- First date where `snow_today == 1`
- Winters with *no* snow at all
- Distribution of first‑snow dates
- **Median first‑snow date**
- **25th–75th percentile window**
- Calendar heatmaps + histograms

This provides a **data‑driven prediction window** for when snow usually begins.

---

## 🔮 Climatological Prediction (How to Interpret)

The notebook’s results help answer:

> “If next winter behaves like the historical record, when is snow most likely to start?”

You will obtain outputs such as:

- **Median first‑snow date:** e.g., *22 January*  
- **Typical window:** e.g., *05 Jan → 15 Feb*  
- **Probability of a snowy winter:** e.g., *78%*  

Replace the above with your actual computed numbers.

---

## 🚀 How to Run

1. Install dependencies:
```
pip install pandas numpy scikit-learn matplotlib requests
```
2. Open the notebook:
```
glasgow_snow_openmeteo_prediction.ipynb
```
3. Run all cells (top → bottom).

The notebook automatically downloads the required historical data.

---

## 📝 Closing Note

This project was built **with care** as a compact, defensible prototype demonstrating:

- Transparent assumptions  
- Clean ML workflow  
- Real‑world climatology application  
- Business‑ready insight communication  

**Made with heart in Glasgow by Shreyas Gowda B.**  
Documentation and explanatory notes prepared with the help of **ChatGPT (GPT‑5)**.

