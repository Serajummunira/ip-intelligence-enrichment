# ip-intelligence-enrichment
Automated Python solution to enrich IP addresses with ARIN RDAP ownership data and GeoIP location intelligence for cybersecurity investigations.
# IP Intelligence Enrichment Automation

## 📌 Project Overview
This project is an automated cybersecurity solution that enriches IP addresses with
network ownership and geographic intelligence.

The system reads IP addresses from an Excel file, queries ARIN RDAP for authoritative
network ownership data, enriches missing geographic information using a GeoIP service,
and outputs a fully processed CSV report.

This solution is useful for:
- SOC investigations
- Threat intelligence enrichment
- SIEM platforms (e.g., QRadar)
- Incident response documentation
- Cybersecurity audits

---

## 🔍 Data Sources Used

### 1. ARIN RDAP (Network Ownership)
Used to retrieve authoritative internet registry data:
- Organization name
- Net name
- Net handle
- IP range (start–end)
- Abuse contact emails
- Network roles

### 2. GeoIP Lookup (Location Intelligence)
Used to enrich geographic and ASN data not consistently available from ARIN:
- Country
- Region (State)
- City
- Latitude / Longitude
- ASN / ISP information

---

## ⚙️ How the System Works

1. IP addresses are provided in an Excel input file (`ips.xlsx`)
2. The Python script reads the IP list automatically
3. For each IP:
   - Queries ARIN RDAP API
   - Queries GeoIP API
   - Merges ownership and location data
4. Outputs a clean enriched CSV report (`ip_enriched_output.csv`)

---

## 📁 Repository Structure
ip-intelligence-enrichment/
│
├── ip_enrichment.py # Main automation script
├── ip_enrichment.ipynb # Google Colab notebook
├── ips.xlsx # Sample input IP list
├── ip_enriched_output.csv # Enriched output report
└── README.md
## 🛠️ Technologies Used
- Python
- Pandas
- Requests
- ARIN RDAP API
- GeoIP (IPinfo)
- Google Colab
