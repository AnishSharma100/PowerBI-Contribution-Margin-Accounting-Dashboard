# PowerBI Contribution Margin Accounting Dashboard
Interactive Power BI dashboard simulating a financial performance analysis for a manufacturing business. Designed as an academic project at HTW Berlin, this model visualises contribution margin, break-even analysis, and regional performance across Europe using DAX-driven KPIs.

#  Contribution Margin Accounting Dashboard

This project presents an **interactive Power BI dashboard** built to simulate the financial performance of a manufacturing company using **Contribution Margin Accounting** principles.  
It was created as a **final academic project** at **HTW Berlin – Hochschule für Technik und Wirtschaft Berlin (University of Applied Sciences)**.

All datasets were **self-created and simulated** for academic demonstration purposes.  
The entire model — including data modelling, DAX measures, visuals, and design — was built **entirely in Power BI**.

---

##  Objective

To build a managerial accounting dashboard that helps analyse:
- How much each product contributes to total profit (Contribution Margin)
- Fixed vs Variable cost behaviour across time
- Regional profitability differences
- Overall break-even point and EBIT trends

The focus was on **translating financial formulas into Power BI DAX** and creating **clear, interactive visual storytelling** for decision-makers.

---

##  Dashboard Overview

### **1 Contribution Margin Accounting (Overview Page)**
This is the **summary page** of the report.
- Displays high-level KPIs: **Total Revenue (€10.92M)**, **Variable Cost (€5.62M)**, **Fixed Cost (€2.54M)**, **Contribution Margin (€5.30M)**, and **EBIT (€2.75M)**.  
- The **line chart** compares Variable vs Fixed costs monthly, showing cost fluctuations and control efficiency.
- The **bar chart** highlights the **Top 10 Ordered Products** — helping identify the most frequently sold items contributing to total revenue.

<img width="1408" height="790" alt="image" src="https://github.com/user-attachments/assets/423d511e-e9db-42a1-abc7-942a4b47d484" />

 Purpose: Give management a quick overview of profitability trends and cost structures month-by-month.

---

### 2 **Product Contribution Margin**
- Waterfall-style visual comparing **total sales**, **variable cost**, **fixed cost**, and **contribution margin** per product  
- Dynamic slicers by **Product Name** and **Month**  
- Table with product-wise breakdown:  
  `Total Sale`, `Variable Cost`, `Fixed Cost`, `Contribution Margin`, and `EBIT`  
- Country-wise Contribution Margin:
  - Netherlands: €0.44M  
  - Italy: €0.28M  
  - France: €0.27M  
  - Spain: €0.26M  
  - Germany: €0.18M
<img width="1415" height="842" alt="image" src="https://github.com/user-attachments/assets/a0e77582-aedc-4d75-a07a-751fd85a4b4f" />  
Purpose: Identify which products and countries drive the most profit, supporting resource allocation and pricing strategies.

---

### 3 **Break-Even Analysis**
- Combined bar and line chart visualising **Total Revenue**, **Variable Cost**, **Fixed Cost**, and **Break-Even Revenue**
- KPIs:
  - Break-Even Revenue: €3.38M  
  - Break-Even Units: 7.78K  
- Interactive product filters for scenario analysis
<img width="1417" height="830" alt="image" src="https://github.com/user-attachments/assets/bf47264b-ca50-4f1f-af4b-00757ae73329" />
Purpose: Enable managers to see how cost structures affect the break-even point and profitability safety margins.

---

### 4 **Contribution Margin Quarterly**
- Layered area chart comparing:
  - Net Contribution Margin  
  - Supply Chain Costs  
  - Variable Cost  
  - Total Revenue  
- Highlights quarterly financial trends for managerial insights

<img width="1416" height="836" alt="image" src="https://github.com/user-attachments/assets/826a7530-46dd-4fb1-8a85-cc5db74dc464" />
Purpose: Monitor quarterly profitability evolution and identify periods of margin compression or expansion.

---

### 5 **Regional Contribution Margin**
- Interactive **map visual** showing regional profitability within Europe  
- Drill-down by **Country → Continent**  
- Geographic distribution of net contribution margin:
  - Germany, Netherlands, France, Spain, Italy, Belgium, Austria

