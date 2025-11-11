# 🌱 Greenhouse Gas Emission Prediction  
Machine Learning model + Streamlit app for predicting Supply Chain Emission Factors (2010–2016)

---

## 📌 Project Overview

This project predicts **Supply Chain Emission Factors with Margins** using historical data (2010–2016) for both **Industries** and **Commodities**.  
The dataset comes from a multi-sheet Excel file where each year has:

- `<year>_Detail_Commodity`
- `<year>_Detail_Industry`

The goal is to combine all sheets, clean the data, build a regression model, and deploy an interactive prediction app using **Streamlit**.

---

## 🎯 Objectives

- Understand & visualize GHG emission patterns.  
- Clean, merge, and preprocess multi-year Excel datasets.  
- Train regression models (Linear Regression, Random Forest).  
- Compare model performance using R², MAE, and RMSE.  
- Deploy a user-friendly Streamlit web application.

---

## 🛠️ Tools & Technologies

### **Programming Language**
- Python

### **Libraries**
- pandas, numpy (data cleaning and processing)  
- scikit-learn (machine learning)  
- matplotlib, seaborn (visualization)  
- joblib (saving ML models)  
- Streamlit (web app)  
- Jupyter Notebook (experimentation)

---

## 📂 Dataset Structure

Each year contains two sheets:

2010_Detail_Commodity
2010_Detail_Industry
2011_Detail_Commodity
2011_Detail_Industry
...
2016_Detail_Commodity
2016_Detail_Industry

## 🔄 Data Processing Pipeline

### ✅ 1. Load Data
For every year (2010–2016), load both commodity and industry sheets.

### ✅ 2. Add Metadata Columns
- `Source` → Commodity / Industry  
- `Year` → Marks the year of data  

### ✅ 3. Standardize Column Names
Strip whitespace and rename:

Commodity Code → Code
Industry Code → Code
Commodity Name → Name
Industry Name → Name

sql
Copy code

### ✅ 4. Merge Yearly Data
Combine commodity + industry sheets for each year.

### ✅ 5. Combine All Years
Concatenate all years into one final DataFrame:

```python
df = pd.concat(all_data, ignore_index=True)
✅ 6. Clean Redundant Columns
Remove empty columns like:

python
Copy code
df.drop(columns=['Unnamed: 7'], inplace=True)
✅ 7. Preprocessing
Handle missing values

Encode categorical features

Scale numerical columns

✅ 8. Model Training
Models used:

Linear Regression

Random Forest Regressor

Evaluation metrics:

R² Score

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

## ✅ 9. Model Saving
python
Copy code
joblib.dump(model, "ghg_model.pkl")
🚀 Streamlit App
The Streamlit app allows the user to input:

Substance

Unit

Reliability

Correlation values

Code / Name

It then predicts:

✅ Supply Chain Emission Factor with Margin
Run the app:

bash
Copy code
streamlit run app.py
📊 Visualizations
Distribution plots

Correlation heatmaps

Comparison of emission factors across years

Feature importance plots (Random Forest)

📎 Folder Structure (Suggested)
kotlin
Copy code
📁 GHG-Emission-Prediction
│── 📄 README.md
│── 📄 requirements.txt
│── 📁 data/
│     └── SupplyChainEmissionFactorsforUSIndustriesCommodities.xlsx
│── 📁 notebooks/
│     └── data_processing.ipynb
│── 📁 models/
│     └── ghg_model.pkl
│── 📁 app/
│     └── app.py
🎓 What I Learned
Combining multi-sheet Excel datasets programmatically

Cleaning real-world messy data

Feature engineering for regression

Building and evaluating ML pipelines

Deploying machine learning models using Streamlit

