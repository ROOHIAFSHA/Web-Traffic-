# Web-Traffic-
# Web Traffic Anomaly Detection using AWS CloudWatch Logs

## 📌 Project Overview

This project leverages a dataset of web traffic logs collected via AWS CloudWatch to **detect suspicious or potentially harmful activities**. The main goal is to analyze patterns in network traffic using machine learning techniques and visualize anomalies to aid cybersecurity decision-making.

---

## 📂 Dataset Description

**Source**: AWS CloudWatch  
**Total Records**: ~X (update after checking)

Each row in the dataset represents a stream of traffic to a production web server.  
The dataset includes the following columns:

- `bytes_in`: Bytes received by the server.
- `bytes_out`: Bytes sent from the server.
- `creation_time`: Record creation timestamp.
- `end_time`: Connection end timestamp.
- `src_ip`: Source IP address.
- `src_ip_country_code`: Country code of source IP.
- `protocol`: Protocol used (e.g., HTTP, TCP).
- `response.code`: HTTP response code.
- `dst_port`: Destination port on server.
- `dst_ip`: Server IP address.
- `rule_names`: Detection rules triggered.
- `observation_name`: Observations made.
- `source.meta`: Metadata for the source.
- `source.name`: Name of the traffic source.
- `time`: Event timestamp.
- `detection_types`: Detection method used.

---

## 🧠 Approach

1. **Data Preprocessing**:
   - Handled missing values.
   - Converted relevant timestamps.
   - Selected numeric features for modeling (`bytes_in`, `bytes_out`, etc.).

2. **Anomaly Detection**:
   - Used **Isolation Forest** to detect suspicious traffic.
   - Added a new column `anomaly`:
     - `1`: Normal traffic
     - `-1`: Suspicious traffic

3. **Visualization**:
   - Countplot of Normal vs Suspicious traffic.
   - Optional: Further plots like `bytes_in` vs `anomaly`, country-wise traffic analysis, etc.

---

## 📊 Visualizations

- **Normal vs Suspicious Traffic**  
  ![anomaly-graph](assets/anomaly_bar_chart.png)

> More visualizations can be added as needed.

---

## 🚀 Technologies Used

- Python
- Pandas
- Seaborn & Matplotlib
- Scikit-learn (Isolation Forest)

---

## 📌 How to Run

1. Clone the repository or download the notebook.
2. Install the requirements:
   ```bash
   pip install pandas matplotlib seaborn scikit-learn
