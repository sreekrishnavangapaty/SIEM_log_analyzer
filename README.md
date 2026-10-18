# 🛡️ SIEM Security Log Analyzer

A Python-based **Security Information and Event Management (SIEM)** system designed to analyze security logs, detect suspicious activities, correlate attack patterns, and manage security alerts through a dark-themed Security Operations Center (SOC) dashboard.

The project simulates essential SIEM capabilities by combining log ingestion, event normalization, rule-based threat detection, alert management, persistent storage, and security analytics in one application.

## 🚀 Key Features

### 📥 1. Multi-Source Log Analysis
- Parse Linux authentication logs, including SSH login attempts and privilege-related events.
- Analyze Linux system logs for service activity and suspicious events.
- Process Windows Security Event Logs exported in CSV format.
- Upload log files or generate sample security scenarios for demonstration.

### 🔍 2. Threat Detection Engine
Detect suspicious authentication and privilege-related activity using configurable detection rules.

| Detection Rule | Description | Default Threshold |
|---|---|---|
| Brute Force Detection | Identifies repeated failed login attempts from a source IP | 5 failures within 5 minutes |
| Account Enumeration | Detects attempts against multiple usernames | 3 unique usernames within 5 minutes |
| Suspicious Login Sequence | Detects repeated failures followed by a successful login | 3 preceding consecutive failures |
| Privilege Escalation Monitoring | Flags privilege changes associated with prior failed authentication activity | 10-minute correlation window |

### 🚨 3. Alert Management
- Generate alerts with severity levels: Low, Medium, High, and Critical.
- Reduce duplicate alerts by tracking recurring detections.
- Track alert status through New, Investigating, Resolved, and False Positive.
- Display supporting evidence and contributing events to assist investigation.

### 📊 4. Interactive SOC Dashboard
Built using Streamlit, the dashboard provides:

- Security overview with event and alert metrics.
- Searchable and filterable security events.
- Alert investigation with evidence and event timelines.
- Threat analysis charts using Matplotlib.
- Detection rule and threshold information.
- Log ingestion and demo scenario generation.
- CSV exports and security summary reports.
- Configurable detection thresholds and time windows.

### 🗄️ 5. Data Storage and Analytics
- Store security events and alerts in SQLite.
- Query persisted data for dashboard metrics and analysis.
- Analyze event distributions, authentication outcomes, suspicious source IPs, and detection trends.
- Preserve alert status updates between application sessions.

## 🧰 Technology Stack

- **Language:** Python
- **Dashboard:** Streamlit
- **Data Analysis:** Pandas
- **Visualization:** Matplotlib
- **Database:** SQLite
- **Configuration:** Python dotenv
- **Testing:** Pytest
- **Version Control:** Git and GitHub

## 🏗️ Architecture

The application follows a modular security-monitoring pipeline:

```text
Security Log Files
        |
        v
    Log Reader
        |
        v
  Source-Specific Parsers
        |
        v
 Event Normalization
        |
        v
 Threat Detection Engine
        |
        v
 Alert Management
        |
        v
   SQLite Database
        |
        v
 Analytics and Statistics
        |
        v
  Streamlit SOC Dashboard
        |
        v
 Investigation and Reports
```

## 📂 Project Structure

```text
SIEM-Security-Log-Analyzer/
├── app/
│   ├── alerts/          # Alert creation and deduplication
│   ├── analytics/       # Security statistics and trends
│   ├── database/        # SQLite models and repository
│   ├── detection/       # Detection rules and correlation
│   ├── ingestion/       # Log reading and ingestion
│   ├── parsers/         # Linux and Windows log parsers
│   ├── schemas/         # Event and alert schemas
│   ├── normalization/   # Event normalization utilities
│   ├── utils/           # Logging and helper functions
│   ├── config.py        # Application configuration
│   └── sample_generator.py
├── dashboard/
│   └── app.py           # Streamlit SOC dashboard
├── data/                # Local database and sample data
├── docs/
│   ├── ARCHITECTURE.md
│   ├── DETECTION_RULES.md
│   └── INTERVIEW_GUIDE.md
├── scripts/             # Sample log generation scripts
├── tests/               # Automated tests
├── .env.example
├── .gitignore
├── requirements.txt
└── README.md
```

## ⚙️ Installation and Setup

### Prerequisites

- Python 3.10 or later
- pip
- Git

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/SIEM-Security-Log-Analyzer.git
cd SIEM-Security-Log-Analyzer
```

Replace `YOUR-USERNAME` with your GitHub username and use your actual repository URL.

### 2. Create a virtual environment

**Windows PowerShell:**

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

**Linux/macOS:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure the environment

If customization is needed, copy the example configuration:

```powershell
# Windows PowerShell
Copy-Item .env.example .env
```

```bash
# Linux/macOS
cp .env.example .env
```

Review `.env.example` and configure the supported settings as needed.

### 5. Run the application

```bash
streamlit run dashboard/app.py
```

Open the local URL displayed in the terminal, usually:

```text
http://localhost:8501
```

Use the dashboard's demo scenario generator to explore the detection pipeline without requiring a live security monitoring environment.

## 🧪 Running Tests

Run the automated test suite from the project root:

```bash
pytest
```

The test suite covers areas such as log parsing, event normalization, detection logic, alert handling, and database operations.

## 📈 Example Use Cases

- Learning how SIEM platforms process security logs.
- Demonstrating rule-based threat detection and event correlation.
- Exploring suspicious authentication patterns.
- Practicing alert investigation and incident triage.
- Visualizing security events and exporting analysis reports.
- Building a foundation for further cybersecurity projects.

## 🔮 Future Enhancements

- Live log streaming and continuous monitoring.
- Integration with additional log sources and security platforms.
- Threat intelligence enrichment for suspicious IP addresses.
- Advanced correlation rules and anomaly detection.
- Role-based access control and authentication.
- Docker-based deployment and automated CI testing.

## 🔐 Security and Limitations

This project is an educational SIEM prototype. Its detections are rule-based and depend on the available log data and configured thresholds. It is not a replacement for a production SIEM or a guarantee of threat detection.

Use synthetic logs or authorized security data when testing. Review sensitive log data before uploading or sharing it.

## 👩‍💻 Author

**Sathwika Mamidipalli**

B.Tech Computer Science and Engineering — Cyber Security

Interested in cybersecurity, security monitoring, threat detection, and practical security engineering.

---

⭐ If you find this project useful, consider starring the repository!
