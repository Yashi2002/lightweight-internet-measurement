# Lightweight Internet Access Measurement Prototype

This project is a small, exploratory prototype for measuring **basic Internet performance** using simple, lightweight techniques.  
It focuses on measuring **HTTP latency** and **DNS resolution latency** for commonly used web services, as a way to understand real-world connectivity quality.

The project was implemented in **Google Colab** using Python and is intended as an early step toward more comprehensive Internet measurement and analysis.

---

## Motivation

Reliable Internet access is essential for participation in education, work, and public services.  
However, connectivity quality can vary significantly depending on location, infrastructure, and network conditions.

This prototype explores how **simple measurements**, such as HTTP response time and DNS lookup time, can provide useful signals about network performance without requiring specialized hardware or privileged access.

---

## What This Project Does

For a small set of well-known web services (Google, Cloudflare, Wikipedia), the notebook:

- Sends multiple HTTP requests to measure **HTTP latency**
- Performs DNS lookups to measure **DNS resolution latency**
- Repeats measurements multiple times to reduce noise
- Aggregates results into a structured table
- Computes **average latencies per service** for comparison

---

## Technologies Used

- **Python**
- **Google Colab**
- `requests` – for HTTP requests
- `dnspython` – for DNS resolution
- `pandas` – for data organization and analysis

---

## Methodology Overview

1. Select a set of target web services.
2. For each service:
   - Measure HTTP response time using repeated GET requests.
   - Measure DNS resolution time using repeated DNS queries.
3. Store individual measurements in a pandas DataFrame.
4. Compute average HTTP and DNS latencies per service.

This approach keeps the measurement process lightweight, reproducible, and easy to extend.

---

## Results (Example)

The analysis shows that:
- DNS resolution times are generally very small compared to HTTP response times.
- HTTP latency varies more significantly across services, likely due to factors such as server location, routing paths, and network conditions.

These results highlight how different components of a web request contribute differently to overall perceived performance.

---

## Limitations

- Measurements are taken from a single environment (Google Colab).
- Results may vary depending on time, location, and network conditions.
- The project does not yet account for packet loss, throughput, or jitter.

---

## Future Work

Possible extensions include:
- Running measurements from multiple geographic locations
- Increasing the number of trials and services
- Adding additional metrics such as packet loss or throughput
- Exploring relationships between network performance and user experience

---

## Purpose

This project is intended as a **learning and exploration exercise** in Internet measurement and network performance analysis, with potential relevance to research on connectivity quality and digital inclusion.
