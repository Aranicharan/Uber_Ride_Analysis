# 🛺 Uber Ride Analysis

## 📘 Overview
This project focuses on analyzing Uber ride data to uncover key insights about trip patterns, cancellations, delays, and weather impacts.  
The goal is to understand operational trends, identify areas for improvement, and visualize how external factors influence trip completion rates.

---

## 🎯 Objectives
- Analyze trip completion and cancellation rates.
- Identify when and why rides are most frequently cancelled.
- Explore relationships between ride delays, weather, and trip status.
- Derive actionable insights to improve efficiency and user satisfaction.

---

## 🧩 Dataset Description
The dataset contains information on Uber ride requests, including timestamps, trip status, and weather conditions.

| Column | Description |
|--------|-------------|
| `request_id` | Unique ID for each ride request |
| `driver_id` | ID of the driver assigned to the trip |
| `trip_status` | Final status of the ride (Trip Completed, Cancelled by Driver, Cancelled by User) |
| `request_day` / `request_hour` | Day and hour of the ride request |
| `start_day` / `start_hour` | Day and hour when the trip started |
| `drop_day` / `drop_hour` | Day and hour when the trip ended |
| `trip_cost` | Total fare of the trip |
| `ride_delay` | Delay between request and trip start |
| `weather` | Weather conditions during the ride |
| `cancellation_reason` | Reason for ride cancellation |

---

## 🧠 Steps Performed
1. **Data Loading & Inspection**
   - Loaded dataset using pandas
   - Checked for missing values and inconsistent data

2. **Data Cleaning**
   - Removed rows with missing timestamps
   - Handled nulls in `trip_cost`, `start_timestamp`, and `drop_timestamp`
   - Standardized column names and formatted timestamps

3. **Exploratory Data Analysis (EDA)**
   - Distribution of trip statuses
   - Ride cancellations by day and hour
   - Impact of weather on cancellations
   - Frequency of trip delays

4. **Visualization**
   - Bar charts and histograms using Matplotlib and Seaborn
   - Pie chart of cancellation reasons
   - Correlation heatmap for numerical features

5. **Insights**
   - Most cancellations occur during morning rush hours.
   - Rainy weather increases cancellation rates significantly.
   - Delays are higher during weekends and peak hours.

---

## 📊 Tools and Libraries
- **Python 3.x**
- **Pandas** – Data manipulation
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **NumPy** – Numerical operations

---

## 🧾 Sample Code Snippet
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_csv("uber_rides.csv")

# Check data overview
print(df.head())

# Trip status distribution
sns.countplot(x="trip_status", data=df)
plt.title("Trip Status Distribution")
plt.show()
