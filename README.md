<h1># ✈️ Airline Performance Analysis Dashboard</h1>

## 📌 Project Overview

The Airline Performance Analysis Dashboard is an end-to-end Business Intelligence project developed using Power BI. The dashboard provides comprehensive insights into airline operations, passenger bookings, revenue generation, flight delays, cancellations, and overall airline performance.

The project demonstrates the complete Power BI workflow, including data cleaning, transformation, data modeling, DAX calculations, KPI tracking, and interactive dashboard design.

---

## 🎯 Objectives

* Analyze passenger booking patterns and travel trends.
* Monitor airline revenue and operational performance.
* Identify delay-prone routes and cancellation patterns.
* Evaluate airline efficiency through KPIs.
* Provide actionable business insights through interactive visualizations.

---

## 🛠️ Tools & Technologies

| Tool        | Purpose                        |
| ----------- | ------------------------------ |
| Power BI    | Dashboard Development          |
| Power Query | Data Cleaning & Transformation |
| DAX         | KPI & Measure Creation         |
| Excel / CSV | Data Source                    |
| GitHub      | Project Hosting                |

---

## 📂 Dataset Information

The dataset contains airline booking and flight operation data including:

### Booking Information

* Booking ID
* Passenger ID
* Passenger Name
* Booking Date
* Travel Date
* Ticket Class
* Ticket Status
* Ticket Price

### Flight Information

* Flight ID
* Airline
* Source City
* Destination City
* Departure & Arrival Times
* Flight Status

### Performance Metrics

* Delay Minutes
* Cancellation Flag
* Seats Available
* Seats Booked

---

## 🔄 Data Preparation

### Power Query Transformations

* Removed duplicate records.
* Handled missing values.
* Standardized airline names.
* Standardized city names.
* Created Delay Categories:

  * On Time
  * Minor Delay
  * Major Delay
* Extracted:

  * Year
  * Quarter
  * Month
* Calculated Occupancy Percentage.

---

## 🏗️ Data Modeling

Implemented a Star Schema Model.

### Fact Table

* Flight_Bookings

### Dimension Tables

* Dim_Date
* Dim_Airline
* Dim_Ticket
* Dim_City

Relationships were established to enable efficient filtering and reporting.

---

## 📊 DAX Measures Created

### Total Passengers

```DAX
Total Passengers =
COUNT(Flight_Bookings[Passenger_ID])
```

### Total Revenue

```DAX
Total Revenue =
SUM(Flight_Bookings[Ticket_Price])
```

### Total Flights

```DAX
Total Flights =
DISTINCTCOUNT(Flight_Bookings[Flight_ID])
```

### Cancelled Flights

```DAX
Cancelled Flights =
CALCULATE(
COUNTROWS(Flight_Bookings),
Flight_Bookings[Cancellation_Flag]=1
)
```

### On-Time Percentage

```DAX
On-Time Percentage =
DIVIDE(
COUNTROWS(
FILTER(
Flight_Bookings,
Flight_Bookings[Delay_Minutes]<=15
)),
COUNTROWS(Flight_Bookings)
)
```

### Average Delay

```DAX
Average Delay =
AVERAGE(Flight_Bookings[Delay_Minutes])
```

### Load Factor

```DAX
Load Factor =
DIVIDE(
SUM(Flight_Bookings[Seats_Booked]),
SUM(Flight_Bookings[Seats_Available])
)
```

---

## 📈 Dashboard Pages

### 1. Executive Overview

KPIs:

* Total Revenue
* Total Passengers
* Total Flights
* Cancellation Rate
* On-Time Percentage

Visuals:

* Revenue Trend
* Flights by Airline
* Revenue by Ticket Class
* Ticket Status Distribution

---

### 2. Flight Performance Analysis

Visuals:

* Monthly Delay Trends
* Flight Status Analysis
* Delay Category Distribution
* Airline Performance Comparison

---

### 3. Revenue Analysis

Visuals:

* Revenue by Airline
* Revenue by Route
* Revenue by Ticket Class
* Monthly Revenue Trends

---

### 4. Passenger Analysis

Visuals:

* Passenger Volume by Airline
* Ticket Status Breakdown
* Class-wise Booking Analysis
* Passenger Distribution

---

## 🎛️ Interactive Features

* Airline Slicer
* Date Slicer
* Source City Filter
* Destination City Filter
* Drill-Through Analysis
* Dynamic Cross-Filtering
* Interactive Tooltips

---

## 🔍 Key Business Insights

* Identified the highest revenue-generating airlines.
* Analyzed routes with maximum delays.
* Evaluated airline punctuality performance.
* Tracked cancellation trends across airlines.
* Measured seat occupancy and load factors.
* Analyzed passenger preferences by ticket class.

---

## 📷 Dashboard Preview

Add screenshots here:

### Executive Overview

![Executive Overview](screenshots/executive_overview.png)

### Flight Performance

![Flight Performance](screenshots/flight_performance.png)

### Revenue Analysis

![Revenue Analysis](screenshots/revenue_analysis.png)

### Passenger Analysis

![Passenger Analysis](screenshots/passenger_analysis.png)

---

## 📁 Repository Structure

```text
Airline-Performance-Dashboard/
│
├── Airline_data_analysis.pbix
├── Flight_Bookings.csv
├── README.md
├── screenshots/
│   ├── executive_overview.png
│   ├── flight_performance.png
│   ├── revenue_analysis.png
│   └── passenger_analysis.png
└── documentation/
    └── Project_Report.pdf
```

---

## 🚀 Skills Demonstrated

* Power BI
* Power Query
* DAX
* Data Cleaning
* Data Modeling
* KPI Monitoring
* Business Intelligence
* Dashboard Design
* Data Visualization

---

## 👨‍💻 Author

**Utsaw Kumar**

Data Analytics & Computer Science Student, IIT Patna

LinkedIn: Add Your LinkedIn URL

GitHub: Add Your GitHub Profile URL

