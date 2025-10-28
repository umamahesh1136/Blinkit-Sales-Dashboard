# 📊 DAX Measures & Calculated Columns — Blinkit Sales Dashboard

This document lists all the DAX measures and calculated columns created for the Blinkit Power BI Project, along with simple explanations for each.  

---

## 🧮 DAX MEASURES

### 💰 1. Total Sales
```DAX
Total Sales = SUM('BlinkIT Grocery Data'[Sales])
```
**Explanation:**  
Calculates the total sales amount from all transactions across all outlets.

---

### 🏬 2. Average Sales per Outlet
```DAX
Average Sales per Outlet = AVERAGE('BlinkIT Grocery Data'[Sales])
```
**Explanation:**  
Finds the mean (average) sales per outlet to assess overall outlet performance.

---

### 📆 3. Average Years of Operation
```DAX
Average Years of Operation = AVERAGE('BlinkIT Grocery Data'[Years of Operation])
```
**Explanation:**  
Shows how long, on average, outlets have been in operation.

---

### ⭐ 4. Avg Item Rating (CSAT)
```DAX
Avg Item Rating (CSAT) = ROUND(AVERAGE('BlinkIT Grocery Data'[Rating]), 1)
```
**Explanation:**  
Calculates the average customer satisfaction (rating) across all items, rounded to one decimal place.

---

### 📦 5. No. of Items
```DAX
No_Of_Items = COUNTROWS('BlinkIT Grocery Data')
```
**Explanation:**  
Counts the total number of items available in the dataset (used for KPI cards or totals).

---

### 🌆 6. Sales by Tier
```DAX
Sales Tier 1 = CALCULATE([Total Sales], 'BlinkIT Grocery Data'[Outlet Location Type] = "Tier 1")
Sales Tier 2 = CALCULATE([Total Sales], 'BlinkIT Grocery Data'[Outlet Location Type] = "Tier 2")
Sales Tier 3 = CALCULATE([Total Sales], 'BlinkIT Grocery Data'[Outlet Location Type] = "Tier 3")
```
**Explanation:**  
Calculates total sales separately for each tier (Tier 1, Tier 2, Tier 3) to analyze regional performance.

---

### 🥛 7. Sales by Fat Content
```DAX
Total Sales Fat Content (Low Fat) =
CALCULATE(SUM('BlinkIT Grocery Data'[Sales]), 'BlinkIT Grocery Data'[Item Fat Content] = "Low Fat")

Total Sales Fat Content (Regular) =
CALCULATE(SUM('BlinkIT Grocery Data'[Sales]), 'BlinkIT Grocery Data'[Item Fat Content] = "Regular")
```
**Explanation:**  
Compares sales between low-fat and regular-fat products to identify health-conscious buying patterns.

---

## 🧾 CALCULATED COLUMNS

### ⚖️ 1. Sales per Kg
```DAX
Sales per Kg = 'BlinkIT Grocery Data'[Sales] / 'BlinkIT Grocery Data'[Item Weight]
```
**Explanation:**  
Shows efficiency of each item by measuring sales value generated per kilogram.

---

### 🕒 2. Years of Operation
```DAX
Years of Operation = YEAR(TODAY()) - 'BlinkIT Grocery Data'[Outlet Establishment Year]
```
**Explanation:**  
Calculates how many years each outlet has been active since its establishment.

---

## 🎯 Usage Notes
- All measures are used in KPI cards and charts to analyze sales, efficiency, and performance by product type, outlet, and tier.  
- The calculated columns enable deeper metrics like *Sales per Kg* and *Outlet Age* that support custom visuals such as scatter plots, combo charts, and ribbon charts.

---

