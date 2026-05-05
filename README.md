#  Performance Testing Project - Load Test

A professional Load Testing project built with **Apache JMeter** to measure the performance of a real REST API under concurrent user load.

---

##  Project Overview

This project simulates **100 concurrent users** hitting a real API to validate system performance under normal daily traffic conditions.

| Property | Value |
|----------|-------|
| **Tool** | Apache JMeter 5.6.3 |
| **Target** | httpbin.org (Professional HTTP Testing API) |
| **Test Type** | Load Test |
| **Virtual Users** | 100 |
| **Ramp-up Period** | 5 minutes |
| **Think Time** | 1-3 seconds (realistic user behavior) |

---

##  Why httpbin.org?

httpbin.org is a free, public HTTP testing service used by QA engineers and developers worldwide. It supports all HTTP methods (GET, POST, PUT, DELETE) and is designed specifically for performance testing.

---

##  Project Structure
performance-testing-project/
│
├── 📂 Test_plan/
│   └── 01_load_test.jmx     ← JMeter test plan (open this in JMeter)
│
├── 📂 Results/
│   └── load_results.jtl     ← Raw test results data
│
└── 📂 Reports/
└── load_report/
└── index.html       ← Open this in browser to see dashboard
---

##  Test Scenarios

Each virtual user simulates a real user performing these actions:

| # | Request Name | Method | Path | Simulates |
|---|-------------|--------|------|-----------|
| 1 | GET - All Posts | GET | /get | User opens homepage feed |
| 2 | GET - Single Post | GET | /get | User clicks on a post |
| 3 | GET - Post Comments | GET | /get | User reads comments |
| 4 | GET - All Users | GET | /get | User browses user list |
| 5 | POST - Create New Post | POST | /post | User writes a new post |
| 6 | PUT - Update Post | PUT | /put | User edits their post |
| 7 | DELETE - Remove Post | DELETE | /delete | User deletes their post |

---

##  Performance Thresholds (SLAs)

| Metric | Target |
|--------|--------|
| Response Time | Under 3,000ms |
| Error Rate | 0% |
| Throughput | Stable throughout test |

---

##  Prerequisites

| Tool | Version | Download |
|------|---------|----------|
| Java | 11+ | https://adoptium.net |
| Apache JMeter | 5.6+ | https://jmeter.apache.org |

---

##  How to Run

**Step 1 - Open PowerShell and navigate to JMeter:**
```powershell
cd "C:\path\to\apache-jmeter\bin"
```

**Step 2 - Run the Load Test:**
```powershell
.\jmeter -n -t "path\to\Test_plan\01_load_test.jmx" -l "path\to\Results\load_results.jtl" -e -o "path\to\Reports\load_report"
```

**Step 3 - Open the HTML Report:**
---

## How to Read the Results

After running the test, open the HTML dashboard and look for:

| Metric | Healthy Value | What it means |
|--------|--------------|---------------|
| APDEX Score | 1.0 | Perfect performance |
| Error % | 0% | No failed requests |
| Average Response | Under 2000ms | Fast response |
| Throughput | Stable | Server handles load |
| 90th Percentile | Under 3000ms | 90% of users happy |

---

##  JMeter Configuration

### Thread Group Settings
- **Number of Threads:** 100 (virtual users)
- **Ramp-up Period:** 300 seconds (5 minutes)
- **Loop Count:** 5 (each user repeats 5 times)
- **On Error:** Continue

### HTTP Request Defaults
- **Protocol:** http
- **Server:** httpbin.org
- **Port:** 80

### Think Time
- **Min:** 1 second
- **Max:** 3 seconds
- Simulates real user reading/thinking time

---

## Test Results Summary

| Metric | Result |
|--------|--------|
| Total Requests | 3,500 |
| Error Rate | 0.23% |
| Average Response | 210ms |
| Min Response | 134ms |
| Throughput | 8.7 req/sec |

---

##  Author

**Nagwa Mahmoud** — QA Engineer
- Performance Testing using Apache JMeter
- Load Testing A
