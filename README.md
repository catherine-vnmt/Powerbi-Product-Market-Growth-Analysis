<img width="1002" height="1024" alt="89cf3a33-78e6-43c5-aa3d-97e350209c10" src="https://github.com/user-attachments/assets/2ca74846-1051-4c48-878d-dde4b6745ed5" />

---

# 📊 [Power BI] Product & Market Strategic Growth Analysis at Global Retail Superstore 

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### 🎯 Objective:
Global Superstore is a retail business operating across 7 markets worldwide. Despite growing revenue year over year, profit growth is slowing down — raising a critical question for senior management:
> *"Are we growing in the right markets, with the right products?"*
This dashboard was built to answer that question by helping senior management:

✔️ **See the full picture** — How is the business performing overall? Is growth healthy or just a vanity metric?

✔️ **Pick the right market** — Which markets are worth investing more into? Which ones should we scale back or exit?

✔️ **Back the right product** — Which products are actually driving profit, not just revenue?

✔️ **Act with confidence** — Make faster, better-informed strategic decisions without getting lost in raw data

### 👤 Who is this project for?  

✔️ Senior Management (Head of Region / C-level executives)  
✔️ Head of Region / Global Business Director 

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: [Global Superstore dataset](https://www.kaggle.com/datasets/shekpaul/global-superstore) (Kaggle) 
- Size: The largest table has 51.292 rows and 20 columns
- Format: .csv 

### 📊 Data Structure & Relationships  

#### 1️⃣ Table Schema & Data Snapshot 

**Table 1: Orders Table** ***(Fact table)***
- Core transaction table containing all sales records across 7 global markets, covering orders, revenue, profit, shipping, and customer information.

<details>
<summary>View Table Schema</summary>

| Column Name | Data Type | Description |
|---|---|---|
| Order ID | Text | Unique identifier for each order |
| Order Date | Date | Date the order was placed |
| Ship Date | Date | Date the order was shipped |
| Ship Mode | Text | Shipping method (First Class, Second Class, Standard, Same Day) |
| Customer ID | Text | Unique identifier for each customer |
| Customer Name | Text | Full name of the customer |
| Segment | Text | Customer segment (Consumer, Corporate, Home Office) |
| City | Text | City of delivery |
| State | Text | State/province of delivery |
| Country | Text | Country of delivery |
| Postal Code | Text | Postal code of delivery |
| Region | Text | Sub-region within market |
| Market | Text | Regional market (US, EU, APAC, LATAM, Africa, EMEA, Canada) |
| Product ID | Text | Unique identifier for each product |
| Category | Text | Product category (Technology, Furniture, Office Supplies) |
| Sub-Category | Text | Product sub-category (e.g. Copiers, Phones, Chairs...) |
| Product Name | Text | Full product name |
| Sales | Decimal | Revenue generated from the order |
| Quantity | Integer | Number of units ordered |
| Profit | Decimal | Profit generated from the order |

</details>

---

**Table 2: People** ***(Dimension table)***
- Maps each regional market to its responsible sales representative. 

<details>
<summary>View Table Schema</summary>

| Column Name | Data Type | Description |
|---|---|---|
| Person | Text | Name of the regional sales representative |
| Region | Text | Regional market the person is responsible for |

</details>

---

**Table 3: Returns** ***(Dimension Table)***
- Records all returned orders, linked to the Orders table via Order ID to calculate return rate.

<details>
<summary>View Table Schema</summary>

| Column Name | Data Type | Description |
|---|---|---|
| Returned | Text | Return status (always "Yes" — only returned orders are recorded) |
| Order ID | Text | Foreign key linking to Orders table |

</details>

---

**Table 4: Dim Date** ***(Created Dimension Table)***
- Custom date table created in Power BI to enable time intelligence calculations (YOY, YTD...). Built to cover the full date range of the Orders table (2011–2014).

<details>
<summary>View Table Schema</summary>

| Column Name | Data Type | Description |
|---|---|---|
| Date | Date | Full date value (e.g. Friday, 1 July 2011) |
| Year | Integer | Calendar year (e.g. 2011) |
| Month | Integer | Month number (1–12) |
| Month Name | Text | Full month name (e.g. July) |
| Year-Month | Text | Combined year and month (e.g. 2011-07) |
| Quarter | Integer | Quarter number (1–4) |

</details>

#### 2️⃣ Data Relationships:  
<img width="1195" height="734" alt="Data relationship" src="https://github.com/user-attachments/assets/8015b137-e0df-4306-abab-8b802f489a94" />
 
<img width="816" height="185" alt="Data relationship 2" src="https://github.com/user-attachments/assets/f2f46463-e005-4d1f-8595-ec0690ccf002" />

---

## 🧠 Design Thinking Process  

1️⃣ **Empathize**
 
### 5W1H Stakeholder Analysis to understand the problem
<img width="1191" height="880" alt="design thinking 1" src="https://github.com/user-attachments/assets/e44729f7-de71-4ffd-bc37-f9aa1861b05a" />

### Empathy map to map the problem with the user
<img width="831" height="1024" alt="design thinking 2" src="https://github.com/user-attachments/assets/48c57d3a-6f7b-4253-8f2c-e16a5e46c727" />

### Explore the dataset to see what we have to solve the problem
<img width="596" height="1024" alt="desing thinking 3" src="https://github.com/user-attachments/assets/85a0a9db-0971-4fc0-bd8b-afb457df8db1" />

2️⃣ **Define point of view**

### Define Northstar Metrics to determine the most critical values to measure
<img width="1002" height="1024" alt="design thinking 4" src="https://github.com/user-attachments/assets/4b919833-92b6-443b-9a8a-fd7520562976" />

### Define Point of View to identify the key viewpoints the stakeholder needs to observe
<img width="1024" height="920" alt="desing thinking 5" src="https://github.com/user-attachments/assets/13519354-7eff-45e6-b9d9-5bafd7a99310" />

### Develop Growth Formula to break down each Northstar metric into measurable components in each viewpoint
<img width="988" height="1024" alt="design thinking 6" src="https://github.com/user-attachments/assets/32d64c29-54d9-498e-9b7a-e9ff4568dfb6" />


3️⃣ **Ideate**
<img width="891" height="1024" alt="desing thinking 7" src="https://github.com/user-attachments/assets/8e3138e6-b9e7-47d6-a509-5cd190cf6910" />


4️⃣ **Prototype and review**  

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Overview Dashboard Preview  
📌 Analysis 1: Overall Business Health
- The company has achieved solid cumulative performance — 178K units sold, $12.64M in total revenue, and $1.47M in total profit. Profit margin has remained stable at around 11–12% across all four years, indicating the business is consistently profitable.

- However, growth momentum is clearly decelerating. Revenue growth slowed from 27.20% (2013) to 26.25% (2014), while profit growth dropped sharply from 32.37% (2013) to 23.89% (2014). Combined with the plateauing profit margin, this signals the business is approaching growth saturation under its current model — continuing without a strategic shift will likely yield diminishing returns.
<img width="1433" height="807" alt="image" src="https://github.com/user-attachments/assets/aecc6913-9ea1-452e-bbab-642b0f1a1edf" />

<img width="1436" height="809" alt="image" src="https://github.com/user-attachments/assets/4f780116-da0e-4d4c-a39a-cd12bf0c1785" />


#### 2️⃣ Product Performance Preview  
📌 ***Analysis 2: Strategic Product: Technology — Copiers***  
- To identify the right growth lever, the analysis starts at the product level. **Technology** is the highest-contributing category in both revenue and profit. More importantly, after bottoming out in 2013 (revenue growth: 24.8%, profit growth: 18.94%), Technology showed a strong recovery in 2014 (revenue growth: 26.53%, profit growth: 35.31%) — and its return rate has been declining (6.09% in 2013 → 5.42% in 2014). These are signs of **improving, quality-driven growth**.

- Within Technology, **Copiers** is selected as the strategic product because:
While Phones rank higher in revenue contribution, Copiers contribute more to total profit and carry a higher profit margin
    - Copiers show accelerating profit growth: 39.4% (2013) → 43.9% (2014)
    - This combination of high margin + accelerating profit growth + declining return rate makes Copiers the most investable sub-category
      
<img width="1441" height="809" alt="image" src="https://github.com/user-attachments/assets/e6c23d2d-7dd2-4266-9e8c-bd225d378929" />


#### 3️⃣ Market Performance Preview  
📌 ***Analysis 3: Strategic Market: EU*** 
- At the market level, APAC and EU are the top two contributors to both revenue and profit, with comparable profit margins — EU at 27.67% and APAC at 27%. While APAC leads in total sales volume, EU demonstrates a consistently stronger profit growth trajectory:
    - EU %Profit YOY: 41.81% (2013) → 46.59% (2014)
    - APAC %Profit YOY: 19.85% (2013) → 31.68% (2014)
<img width="1438" height="807" alt="image" src="https://github.com/user-attachments/assets/6218e3e8-a7cf-480d-842d-cc1c4c2119ab" />

---

## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, we would recommend the **Global business management** to consider the following:

📌 Key Takeaways:  
Strategic focus: Scale Copiers in the EU market
Based on the combined product and market analysis, the clearest near-term growth opportunity lies at the intersection of the highest-margin product (Copiers) and the highest-growth market (EU).

⚠️ Important risk flag: The return rate for Copiers in the EU market reached 11.59% in 2014 — notably high and must be investigated before scaling investment. Whether this is driven by product quality issues (supplier-side) or customer expectation mismatches will determine the corrective action required.

✔️ **Expand the Copier product range:** Introduce newer Copier models to attract new buyers and give existing customers a reason to upgrade — driving both new customer acquisition and upsell revenue.  
✔️ **Proactive outreach to existing customers:** Actively contact long-term Copier buyers to offer maintenance services for their existing machines, while introducing new product lines for upgrade consideration. This converts one-time buyers into repeat customers and builds long-term relationships. 
✔️ **Cross-sell related Office Supplies:** Offer relevant Office Supplies (paper, ink cartridges, accessories) as bundled promotions to Copier buyers — increasing average order value with minimal additional sales effort.

✔️ **Bundle maintenance and service packages:** Offer optional service and warranty packages alongside Copier sales to maximize revenue per transaction and create a recurring revenue stream beyond the initial purchase.

✔️ **Prepare to replicate in APAC:** After proving the model in EU, APAC is the logical next market — it has the largest sales volume of all markets and a comparable profit margin to EU (~27%). Having a documented playbook from the EU expansion will significantly reduce the time and cost of replicating success in APAC.
