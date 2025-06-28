# Superstore Analytics Dashboard - Tableau

*Interactive Tableau dashboard for analyzing Superstore sales, profit, and orders.*

---

## 📌 Overview
A dynamic Tableau dashboard built to analyze the **Sample Superstore** dataset. This project demonstrates advanced Tableau features like parameters, LOD calculations, and interactive filtering to provide actionable business insights.

Key Questions Addressed:
- How do sales and profit trends vary by region/category?
- Which products contribute most to profit margins?
- What is the return rate across customer segments?

---

## 🛠️ Technical Implementation

### **1. Core Features**
| Feature                | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Dynamic Metrics**    | User-selectable metrics (Sales/Profit/Orders) via parameter control.        |
| **Interactive Filters**| Year/Region filters with show/hide toggle for cleaner UI.                   |
| **Top 5 Products**     | Always displays top performers regardless of other filters (LOD calculation).|
| **KPI Cards**          | Real-time Profit Margin (`SUM(Profit)/SUM(Sales)`) and Return Rate metrics.  |

### **2. Advanced Techniques Used**
- **Parameters**: Created for metric selection and view customization.
- **Calculated Fields**: 
  ```tableau
  // Profit Margin Calculation
  [Profit Margin] = SUM([Profit])/SUM([Sales])
  
  // Return Rate Calculation
  [Return Rate] = COUNTD(IF [Returned]=TRUE THEN [Order ID] END)/COUNTD([Order ID])
