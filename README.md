# BOLT



---

## Introduction

**BOLT (Billing Overload and Load Tracking)** is a predictive analytics project designed to address the common issue of unexpectedly high electricity bills despite stable consumption patterns. The idea originated from real-world observations where electricity bills increased significantly without noticeable changes in usage behavior.

To address this problem, BOLT leverages machine learning and deep learning techniques to forecast electricity consumption and identify anomalies in billing patterns. By comparing predicted consumption with actual readings, the system helps detect unusual deviations that may indicate billing errors or abnormal usage.

The objective of this project is to enable users to identify discrepancies early and take appropriate action by contacting utility providers or relevant authorities, while also promoting better energy awareness and consumption management.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Models Used](#models-used)
- [Evaluation Metrics](#evaluation-metrics)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

This project focuses on predicting electricity meter readings using time-series analysis. Multiple models are implemented and compared to evaluate forecasting performance and reliability. The system captures seasonal trends, consumption patterns, and abnormal variations in usage data.

By integrating forecasting with anomaly detection, BOLT provides insights that can assist in monitoring energy consumption and identifying unexpected billing behavior.

---

## Dataset

The dataset contains the following attributes:

- **building_id**: Unique identifier for each building  
- **meter**: Type of meter (only electricity meter data with `meter = 0` is used)  
- **timestamp**: Date and time of the meter reading  
- **meter_reading**: Recorded electricity consumption  

### Data Preprocessing Steps
1. Filter electricity meter readings (`meter = 0`).
2. Convert meter readings into kWh using a conversion factor of 0.2931.
3. Split the dataset into training and testing sets using an 80–20 ratio.

---

## Project Workflow

1. **Data Filtering and Conversion**  
   Filtered electricity data is stored in `filtered_electricity_data.csv`. Data for building 779 is further processed and saved as `filtered_electricity779_data.csv`, followed by conversion to kWh in `building_779_updated_meter_reading.csv`.

2. **Data Visualization**  
   Statistical summaries and visualizations are used to analyze data distribution and consumption patterns.

3. **Model Development**
   - **ARIMA** for traditional time-series forecasting.
   - **Random Forest** for regression-based prediction.
   - **GRU** for sequential learning.
   - **LSTM** for capturing long-term temporal dependencies.
   - **Hybrid LSTM–GRU Model** as the final forecasting model, combining the long-term memory capability of LSTM with the efficiency of GRU.
     The hybrid architecture captures both long-term consumption trends and short-term fluctuations, resulting in improved prediction stability and more reliable anomaly detection.

4. **Model Evaluation**  
   Predictions are compared against actual readings using standard evaluation metrics.

5. **Anomaly Detection**  
   Anomalies are identified by analyzing deviations between predicted and actual consumption values.

---

## Models Used

- **ARIMA**  
  A classical statistical model effective for trend and seasonal forecasting.

- **Random Forest**  
  An ensemble learning method that improves prediction accuracy through multiple decision trees.

- **GRU (Gated Recurrent Unit)**  
  A recurrent neural network architecture designed for efficient sequence learning.

- **LSTM (Long Short-Term Memory)**  
  A deep learning model capable of learning long-term dependencies in time-series data.

- **Hybrid LSTM–GRU Model**  
  The hybrid LSTM–GRU model is used as the final forecasting model in BOLT, combining LSTM’s long-term memory capability with GRU’s computational efficiency to capture both long-term patterns and short-term fluctuations, improving prediction accuracy and anomaly detection reliability.


---

## Evaluation Metrics

Model performance is evaluated using:

- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **Mean Absolute Percentage Error (MAPE)**

---

### Usage
#### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/electricity-meter-reading-prediction.git
cd electricity-meter-reading-prediction
```
#### 2. Install Dependencies
Install required Python libraries:
```bash
pip install -r requirements.txt
```
### 3. Run Data Preprocessing and Modeling

Follow the provided scripts to:

1. Filter and preprocess the dataset.
2. Train ARIMA, Random Forest, GRU, and LSTM models.
3. Generate predictions and save results.

### 4. Evaluate Model Performance
Review evaluation metrics to compare model performance.

### 5. Anomaly Detection
Run the anomaly detection step to identify significant deviations from predicted consumption.

---

## Results

#### 1. Actual Data Analysis After Pre-Processing:
![Actual Data Analysis](https://github.com/user-attachments/assets/de027553-a4c3-4f08-b642-d585b8ddc016)

#### 2. Raw Data Plot for 779 Building Id:
![Actual Data Plot](https://github.com/user-attachments/assets/3dc82eb6-c8b4-426a-a5e8-f99b0f3cdfe8)

#### 3. GRU Prediction:
![GRU Prediction](https://github.com/user-attachments/assets/369db538-fb67-47ee-a3e6-2db3461c6fed)

#### 4. LSTM Prediction:
![LSTM Prediction](https://github.com/user-attachments/assets/c6608c1a-5710-4179-b0bd-68cea1ff0a35)

#### 5. Anomaly Detection:
![Anomaly Detection](https://github.com/user-attachments/assets/1f580958-051d-425c-b120-cbcc3437ffaf)

Results are saved in CSV files, plots, and evaluation outputs. Comparative performance metrics for ARIMA, Random Forest, GRU, and LSTM models demonstrate the effectiveness of deep learning approaches in electricity consumption forecasting. The anomaly detection component highlights unusual consumption behavior that may indicate billing discrepancies or abnormal usage patterns.

---


## Why This Project Matters

Electricity billing discrepancies and unexpected spikes in energy costs are common problems faced by households and organizations. In many cases, users lack the technical tools to verify whether an increase in billing is due to genuine consumption changes or potential errors in measurement or billing systems.

BOLT addresses this problem by combining time-series forecasting with anomaly detection to create a data-driven approach for monitoring electricity consumption. Instead of relying solely on historical averages or manual inspection, the system predicts expected consumption patterns and identifies deviations automatically.

This project is important because it demonstrates:

- **Real-world problem solving** using AI and machine learning.
- **Application of time-series forecasting** in energy analytics and sustainability.
- **Integration of classical and deep learning models** for comparative analysis.
- **Practical anomaly detection**, which can support early identification of billing issues or abnormal energy usage.
- **Scalability potential**, where similar systems can be extended to smart grids, IoT-based monitoring, and energy optimization platforms.

By bridging predictive analytics with real-world usability, BOLT highlights how AI can be applied beyond academic experimentation to deliver meaningful and actionable insights.
------
## Contributing

Contributions are welcome. Please fork the repository and submit a pull request for improvements or feature additions.

---

## License

This project is licensed under the MIT License.

---

