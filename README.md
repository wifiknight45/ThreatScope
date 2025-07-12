
  **ThreatScope = SOC Dashboard - Real-Time Security Analytics** script

**Please note that ThreatScope is currently under development for enhanced security + improved error handling
+ scalability with integration of the open source Wazuh SIEM.**

  ## Overview
This Python application provides **real-time security event monitoring** using **Dash**, **Flask**, and **machine learning-based anomaly detection**. It fetches logs from a **Wazuh SIEM**, analyzes security events for anomalies, and visualizes them in an interactive web-based dashboard.

## Features
✅ **Real-Time Log Updates** – Fetches security logs dynamically from Wazuh SIEM.  
✅ **Anomaly Detection** – Uses `IsolationForest` for identifying unusual security events.  
✅ **Time-Series Analysis** – Leverages `seasonal_decompose` for trend and seasonality insights.  
✅ **Multi-threading for Efficiency** – Ensures seamless background log updates.  
✅ **Secure API Requests** – Implements HTTPS security and request error handling.  
✅ **Export Functionality** – Supports exporting logs as CSV or TXT files.  
✅ **Scalable & Configurable** – Adjustable log refresh rate and enhanced thread safety.

==================================================================================================================


RECENT DEVELOPMENTS/UPDATES:
## v2 is now live!
key updates:
Exception Handling - protects against request failures and network errors.
Thread Safety - prevents race conditions when updating security logs
Improved Scalability - dynamic contamination level adjustment ensures better anomaly detection for varying data sizes. 
Enhanced Logging - provides better visibility into runtime operations. 
Code Modularity - functions are now structured for easier maintenance.
Configurable Update Frequence - allows users to control the log refresh rate. 
V2 is more secure, scalable and efficient. 

# ThreatScope version 1 is now live
This Automated SOC Dashboard Generator is a real-time security analytics tool that fetches logs from open-source SIEM solutions, applies machine learning for anomaly detection, implements role-based access control, and allows exporting security logs for further analysis.

## Installation
Ensure you have Python **3.8 or later** installed. Then, clone this repository and install dependencies:

```bash
git clone https://github.com/wifiknight45/ThreatScope.git
cd ThreatScope

pip install -r requirements.txt
```

## Dependencies
This project requires the following Python packages:
```bash
pandas
plotly
dash
flask
requests
sklearn
statsmodels
threading
logging
```

Install them using:
```bash
pip install pandas plotly dash flask requests scikit-learn statsmodels
```

## Configuration
Modify the **Wazuh API URL** and **Authentication Token** in `fetch_security_logs()`:

```python
wazuh_api = "https://YOUR_WAZUH_MANAGER:55000/security/events"
headers = {"Authorization": "Bearer YOUR_API_KEY"}
```

You can also adjust the log **update frequency**:
```python
update_logs(interval=30)  # Updates every 30 seconds
```

## Running the Application
Execute the script using:
```bash
python app.py
```
Then, open your browser and go to:
```
http://127.0.0.1:8050
```

## Exporting Logs
To export security logs:
- **CSV Format**: `http://127.0.0.1:8050/export/csv`
- **TXT Format**: `http://127.0.0.1:8050/export/txt`

## Security Considerations
⚠ **DO NOT hardcode API credentials** in the script. Use environment variables.  
⚠ **Enable HTTPS verification** to prevent man-in-the-middle attacks.  
⚠ **Run behind a secure firewall** when deploying publicly.  

## Contributing
Feel free to submit **pull requests** or report issues. We welcome improvements and feedback! 🚀

## License
📜 This project is licensed under the **MIT License** – feel free to modify and distribute.

---




