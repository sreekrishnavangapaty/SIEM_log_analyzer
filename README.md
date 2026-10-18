# SIEM Security Log Analyzer

**Turning raw security logs into actionable security insights.**

A Python-based Security Information and Event Management (SIEM) application that analyzes system logs, detects suspicious activities, and centralizes security alerts through an interactive Security Operations Center (SOC) dashboard.

## Features

- **Log Analysis** — Parse Linux authentication logs, Linux system logs, and Windows Security Event Logs.
- **Threat Detection** — Identify brute-force attempts, account enumeration, suspicious login sequences, and privilege escalation patterns.
- **Alert Management** — Generate severity-based alerts, deduplicate recurring detections, and track investigation status.
- **Security Analytics** — Visualize event distributions, authentication trends, suspicious IP addresses, and detection patterns.
- **SOC Dashboard** — Explore security events, investigate alerts, review detection rules, and monitor system activity.
- **Reporting** — Export security events and alerts as CSV files.
- **Data Persistence** — Store events and alerts in an SQLite database.

## Technology Stack

Python · Streamlit · Pandas · Matplotlib · SQLite · Pytest

## Architecture

```text
Security Logs
     ↓
Log Parsing & Normalization
     ↓
Threat Detection & Correlation
     ↓
Alert Management
     ↓
SQLite Database
     ↓
Analytics & SOC Dashboard
```

## Setup

**Prerequisites:** Python 3.10+ and Git.

**1. Clone the repository**

```bash
git clone https://github.com/YOUR-USERNAME/SIEM-Security-Log-Analyzer.git
cd SIEM-Security-Log-Analyzer
```

Replace the repository URL with your actual GitHub URL.

**2. Create a virtual environment**

```bash
python -m venv venv
```

Activate it on Windows:

```powershell
.\venv\Scripts\Activate.ps1
```

On Linux/macOS:

```bash
source venv/bin/activate
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

**4. Configure environment variables (optional)**

Create a `.env` file from the example configuration if you need to customize the settings.

Windows PowerShell:

```powershell
Copy-Item .env.example .env
```

Linux/macOS:

```bash
cp .env.example .env
```

## Usage

**Launch the dashboard**

```bash
streamlit run dashboard/app.py
```

Open `http://localhost:8501` in your browser.

**Analyze security logs**

1. Open the **Log Ingestion** section.
2. Upload supported Linux or Windows security log files, or generate a demo scenario.
3. Review detected events and generated alerts.
4. Explore the **Security Events**, **Security Alerts**, and **Threat Analysis** sections.
5. Investigate alerts, update their status, and export reports from the **Reports** section.

**Run tests**

```bash
pytest
```

## Objective

Demonstrate core SIEM workflows, from log ingestion and event normalization to rule-based threat detection, alert investigation, and security analytics.

## Security Note

This project is intended for educational and authorized security monitoring. Detection results depend on available log data and configured rules.

