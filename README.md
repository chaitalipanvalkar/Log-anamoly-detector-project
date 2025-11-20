# Log-anamoly-detector-project
#  Real-Time Hybrid Log Monitoring & Anomaly Detection System  
### Final Year Project – Python | Machine Learning | Tkinter | Cybersecurity

A real-time log monitoring system that detects anomalies using:
- **Hybrid Machine Learning Models** (Isolation Forest + Autoencoder)
- **Rule-Based Detection**
- **HMAC-based Log Integrity Verification**
- **Real-Time Tkinter Dashboard**
- **SQLite Storage**
- **Support for Mixed Logs (System + App + Web + Security)**

This system is inspired by modern SIEM tools like **ELK Stack, Splunk, Wazuh**, and provides a lightweight but powerful alternative for real-time monitoring.

---

##  Project Highlights

###  1. Real-Time Log Monitoring  
- Watches multiple log files inside the `logs/` folder  
- Streams & processes new entries instantly  
- Extracts features for ML scoring  

###  2. Log Integrity using HMAC  
- Prevents tampering  
- Every log line is hashed using a secret key  
- Mirror files stored for verification  

###  3. Hybrid ML Anomaly Detection  
- **Isolation Forest (Light Model)** for quick scoring  
- **Autoencoder (Deep Model)** for structural anomalies  
- **Rule-Based system** for keyword spikes / brute force / bursts  
- **Fusion Engine** → Combines scores into final severity  
  - NORMAL  
  - WARNING  
  - CRITICAL  

###  4. SQLite Database  
Stores:
- Raw logs  
- HMAC values  
- ML scores  
- Anomaly history  

###  5. Tkinter UI Dashboard  
- Live log viewer  
- Color-coded severity indicators  
- Pop-up alerts for CRITICAL anomalies  
- Matplotlib-based charts  
- Exportable PDF/Text reports  

---

## Project Structure

project/
│
├── dataset/
│ ├── Thunderbird_2k.log_structured.csv
│ └── Thunderbird_2k.log_templates.csv
│
├── models/
│ ├── iso_model.pkl
│ ├── ae_model.h5
│ └── scaler.pkl
│
├── logs/
│ ├── app.log
│ ├── auth.log
│ └── system.log
│
├── mirrors/
├── reports/
│
├── src/
│ ├── watcher.py
│ ├── processor.py
│ ├── integrity.py
│ ├── db.py
│
│ ├── feature_extraction.py
│ ├── ml_engine.py
│ ├── rules.py
│ ├── trainer_iso_forest.py
│ ├── trainer_autoencoder.py
│
│ ├── ui.py
│ ├── charts.py
│ ├── report_generator.py
│ └── main.py
│
└── README.md

