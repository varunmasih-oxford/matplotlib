# Python Data Visualization – Practical Lab
## Project: Retail Business Data Analysis (22 Exercises, Beginner → Advanced)

**Role:** Data Analyst at a retail company selling electronics online and offline.
**Tools:** Python, Pandas, Matplotlib, Seaborn
**Dataset:** `retail_sales.csv` (1,200 orders, Jan 2024 – Dec 2025)

### Data dictionary
| Column | Meaning |
|---|---|
| Order_ID, Order_Date | Order identifier and date |
| Region | North / South / East / West |
| Store_Type | Online / Offline |
| Category, Product | Product hierarchy |
| Unit_Price, Quantity | Price per unit, units sold |
| Customer_ID, Customer_Age, Age_Group, Gender | Customer details |
| Customer_Segment | Regular / Premium / Corporate / Student |
| Discount_Pct | Discount given (%) |
| Ad_Spend | Advertising spend linked to the order (₹) |
| Revenue, Cost, Profit | Financials per order (₹) |
| Rating | Customer rating 1–5 (25 values missing) |
| Delivery_Days | Days to deliver |
| Payment_Mode | Card / UPI / Cash / EMI |

### Setup
```python
import pandas as pd, numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv("retail_sales.csv", parse_dates=["Order_Date"])
df["Month"] = df["Order_Date"].dt.to_period("M").dt.to_timestamp()
```
**Rules for every exercise:** (1) decide the chart yourself and justify it, (2) add title, axis labels, and legend where needed, (3) write a 2–3 line business interpretation.

---
## Level 1 – Beginner (Exercises 1–7): Comparisons, trends, shares

**1. Monthly sales trend.** Management wants to know how total revenue has moved month by month across the two years. Are there seasonal peaks?

**2. Best category.** Which product category brings in the most revenue? Present it so the ranking is obvious.

**3. Top 10 products.** Product names are long. Show the 10 best-selling products by revenue in a readable way.

**4. Online vs offline by region.** Compare online and offline revenue in each region side by side. Where does online beat offline?

**5. Category mix per region.** The regional heads want to see both total revenue and how it is made up by category, in a single chart.

**6. Customer segment share.** What share of total revenue comes from each customer segment? (Use a chart that shows part-to-whole.)

**7. Payment preferences.** Show how orders are split across payment modes, using a ring-style chart. Which mode could the finance team promote?

## Level 2 – Intermediate (Exercises 8–14): Distributions and relationships

**8. Age profile.** How are customers distributed by age? Experiment with bin counts (5, 10, 20). What changes in your interpretation?

**9. Age by gender.** Compare the smooth age distribution of male and female customers. Do they overlap?

**10. Profit spread.** Some categories look risky. Show the median, spread, and outliers of profit per category.

**11. Customer satisfaction.** Compare the full shape of the rating distribution for online vs offline stores. Is the average hiding something?

**12. Advertising effect.** Is there a relationship between advertising spend and revenue per order?

**13. Category performance map.** Show revenue, profit, and units sold for each category in one chart (three variables).

**14. Discount impact.** Do heavier discounts reduce profit? Add a trend line and report the direction.

## Level 3 – Advanced (Exercises 15–22): Multi-variable and composite views

**15. Profitability drivers.** Which numeric factors (price, quantity, discount, ad spend, rating, delivery days) move with revenue and profit? Show every pairwise relationship in one grid with values.

**16. Variable explorer.** Create a matrix of scatter plots and distributions for Age, Discount, Ad Spend, Revenue, and Profit. Pick two relationships that surprise you. (Hint: use a 400-row sample.)

**17. Growth story.** Show how revenue accumulates over the two years, with the filled area emphasising total volume.

**18. Changing mix.** Show how each category's monthly revenue contributes to the total over time. Which category drives the festive (Oct–Dec) spike?

**19. Who buys?** How many orders come from each age group? Keep the age groups in natural order.

**20. Delivery experience.** Show every individual order's delivery time by region (not just averages). Which region has the most delays?

**21. Dense data.** Ad Spend vs Revenue has many overlapping points. Show the relationship together with the distribution of each variable on the margins.

**22. Two metrics, one story.** Show monthly revenue and profit margin % together on one chart, using two different y-axes. Do high-revenue months also have high margins?

---
## Final Project – Management Dashboard
Build a single 2×3 dashboard (`plt.subplots`) answering management's seven questions:
1. Top products 2. Monthly trend 3. Revenue by customer group 4. Age distribution 5. Ad vs sales 6. Regional performance 7. Profitability drivers

**Deliverables:** `dashboard.png` plus a half-page written summary with 3 findings and 2 recommendations.

### Marking scheme (per exercise, 10 marks)
| Criterion | Marks |
|---|---|
| Appropriate chart choice with justification | 3 |
| Correct, clean code (groupby/pivot used well) | 3 |
| Labels, title, readability | 2 |
| Business interpretation | 2 |

### Chart-type answer key (instructors only)
1 Line · 2 Bar · 3 Horizontal bar · 4 Grouped bar · 5 Stacked bar · 6 Pie · 7 Donut · 8 Histogram · 9 KDE · 10 Box plot · 11 Violin · 12 Scatter · 13 Bubble · 14 Regression plot · 15 Correlation heatmap · 16 Pair plot · 17 Area · 18 Stacked area · 19 Count plot · 20 Strip plot · 21 Joint (hexbin) plot · 22 Dual-axis combo
