# ThreatFox API to MongoDB ETL Pipeline

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![MongoDB](https://img.shields.io/badge/MongoDB-5.0%2B-green)
![License](https://img.shields.io/badge/license-MIT-orange)

## Overview

Automated Python pipeline that:

- **Extracts** Indicators of Compromise (IOCs) from [ThreatFox API](https://threatfox.abuse.ch/export/json/recent/)
- **Transforms** data with:
  - Field validation (`ioc_value`, `ioc_type`, `malware`)
  - Confidence level normalization (0-100 scale)
  - Timestamp conversion (`first_seen_utc` → MongoDB ISODate)
- **Loads** into MongoDB with:
  - Upsert operations to prevent duplicates
  - Optimized indexes on `indicator` (unique), `ioc_type`, and `malware`

## 🛠️ Installation

```bash
# Clone repository
git clone https://github.com/your-repo/threatfox-etl.git
cd threatfox-etl

# Set up virtual environment
python -m venv venv
venv\Scripts\activate  # Windows
source venv/bin/activate  # Linux/Mac

# Install dependencies
pip install -r requirements.txt
```
