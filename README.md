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
`web_threats.csv` - includes traffic data like source IPs, ports, protocols, etc.

## 🛠️ Key Features Created
- `duration`
- `avg_packet_size`
- `hour` of traffic
- Anomaly labels (`is_anomaly`)

## 📈 Output Example
- 15 out of 282 records flagged as suspicious
- Visualizations show most active hours, protocol usage, and country-based interactions

## 💡 Insights
- High `bytes_in` and low `bytes_out` sessions may signal infiltration attempts
- Suspicious traffic from certain country codes and non-standard ports

## ✅ Tools Used
- Python (Pandas, Matplotlib, Seaborn, Scikit-learn)
- Jupyter Notebook

