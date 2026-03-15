# 🛒 Global Superstore Sales — Exploratory Data Analysis (EDA)

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.x-green?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange)
![Plotly](https://img.shields.io/badge/Plotly-5.x-purple?logo=plotly)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

---

## 📌 Project Overview

A full end-to-end Exploratory Data Analysis on a **Global Superstore Sales** dataset containing **51,290 orders** across **7 markets** and **147 countries** from **2011 to 2014**.

The goal was to extract actionable business insights around profitability, discount strategy, sales performance, customer behavior, and shipping operations.

---

## 📊 Dataset

| Property | Value |
|---|---|
| Rows | 51,290 |
| Columns | 21 |
| Period | 2011 – 2014 |
| Markets | APAC, EU, US, LATAM, Africa, EMEA, Canada |
| Source | Global Superstore (Kaggle) |

### Key Columns
- `order_date`, `ship_date` — Order and shipping dates
- `category`, `sub_category`, `product_name` — Product info
- `sales`, `profit`, `discount`, `shipping_cost` — Financial data
- `market`, `region`, `country` — Geographic data
- `segment`, `customer_name` — Customer data

---

## 🔧 Project Pipeline
```
1. Data Loading
2. Data Cleaning
3. Exploratory Data Analysis (EDA)
4. Data Visualization
5. Key Insights
```

---

## 🧹 Data Cleaning Steps

- Converted `order_date` and `ship_date` to `datetime` format
- Fixed numeric columns with comma-separated values (`1,648` → `1648`)
- Filled missing values using `mode()` for categorical columns
- Filled missing numeric values using `groupby product_name` mean
- Calculated `days_to_ship` from date difference
- Verified zero duplicate rows

---

## 💡 Key Findings

### Profit & Loss
| Metric | Value |
|---|---|
| Overall Profit Margin | **11.62%** |
| Unprofitable Orders | **24%** of all orders |
| Best Category | Technology ($663K profit) |
| Worst Category | Furniture (highest losses ratio) |

### Discount Impact
> ⚠️ **Discount is the #1 driver of losses — not shipping cost.**

| Discount Range | Avg Profit |
|---|---|
| 0% – 10% | +$72.62 |
| 10% – 20% | +$27.61 |
| 20% – 30% | **-$21.88** ← loss starts here |
| 30% – 50% | -$61.55 |
| 50% – 80% | -$98.20 |
| 80% – 100% | -$1,534.33 |

Discount–Profit Correlation:
- Furniture: **-0.49** (strongest negative impact)
- Technology: -0.38
- Office Supplies: -0.25

### Sales Performance
| Year | Sales | YoY Growth |
|---|---|---|
| 2011 | $2.26M | — |
| 2012 | $2.68M | +19% |
| 2013 | $3.41M | +27% |
| 2014 | $4.30M | +26% |

**Top Market:** APAC ($3.58M sales, $437K profit)  
**Top Country by Sales:** United States ($2.3M)  
**Top Country by Profit:** United States ($286K)

### Customer Behavior
- **Consumer** segment generates the most profit ($749K)
- **Top customer by profit:** Tamara Chand ($8,673)
- **Top customer by sales:** Tom Ashbrook ($40,489)

### Operations & Shipping
| Ship Mode | Avg Days | Avg Cost |
|---|---|---|
| Standard Class | 5 days | $20 |
| Second Class | 3 days | $30 |
| First Class | 2 days | $41 |
| Same Day | 0 days | $43 |

> ✅ Order priority **does** affect shipping speed:
> Critical = 2 days avg vs Low = 6 days avg

---

## 📈 Visualizations

The notebook includes the following charts:

- Total Profit by Category
- Profit by Sub-Category (Top 10)
- Gains vs Losses by Category
- Profit vs Discount Scatter Plot
- Avg Profit by Discount Range
- Discount–Profit Correlation by Category
- Sales Trend by Year
- Year-over-Year Sales Growth %
- Total Sales by Market
- Top 10 Countries by Sales & Profit
- Profit by Country (Choropleth Map)
- Total Profit by Segment
- Avg Shipping Time by Ship Mode & Priority
- Monthly Sales & Profit Trend (Dual Axis)

---

## 🛠️ Tools & Libraries
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
```



## 📬 Contact

Feel free to connect on [LinkedIn](https://www.linkedin.com/in/mohamed-eltmsah/) or reach out for collaboration!

---

> *"Data is not just numbers — it tells a story. This project is about listening to it."*
