# suspicious-web-threat-analysis
Anomaly detection in web traffic using Isolation Forest.
#  Suspicious Web Threat Interaction Detection

This project analyzes web traffic data to detect potentially harmful or suspicious interactions using anomaly detection techniques.


##  Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Objectives](#objectives)
- [Tools Used](#tools-used)
- [Project Workflow](#project-workflow)
- [Key Findings](#key-findings)
- [Threat Scoring System](#threat-scoring-system)
- [Executive Recommendations](#executive-recommendations)
- [Conclusion](#conclusion)

  ##  Objective
To identify patterns that could indicate security threats (e.g., infiltration attempts, bot activity, or abnormal port usage) using Isolation Forest.
- Import and explore real-world web traffic logs
- Preprocess and extract key traffic features
- Identify abnormal behavior using Isolation Forest
- Engineer a custom `threat_score` system
- Provide actionable executive-level recommendations


##  Dataset

- Filename: `web_threats.csv`
- Records: 282 web interaction logs
- Key Columns:
  - `src_ip`, `dst_ip`, `src_ip_country_code`, `dst_port`
  - `bytes_in`, `bytes_out`, `creation_time`, `end_time`



##  Tools Used
- Python (Pandas, Matplotlib, Seaborn, Scikit-learn)
- Jupyter Notebook

##  Project Workflow

### 1. Data Cleaning & Preprocessing
- Parsed time columns
- Checked for missing/null values
- Engineered features: `duration`, `avg_packet_size`, `hour`

### 2. Exploratory Data Analysis
- Traffic pattern: `bytes_in` vs `bytes_out`
- Protocol usage distribution
- Country-wise source IPs
- Destination port usage

### 3. Anomaly Detection (Modeling)
- Isolation Forest trained on:
  - `bytes_in`, `bytes_out`, `duration`, `avg_packet_size`
- Labeled anomalies as `is_anomaly`

### 4. Custom Threat Scoring
- Created `threat_score` (0–10 scale) based on:
  - Model anomaly detection
  - Use of suspicious ports (22, 3389, etc.)
  - Source from high-risk countries (CN, RU, etc.)
  - High inbound with low outbound traffic

## Files in this Repo
- `suspicious_web_threat_analysis.ipynb` – Full project notebook
- `web_threats.csv` – Dataset used
- `README.md` – Project overview (this file)

  ##  Key Findings

- Most traffic occurred during business hours
- Ports like 6666, 1337, 4444 appeared frequently in anomalies
- Anomalies typically had high bytes in and very little bytes out
- A few source countries contributed disproportionately to suspicious ev


## ⚠️ Threat Scoring System

Each session was assigned a risk score (0–10) based on a custom logic:

| Criteria                              | Points |
|---------------------------------------|--------|
| Detected as anomaly by model          | +4     |
| Suspicious destination port used      | +2     |
| Country flagged as high-risk          | +2     |
| High `bytes_in` and low `bytes_out`   | +2     |

> The score is capped at 10 to prioritize highest-risk traffic.


##  Executive Recommendations

-  **Block or closely monitor** non-standard ports like 3389, 6666, and 4444
-  **Review IP traffic from high-risk countries** (e.g., CN, RU, KP)
-  **Flag sessions with high inbound and low outbound traffic** for deeper inspection
-  **Consider integrating a threat intelligence API** (like AbuseIPDB) for real-time IP blacklisting
-  **Apply stricter firewall or IDS rules** based on threat score

##  Conclusion

This project demonstrates how machine learning and data analysis can be used to:
- Proactively detect suspicious web activities
- Assign a custom threat score
- Generate actionable recommendations for cybersecurity teams


## 📬 Contact
Created as part of a virtual internship by Aliya Nishath

