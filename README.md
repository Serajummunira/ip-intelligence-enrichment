# 🌐 IP Intelligence Enrichment Pipeline (Global RDAP + GeoIP)

This repository contains the Python-based IP enrichment pipeline developed for the research study:

**“Assessing the Reliability of Global IP Geolocation and Ownership Attribution Using RDAP and GeoIP”**

---

## 📌 Project Overview

This project implements an automated cybersecurity data enrichment pipeline that enhances IP address intelligence by combining:

- **Global RDAP (Registration Data Access Protocol)** for authoritative ownership data  
- **GeoIP (IPinfo API)** for geolocation context  

Unlike traditional approaches limited to a single registry, this pipeline uses **global RDAP bootstrapping**, enabling queries across all Regional Internet Registries (RIRs):

- ARIN (North America)  
- RIPE NCC (Europe)  
- APNIC (Asia-Pacific)  
- LACNIC (Latin America)  
- AFRINIC (Africa)  

---

## ⚙️ Key Features

- 🌍 Global RDAP bootstrapping (multi-registry support)
- 📍 GeoIP enrichment using IPinfo API
- 🧹 Data cleaning and preprocessing
- 🔄 Automated batch processing of large IP datasets
- 📊 Structured output for analysis (CSV format)

---

## 🧠 Use Cases

This pipeline is designed for:

- SOC investigations  
- Threat intelligence enrichment  
- SIEM platforms (e.g., QRadar)  
- Incident response analysis  
- Cybersecurity audits  

---

## 📊 Data Sources Used

### 1. Global RDAP (Ownership Intelligence)

Provides authoritative registry-based data:

- Organization name  
- ASN (Autonomous System Number)  
- Registry (RIR)  
- Network range  
- Abuse contact information  

---

### 2. GeoIP (Location Intelligence – IPinfo)

Provides estimated geographic data:

- Country  
- Region (State)  
- City  
- Latitude / Longitude  
- ISP / ASN (when available)

⚠️ Note: GeoIP data is **non-authoritative** and may contain missing or inaccurate values.

---

## 🔄 How the System Works

1. Input: IP addresses provided in an Excel/CSV file  
2. Pipeline processes each IP:
   - Performs **global RDAP lookup**
   - Performs **GeoIP enrichment (IPinfo API)**
*****Important Note:** API keys are not included in the repository for security reasons.
Users must provide their own API keys when running the notebook.
3. Merges ownership + geolocation data  
4. Outputs a clean enriched dataset (`.csv`)

---

## 📁 Repository Structure
ip-intelligence-enrichment/
│── ip_enrichment_pipeline_rdap_geoip.ipynb # Main Colab pipeline
│── ip_enrichment.py # Python script version
│── ips.xlsx # Sample input dataset
│── ip_enriched_output.csv # Example output
│── README.md
## 🛠 Technologies Used

- Python  
- Pandas  
- NumPy  
- Requests  
- Matplotlib  
- RDAP (via ipwhois / HTTP queries)  
- IPinfo API (GeoIP)  
- Google Colab  

---

## 🔐 Setup Instructions

To run this pipeline:

1. Clone the repository  
2. Install dependencies:
   ```bash
   pip install pandas requests ipwhois

**Set your API key:

export IPINFO_TOKEN="your_api_key"
**Run the notebook or script

📄 Research Context
This pipeline was developed as part of a research study evaluating the reliability of IP geolocation vs. ownership attribution in cybersecurity investigations.

Key findings:
-RDAP provides highly reliable ownership data
-GeoIP shows high missing values and inconsistencies
-Multi-source enrichment improves analysis accuracy
📂 Data Availability
Dataset source: https://www.abuseipdb.com
Code available in this repository
⚠️ Disclaimer
-This project is intended for educational and research purposes only.
-API usage must comply with respective service terms.

👩‍💻 Author
Serajum Munira
MS in Information Quality (Cybersecurity & Data Science)
