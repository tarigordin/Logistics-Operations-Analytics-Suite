# 🚚 Logistics & Fleet Operations Analytics Suite

An end-to-end executive Business Intelligence solution built in Power BI to monitor freight financials, driver efficiency, route profitability, and SLA fulfillment across modern supply chain networks.

![Logistics Operations Analytics Suite](OSORU TARIMOBOERE GORDIN CAPSTONE PROJECT.png)

---

## 📌 Executive Summary

Modern logistics operations require real-time visibility across disjointed cost centers—spanning fuel consumption, fleet maintenance, driver retention, and customer SLA compliance. 

This project integrates disparate transactional logistics datasets into a relational star-schema model to deliver a **4-part executive dashboard suite** configured with custom container UI architecture and robust DAX calculations.

---

## 🏗️ Architecture & Core Dashboards

The suite is engineered into four synchronized operational modules:

### 1. Financial Overview
* **Focus:** Profitability margins, cost breakdown, and customer value distribution.
* **Key Visuals:** Revenue vs. Expenses monthly trend, Top 5 Profitable Routes, Top 5 Customers by Revenue & Margin, and Executive Narrative Takeaways.
* **Core Metrics:** Total Revenue, Net Profit, Profit Margin (%), Total Dispatched Loads, and Baseline On-Time Delivery Rate.

### 2. Fleet & Driver Performance
* **Focus:** Asset utilization, preventative maintenance overhead, and safety incident tracking.
* **Key Visuals:** Driver Performance Matrix, Maintenance Expense Breakdown (Parts vs. Labor), Delivery Status by Fuel Type, and Safety Incident Count.
* **Core Metrics:** Total Active Drivers, Total Fleet Mileage, Total Incidents, and Total Maintenance Cost.

### 3. Route Analytics
* **Focus:** Transit bottlenecks, route cost per mile, and origin-destination efficiency.
* **Key Visuals:** Top 5 Routes by Revenue & Cost, Cost Efficiency Scatter Analysis, Transit vs. Idle Time by Origin, and City-Level Yield Summaries.
* **Core Metrics:** Total Active Routes, Average Transit Duration (hrs), Average Trip Duration (hrs), Cost Per Mile ($), and Total Route Revenue.

### 4. Delivery Performance & SLA Tracking
* **Focus:** Contractual compliance, customer dwell times, and facility detention.
* **Key Visuals:** Delivery Volume & On-Time SLA Trend (evaluated against a dynamic 95% target threshold), Top 5 Delay Bottlenecks by City, Facility SLA Compliance & Dwell Summary Matrix, and Top 5 Drivers by On-Time Rate.
* **Core Metrics:** Total Delivery Events, On-Time Delivery Rate (OTD %), Delayed Deliveries, Total Detention Hours, and Average Detention Minutes per Stop.

---

## 📊 Data Modeling & Methodology

* **Schema Architecture:** Star schema establishing one-to-many relationships between centralized fact tables (`delivery_events`, `loads`, `fuel_purchases`, `maintenance_records`) and dimension models (`Calendar`, `drivers`, `facilities`, `routes`, `customers`, `Dim_State`).
* **Data Cleansing & Transformation:** Executed in Power Query to standardize timestamps, isolate transit vs. detention dwell periods, and handle regional name normalization.
* **UI/UX Container Design:** Custom slate-navy container frames built in PowerPoint to eliminate visual noise, standardize 5-KPI header ribbons, and maintain fixed visual bounds across all viewports.

---

## 📐 Key DAX Measures (Samples)

### On-Time Delivery Rate (OTD %)
```dax
On-Time Delivery Rate = 
DIVIDE(
    CALCULATE(
        COUNTROWS(delivery_events),
        delivery_events[on_time_flag] = TRUE()
    ),
    COUNTROWS(delivery_events),
    0
)
SLA Target = 0.95
Cost Per Mile = 
DIVIDE(
    [Total Operational Expenses],
    [Total Fleet Mileage],
    0
)