<img width="1415" height="834" alt="image" src="https://github.com/user-attachments/assets/1add1203-8d3c-46c8-b4f4-e6ad66b77893" />
Purpose: Visualise how profitability varies geographically and locate the most and least profitable markets.

---

##  Data Modelling & Relationships

All data modelling and DAX calculations were completed in **Power BI Desktop**.

###  Data Model
Tables Used:
- **Master Data:** Revenue, Variable Cost, Fixed Cost, EBIT, Contribution Margin  
- **Product Category:** Product name and category hierarchy  
- **Region:** Continent and Country mappings  
- **Date:** Calendar table for time intelligence  
- **Supply Chain:** Net Contribution Margin by product  

Relationships:
- 1:* relationships between Master Data → Product Category / Date / Region  
- Model supports **cross-filtering by product, time, and geography**
- Advanced data modelling and relationship design using Star Schema.
<img width="1298" height="783" alt="image" src="https://github.com/user-attachments/assets/5cd110c5-ffcb-4d09-9e34-8d7201f3b014" />

---

DAX Calculations Overview

All financial KPIs in this dashboard were computed using DAX (Data Analysis Expressions) to simulate realistic managerial accounting logic.
Each measure dynamically responds to filters for Product, Country, and Month, providing an interactive decision-making environment.

Core Financial Measures
- Contribution Margin	= [Total Revenue] - [Total Variable Cost]	Calculates the profitability per product before deducting fixed costs.
- EBIT	= [Contribution Margin] - [Total Fixed Cost]	Represents earnings before interest and taxes, showing operational profitability.
- Break Even Units	= [Total Fixed Cost] / ([Selling Price per Unit] - [Variable Cost per Unit])	Determines the sales quantity needed to cover all fixed costs.
- Break Even Revenue	= [Break Even Units] * [Selling Price per Unit]	Converts break-even units into monetary value.
- Fixed Cost Coverage	= [Contribution Margin] / [Total Fixed Cost]	Indicates how much contribution margin covers fixed expenses.
- Variable Cost Coverage	= [Total Revenue] / [Total Variable Cost]	Evaluates efficiency between sales revenue and variable costs.
<img width="886" height="27" alt="image" src="https://github.com/user-attachments/assets/36c4b642-97d2-4be1-b11a-687b8238033e" />
<img width="723" height="29" alt="image" src="https://github.com/user-attachments/assets/a5063aa6-3675-4919-b84e-22704d46d142" />
<img width="874" height="24" alt="image" src="https://github.com/user-attachments/assets/ab8b7ad6-d22d-492a-9607-a7e4d6e56918" />
<img width="642" height="30" alt="image" src="https://github.com/user-attachments/assets/c7c8e878-cbbe-41d3-b15c-20afa8f8f9aa" />

---

Regional Hierarchy
A Region Hierarchy was created under the “Region” table
This structure enables users to drill down from Europe to individual countries (Germany, France, Spain, Italy, Netherlands, Belgium, Austria) in the map visual, connecting geography with profitability metrics.

<img width="211" height="65" alt="image" src="https://github.com/user-attachments/assets/23f42c44-ebe5-4a5f-8706-23d8b39b2966" />

Together, these DAX measures and hierarchies transform static financial data into a dynamic analytical model — making Power BI a practical tool for managerial accounting and strategic decision support.

---

Insights & Learnings

- Demonstrated how DAX can model classical accounting formulas dynamically.
- Applied cost-volume-profit (CVP) logic in Power BI.
- Enhanced understanding of financial storytelling through data visualisation.
- Developed advanced data modelling and relationship design using Star Schema.
- Used KPI cards, area charts, and maps to blend financial and operational perspectives.

Academic Context

This dashboard was submitted as part of the MBA&E – Global Procurement programme’s final evaluation at HTW Berlin.
It was graded with 1.0 (Sehr Gut) and recognised for strong analytical design, data integrity, and DAX accuracy.

Future Enhancements

- Integrate automated data refresh via Power BI Service.
- Add What-If parameters for cost sensitivity and price elasticity.
- Extend dashboard to cover Cash Flow and Profit Variance analysis.
- Introduce Python integration for predictive financial modelling.

Institution

HTW Berlin – Hochschule für Technik und Wirtschaft Berlin
University of Applied Sciences


