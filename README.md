# 🚕 A-Hypothesis-Testing-Framework-for-Revenue-Maximization for NYC Yellow Taxi Trip Data — January 2020

An **interactive, analysis-ready README** for exploring New York City Yellow Taxi trips in **January 2020**, sourced from Kaggle.

🔗 **Dataset Link**: [https://www.kaggle.com/datasets/gauravpathak1789/yellow-tripdata-2020-01](https://www.kaggle.com/datasets/gauravpathak1789/yellow-tripdata-2020-01)

---

## 📌 Overview

This dataset captures **millions of real taxi trips** recorded by NYC Yellow Cabs during **January 2020**. Each row represents a completed trip and includes information about:

* Pickup & drop-off timestamps
* Trip distance and duration
* Fare details and surcharges
* Passenger count
* Payment type (cash / card)
* Location identifiers

It is widely used for **EDA, hypothesis testing, forecasting, optimization, and business analytics projects**.

---

## 🎯 Business & Analytics Use-Cases

You can use this dataset to answer questions such as:

* 💰 Do **card payments generate higher fares** than cash?
* ⏱️ How does **trip duration** affect fare amount?
* 🧍 How does **passenger count** influence revenue?
* 📍 Which pickup locations generate the most trips?
* 📊 Can we **optimize driver revenue** using behavioral insights?

This dataset is ideal for:

* Data Analytics portfolios
* Hypothesis Testing (A/B style analysis)
* Time Series & demand analysis
* BI dashboards (Tableau / Power BI)

---

## 🧾 Dataset Structure

Each row represents **one taxi trip**.

### 🔑 Key Columns

| Column Name             | Description                    |
| ----------------------- | ------------------------------ |
| `tpep_pickup_datetime`  | Trip pickup timestamp          |
| `tpep_dropoff_datetime` | Trip drop-off timestamp        |
| `passenger_count`       | Number of passengers           |
| `trip_distance`         | Distance traveled (miles)      |
| `fare_amount`           | Base fare                      |
| `extra`                 | Extra charges (e.g. rush hour) |
| `mta_tax`               | MTA tax                        |
| `tip_amount`            | Tip paid                       |
| `tolls_amount`          | Toll charges                   |
| `total_amount`          | Total trip cost                |
| `payment_type`          | Cash / Card                    |
| `PULocationID`          | Pickup zone ID                 |
| `DOLocationID`          | Drop-off zone ID               |

📌 *Location IDs can be mapped using NYC Taxi Zone lookup tables.*

---

## 🔄 Data Preparation Steps (Recommended)

Before analysis, perform the following:

* Remove trips with **zero or negative fare / distance**
* Filter unrealistic passenger counts (e.g. `> 5`)
* Convert datetime columns to proper `datetime` format
* Create derived features:

  * `trip_duration (minutes)`
  * `fare_per_mile`

---

## 🧠 Sample Analysis Ideas

### 1️⃣ Exploratory Data Analysis (EDA)

* Fare distribution
* Trip distance vs fare
* Peak pickup hours

### 2️⃣ Hypothesis Testing

**Question:** Does payment type affect fare amount?

* Null Hypothesis (H₀): No difference in average fare
* Alternative Hypothesis (H₁): Significant difference exists

Statistical tests:

* T-test / Mann–Whitney U

### 3️⃣ Revenue Optimization

* Identify high-value trips
* Analyze payment behavior
* Recommend incentives for higher-revenue payment types

---

## 📊 Visualization Ideas

You can build:

* 📈 Fare vs Trip Distance scatter plots
* 🥧 Payment type distribution pie charts
* 📉 Trip duration vs fare regression line
* 📊 Passenger count vs revenue bar charts

Works great with:

* Matplotlib / Seaborn
* Plotly
* Tableau / Power BI

---

## 🧪 Example Python Starter Code

```python
import pandas as pd

# Load dataset
df = pd.read_csv('yellow_tripdata_2020-01.csv')

# Convert datetime
df['tpep_pickup_datetime'] = pd.to_datetime(df['tpep_pickup_datetime'])
df['tpep_dropoff_datetime'] = pd.to_datetime(df['tpep_dropoff_datetime'])

# Create trip duration
df['trip_duration_min'] = (df['tpep_dropoff_datetime'] - df['tpep_pickup_datetime']).dt.total_seconds() / 60

# Basic filter
df = df[(df['fare_amount'] > 0) & (df['trip_distance'] > 0)]

print(df.head())
```

---

## 🚀 Ideal For

* 📁 Portfolio Projects
* 🧑‍🎓 Academic Assignments
* 🧠 Hypothesis Testing Case Studies
* 📊 Dashboard Storytelling
* 🏙️ Urban Mobility Analytics

---

## 📎 Data Source & Credits

* **Provider**: NYC Taxi & Limousine Commission (TLC)
* **Platform**: Kaggle
* **Dataset**: Yellow Taxi Trip Records — January 2020

---

## ⭐ Tip for Recruiters & Reviewers

This dataset demonstrates:

* Real-world data complexity
* Business-driven analytics
* Statistical thinking
* End-to-end data workflows

Perfect for showcasing **practical data analytics skills**.

---

Happy analyzing! 🚕📊
