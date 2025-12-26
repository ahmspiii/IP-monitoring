# IP-monitoring


# Workflow Automation System

This project implements two automated workflows for security monitoring and alerting. The system is designed to handle real-time webhook events and scheduled weekly checks.

## Workflow 1: Real-time Security Monitoring (Webhook Triggered)

### Overview
This workflow is triggered by incoming webhook events and performs real-time security analysis.

### Flow
1. **Webhook Trigger**
   - Receives incoming data/events from external sources
   - Acts as the entry point for real-time monitoring

2. **Security Checks (Parallel Processing)**
   - **VirusTotal Check**
     - Scans files/URLs for malware and security threats
   - **IP Analysis**
     - `ip_geo`: Performs geolocation lookup
     - `abuse db`: Checks against abuse databases (abuseipdb.com)
     - `ip-api.com`: Gathers additional IP information

3. **Data Processing**
   - JavaScript code processes and aggregates results from IP analysis
   - Combines data from all security checks

4. **AI Analysis**
   - Uses Google Gemini Chat Model for intelligent analysis
   - Applies Simple Memory for context awareness
   - Makes decisions based on the collected data

5. **Alerting**
   - Sends notifications based on analysis results
   - Can integrate with various messaging platforms

## Workflow 2: Weekly SSL Certificate Monitoring (Scheduled)

### Overview
This workflow runs on a weekly schedule to monitor SSL certificate expiration.

### Flow
1. **Weekly Trigger**
   - Scheduled to run automatically every week
   - Ensures regular monitoring of SSL certificates

2. **Data Collection**
   - Fetches list of URLs to monitor from a spreadsheet
   - Maintains an up-to-date list of endpoints

3. **SSL Certificate Check**
   - Verifies SSL certificate status for each URL
   - Checks certificate expiration dates
   - Validates certificate chains

4. **Data Management**
   - Updates the monitoring spreadsheet with latest status
   - Maintains historical data for trend analysis

5. **Alert System**
   - **Expiry Alert**
     - Conditionally triggers based on certificate status
     - Sends email alerts for certificates nearing expiration
   - **False**
     - No action taken if certificates are valid



### Prerequisites
- Node.js (for JavaScript processing)
- API keys for:
  - VirusTotal
  - ip2location.io
  - abuseipdb.com
  - ip-api.com
  - Google Gemini API


## Usage
- The webhook workflow runs automatically on incoming events
- The SSL monitoring runs weekly by default (configurable)
- Check logs for monitoring and debugging.


