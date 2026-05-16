# DAX Measures & Calculated Columns

This file contains key DAX measures and calculated columns used in the Pizza Sales Performance Analysis Dashboard built using Power BI.

---

# KPI Measures

## Total Revenue

```DAX
Total Revenue =
SUM(order_details[Revenue])
```

Calculates total sales revenue generated from all pizza orders.

---

## Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(order_details[order_id])
```

Calculates total number of customer orders.

---

## Total Pizzas Sold

```DAX
Total Pizzas Sold =
SUM(order_details[quantity])
```

Calculates total quantity of pizzas sold.

---

## Average Order Value

```DAX
Average Order Value =
DIVIDE([Total Revenue], [Total Orders])
```

Calculates average revenue generated per order.

---

# Dynamic Title Measures

## Revenue Analysis Dynamic Title

```DAX
Dynamic Title =
"Revenue Analysis | " &
SELECTEDVALUE(orders[Month Name], "All Months")
& " | " &
SELECTEDVALUE(pizza_types[category], "All Categories")
```

Creates dynamic chart titles based on slicer selections.

---

# Calculated Columns

## Day Number Sorting

```DAX
Day Number =
SWITCH(
    orders[day_name],
    "Monday",1,
    "Tuesday",2,
    "Wednesday",3,
    "Thursday",4,
    "Friday",5,
    "Saturday",6,
    "Sunday",7
)
```

Used for proper weekday sorting in charts and visuals.

---

## Rush Hour Classification

```DAX
Rush Period =
SWITCH(
    TRUE(),
    orders[Hour] >= 11 && orders[Hour] <= 13, "Lunch Rush",
    orders[Hour] >= 17 && orders[Hour] <= 19, "Dinner Rush",
    "Normal Hours"
)
```

Classifies order timings into lunch rush, dinner rush, and normal business hours.

---

# Technical Skills Demonstrated

* DAX Calculations
* KPI Development
* Dynamic Dashboard Elements
* Calculated Columns
* Time-Based Analysis
* Interactive Reporting
* Business Intelligence & Analytics
