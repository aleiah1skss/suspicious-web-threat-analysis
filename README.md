# suspicious-web-threat-analysis
Anomaly detection in web traffic using Isolation Forest.
# 🚨 Suspicious Web Threat Interaction Detection

This project analyzes web traffic data to detect potentially harmful or suspicious interactions using anomaly detection techniques.

## 📊 Objective
To identify patterns that could indicate security threats (e.g., infiltration attempts, bot activity, or abnormal port usage) using Isolation Forest.

## 🔍 Techniques Used
- Data cleaning & preprocessing
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Anomaly Detection with Isolation Forest
- Visualization & Reporting

## 📁 Dataset
- Name:`web_threats.csv` 
- Contains 282 entries of network traffic logs
- Features: bytes in/out, IPs, protocols, ports, detection types, timestamps, etc.

## 🧠 Key Steps

1. **Data Cleaning**  
   - Handled missing values  
   - Converted timestamp fields to datetime format  

2. **Exploratory Data Analysis (EDA)**  
   - Traffic analysis based on bytes_in / bytes_out  
   - Protocol distribution and hourly traffic pattern

3. **Feature Engineering**  
   - Extracted session duration  
   - Calculated average packet size  

4. **Anomaly Detection (Modeling)**  
   - Applied Isolation Forest to detect abnormal sessions  
   - Evaluated detection rate of anomalies

5. **Insights**
   - 15 anomalies found among 282 entries  
   - High `bytes_in` with low `bytes_out` might indicate infiltration  
   - Non-standard port activity & specific country codes show suspicious patterns

## 📈 Output Example
- 15 out of 282 records flagged as suspicious
- Visualizations show most active hours, protocol usage, and country-based interactions


## ✅ Tools Used
- Python (Pandas, Matplotlib, Seaborn, Scikit-learn)
- Jupyter Notebook

## 📂 Files in this Repo
- `suspicious_web_threat_analysis.ipynb` – Full project notebook
- `web_threats.csv` – Dataset used
- `README.md` – Project overview (this file)

## 📬 Contact
Created as part of a virtual internship by Aliya Nishath

