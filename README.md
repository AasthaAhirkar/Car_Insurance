# 📊 Insurance Risk & Claims Analysis – Power BI 

This project provides a complete analysis of insurance policyholders, vehicle information, and claim patterns using an interactive Power BI dashboard.  
The goal is to help insurance companies understand risk, customer behavior, and claim trends for better decision-making.

---

## 🧩 Problem Statement

Insurance companies store data across different systems.  
Due to this scattered information, stakeholders face challenges like:

- Lack of a unified dashboard  
- Difficulty analyzing policy and claim trends  
- No proper demographic or risk segmentation  
- Limited visibility into high-risk customers  
- No data-driven approach to premium optimization  

A centralized dashboard is required to visualize claims, policies, customer segments, risk zones, and behavioral factors.

---

## 🎯 Project Objective

Build a **Power BI dashboard** that delivers:

- Clear KPIs for policies & claims  
- Segmentation by demographic & vehicle attributes  
- Region-wise claim performance  
- Risk analysis using age, education, kids driving & car usage  
- A dynamic measure switch for deep exploration  
- Business insights to support underwriting & pricing  

---

## 📘 Domain Understanding

Insurance risk depends on multiple variables:

### 1️⃣ Age  
Young (<25) → higher accident risk  
Middle-aged (26–55) → highest policy volume  
Old (>60) → moderate risk  

### 2️⃣ Vehicle Age  
New cars → fewer claims  
Old cars (>10 yrs) → higher breakdown risk  

### 3️⃣ Car Use  
Commercial cars → more exposure → more claims  

### 4️⃣ Coverage Zone  
Urban → heavy traffic → more accidents  
Rural → low frequency but severe damage  

### 5️⃣ Kids Driving  
Households with young drivers tend to generate higher claim amounts  

### 6️⃣ Claim Amount & Frequency  
High frequency = risky customers  
High amount = severe losses  

---

## 🧹 Data Cleaning & Transformation

Performed using Power Query:

- Removed duplicates  
- Handled blank values  
- Created **Age** from Birthdate  
- Created **Age Groups**  
- Converted Claim Amount to numeric  
- Created **Car Age** column  
- Normalized categorical fields  
- Grouped Kids Driving into bins  

---

## 📐 DAX Measures Used

```DAX
Total Policies = COUNT('Data'[ID])

Total Claim Amount = SUM('Data'[Claim Amt])

Average Claim Amount = AVERAGE('Data'[Claim Amt])

Claim Frequency = AVERAGE('Data'[Claim Freq])
```

Dynamic Switch:

```DAX
Selected Measure =
SWITCH(
    SELECTEDVALUE('Measure Selector'[Measure]),
    "Total Policies", [Total Policies],
    "Total Claim Amount", [Total Claim Amount]
)
```

---

## 📊 Dashboard Visuals

### 📌 KPIs
- Total Policies  
- Total Claim Amount  
- Avg Claim Frequency  
- Avg Claim Amount  
- Gender-wise Policies  

### 📈 Visual Components

| Visual | Purpose |
|--------|---------|
| Donut – Car Use | Private vs Commercial claim analysis |
| Bar – Car Make | High-risk vehicle brands |
| Donut – Coverage Zone | Region-wise claims |
| Bar – Age Group | Which age groups file more claims |
| Area – Car Year | Impact of car age |
| Ribbon – Kids Driving | Risk based on young drivers |
| Pie – Education | Education-level segmentation |
| Matrix – Education vs Marital Status | Customer profiling |

## 🖼️ Dashboard Screenshots

### 📌 Insurance Dashboard
![Dashboard Preview](https://github.com/AasthaAhirkar/Car_Insurance/blob/main/dashboard1.png)


---

## 🔍 Key Business Insights

### 🚗 Car Use
- Private cars → highest policies  
- Commercial cars → fewer policies but higher claim severity  

### 🚘 Car Make
- Ford & Chevrolet → highest claim amounts  
- Luxury brands → expensive repairs → higher claim costs  

### 🗺 Coverage Zone
- Urban & Highly Urban → highest claim frequency  
- Rural → fewer claims but moderate impact  

### 🎯 Age Group
- 26–55 age group → highest contribution  
- 15–25 → low share but high risk behavior  

### 🚙 Car Year
- 2000–2015 vehicles → most claims  
- Very old cars → fewer policies → lower claims  

### 👨‍👧 Kids Driving
- 0 kids → lowest claims  
- 1 or more kids → sharp increase in claim amount  

### 🎓 Education
- Bachelor’s & High School → highest claims  
- Higher education → moderate claim levels  

---

## 📌 Conclusion

This Power BI dashboard provides a clear, data-driven view of insurance policies and claim patterns, helping identify high-risk segments and key business trends.
It enables insurance companies to improve decision-making, optimize premium strategies, and manage claims more efficiently.
