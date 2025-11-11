# 🌱 Greenhouse Gas Emission Prediction (2010–2016)

A complete Machine Learning project that predicts **Supply Chain Emission Factors with Margins** using multi-year industry and commodity emission datasets.  
The project includes dataset merging, preprocessing, model training, evaluation, and a deployed Streamlit web application.

---

## 📌 Project Overview
This project uses a multi-sheet Excel dataset containing emission data from **2010 to 2016**.  
Each year in the dataset includes two sheets:

- <year>_Detail_Commodity  
- <year>_Detail_Industry  

The main goal is to:
- Merge these sheets year-wise  
- Clean and standardize the data  
- Build and evaluate regression models  
- Deploy a prediction interface using Streamlit  

---

## 🎯 Objectives
- Understand and visualize greenhouse gas emission patterns  
- Clean and preprocess multi-year Excel data  
- Apply feature engineering and data encoding  
- Train and evaluate regression models  
- Deploy the model using Streamlit for real-time predictions  

---

## 🛠️ Technologies Used

### Programming Language
- Python

### Libraries
- pandas  
- numpy  
- scikit-learn  
- matplotlib  
- seaborn  
- joblib  
- Streamlit  

### Tools
- Jupyter Notebook  
- VS Code  

---

## 📂 Dataset Structure
The dataset contains two sheets for each year from 2010 to 2016:

2010_Detail_Commodity
2010_Detail_Industry
2011_Detail_Commodity
2011_Detail_Industry
...
2016_Detail_Commodity
2016_Detail_Industry

markdown
Copy code

Each sheet includes:
- Code  
- Name  
- Substance  
- Unit  
- Reliability  
- Temporal Correlation  
- Geographical Correlation  
- Technological Correlation  
- Emission Factor  

---

## 🔄 Data Processing Pipeline

### ✅ 1. Load Data
Read Commodity and Industry sheets for every year.

### ✅ 2. Add Metadata Columns
Add additional columns:
- `Source` (Commodity / Industry)  
- `Year` (2010–2016)  

### ✅ 3. Clean Column Names
Remove extra whitespace and standardize:
- Commodity Code → Code  
- Industry Code → Code  
- Commodity Name → Name  
- Industry Name → Name  

### ✅ 4. Merge Commodity & Industry Data
Combine commodity and industry datasets for each year using `pd.concat`.

### ✅ 5. Combine All Years
Merge all years into a single final dataframe:

df = pd.concat(all_data, ignore_index=True)

sql
Copy code

### ✅ 6. Remove Unnecessary Columns
Drop empty or irrelevant columns like:

df.drop(columns=['Unnamed: 7'], inplace=True)

markdown
Copy code

### ✅ 7. Data Preprocessing
- Handle missing values  
- Encode categorical variables  
- Scale numerical features  

### ✅ 8. Model Training
Train ML regression models:
- Linear Regression  
- Random Forest Regressor  

### ✅ 9. Model Evaluation
Evaluate using:
- R² Score  
- Mean Absolute Error (MAE)  
- Root Mean Squared Error (RMSE)  

### ✅ 10. Save Trained Model
Save the final model using joblib:

joblib.dump(model, "ghg_model.pkl")

yaml
Copy code

---

## 🚀 Streamlit Application

The Streamlit app allows users to input:
- Substance  
- Unit  
- Reliability  
- Temporal / Geographical / Technological correlations  
- Code or Name  

The app outputs:
✅ **Predicted Supply Chain Emission Factor with Margin**

Run the app using:

streamlit run app.py

yaml
Copy code

---

## 📊 Visualizations Included
- Year-wise emission trends  
- Correlation heatmaps  
- Distribution plots  
- Feature importance (Random Forest)  

---

## 📁 Recommended Project Structure

GHG-Emission-Prediction
│ README.md
│ requirements.txt
│ data/
│ SupplyChainEmissionFactorsforUSIndustriesCommodities.xlsx
│ notebooks/
│ data_cleaning.ipynb
│ models/
│ ghg_model.pkl
│ app/
│ app.py

yaml
Copy code

---

## ✨ Key Features
- Multi-year, multi-sheet dataset integration  
- Clean and efficient preprocessing pipeline  
- Regression model with strong interpretability  
- Fully functional Streamlit prediction interface  

---
