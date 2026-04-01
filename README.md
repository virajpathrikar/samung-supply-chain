 # Samsung Supply Chain & Logistics Dashboard
### Built with Microsoft Power BI

---

## Project Overview

This is an end-to-end **Supply Chain & Logistics Analytics Dashboard** built in **Microsoft Power BI**, modeled around Samsung's global product ecosystem. The dashboard provides a comprehensive view of supplier performance, inventory health, shipment operations, and customer revenue — enabling data-driven decisions across the supply chain.

The project was built using a **synthetic dataset** designed to simulate realistic supply chain scenarios for Samsung's product lines including smartphones, wearables, tablets, and home appliances.

---

## Objective

To design an interactive, multi-page Power BI dashboard that:
- Tracks **key supply chain KPIs** at a glance
- Identifies **bottlenecks** in supplier lead times, shipment delays, and inventory levels
- Monitors **product-level inventory** vs. safety stock and reorder points
- Analyzes **revenue performance** by customer/platform
- Supports **operational decision-making** with drill-through and visual filtering

---

## Dashboard Pages

### 1. Home
A clean landing page featuring the Samsung branding and navigation buttons to all dashboard sections: Overview, Supplier, Inventory, and Shipment.

---

### 2. 📈 Overview
A high-level summary of all key metrics across the supply chain.

| KPI | Value |
|-----|-------|
| Gross Revenue | 186.86M |
| Total Revenue | 176.95M |
| Profit | 48.56M |
| Profit Margin % | 27.44% |
| Perfect Order % | 75% |
| Total Shipments | 8K |
| Order Quantity | 129K |
| Inventory Stock | 160K |
| Shipment Quantity | 3M |
| Delivered Quantity | 187K |

**Key Visuals:**
- Avg Lead Time by Supplier (bar chart)
- Top products by Inventory Stock
- Total Delay by Carrier
- Total Revenue by Customer/Platform

---

### 3. 🏭 Supplier
Deep-dive into supplier performance, cost analysis, and lead time benchmarking.

| KPI | Value |
|-----|-------|
| Total Unit Cost | 78.13M |
| Order Quantity | 129K |
| Avg Lead Time | 11.53 days |
| Avg Quality Score | 96.63 |
| Avg Unit Cost | 880.71 |
| Count of Suppliers | 7 |

**Key Visuals:**
- Unit Cost by Month (line chart) — peaks in Apr & Aug at 8.0M
- Supplier AVG Lead Time — Samsung India & Vietnam fastest at 9 days
- Supplier Order Quantity — Samsung Vietnam leads at 20K
- Supplier Unit Cost — BOE Technology highest at 11M
- Avg Lead Time by Country — India & Vietnam outperform at 9 days vs. 12 for China, Japan, South Korea, Taiwan

**Suppliers Covered:**
- BOE Technology (China)
- Samsung Electronics (South Korea)
- Sony Semiconductor (Japan)
- Taiwan Semiconductor (Taiwan)
- SK Hynix Inc. (South Korea)
- Samsung India (India)
- Samsung Vietnam (Vietnam)

---

### 4. Inventory
Tracks product-level stock levels, safety stock, reorder points, and defect rates.

| KPI | Value |
|-----|-------|
| Inventory Stock | 160K |
| Safety Stock | 89K |
| Turnover Rate | 117.0% |
| Days of Inventory | 311.88 |
| Defective Units | 24.10K |
| Avg Defective Units | 5.36 |

**Key Visuals:**
- Average Defective Units by Month — peaks in March (7.0) and October (6.4)
- Inventory Stock by Month — peaks in Feb (19.2K) and Mar (19.4K)
- Product Defect Rate — Galaxy S24 Ultra leads with 4.3K defects
- Inventory Stock Chart — Current Stock vs. Safety Stock vs. Reorder Point per product

**Top Products by Stock:**
| Product | Stock |
|---------|-------|
| Galaxy S24 Ultra | 25K |
| Galaxy Buds2 Pro | 22K |
| Galaxy Watch6 Classic | 20K |
| Galaxy S23 | 15K |
| Galaxy Z Flip5 | 14K |

---

### 5. Shipment
Analyzes shipping performance, carrier delays, delivery rates, and cost trends.

| KPI | Value |
|-----|-------|
| Total Shipments | 8K |
| Shipment Cost | 19.42M |
| Total Delays | 573 |
| Shipment Quantity | 3M |
| Delivered Shipments | 5,647 |
| Delivered % | 75.29% |

**Key Visuals:**
- Total Delay by Carrier — Maersk Line highest at 87 delays
- Total Delay by Reason — Carrier Capacity (90) is the top reason
- Shipment Cost by Month — rises sharply toward Dec (~2.0M)
- Total Shipment by Status (donut chart) — Delivered, In Transit, Delayed, Processing

**Delay Reasons Breakdown:**
| Reason | Delays |
|--------|--------|
| Carrier Capacity | 90 |
| Documentation Issue | 78 |
| Port Congestion | 73 |
| Customs Clearance | 71 |
| Weather Disruption | 68 |
| Mechanical Failure | 67 |
| Security Check | 67 |
| Address Exception | 59 |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Microsoft Power BI Desktop | Dashboard development & visualization |
| DAX (Data Analysis Expressions) | Calculated measures & KPIs |
| Power Query (M Language) | Data transformation & cleaning |
| Synthetic Dataset (CSV/Excel) | Simulated supply chain data |

---

## 📐 DAX Measures Used

```dax
-- Profit Margin %
Profit Margin % = DIVIDE([Profit], [Gross Revenue]) * 100

-- Perfect Order %
Perfect Order % = DIVIDE([Delivered Quantity], [Total Shipment Quantity]) * 100

-- Avg Lead Time
Avg Lead Time = AVERAGE(Supplier[lead_time_days])

-- Turnover Rate
Turnover Rate = DIVIDE([Total Revenue], [Inventory Stock])

-- Days of Inventory
Days of Inventory = DIVIDE([Inventory Stock], DIVIDE([Total Revenue], 365))
```

---

## Data Model

The dashboard follows a **Star Schema** structure:

- **Fact Tables:** Orders, Shipments, Inventory Transactions
- **Dimension Tables:** Products, Suppliers, Customers, Carriers, Date

**Relationships:**
- One-to-Many between dimension and fact tables
- Date table linked to all time-based fact tables for consistent time intelligence

---

## Project Structure

```
Samsung-Supply-Chain-Dashboard/
│
├── Samsung_Supply_Chain.pbix       # Main Power BI file
├── Dataset/
│   ├── supplier_data.csv
│   ├── inventory_data.csv
│   ├── shipment_data.csv
│   └── customer_data.csv
├── Screenshots/
│   ├── home.png
│   ├── overview.png
│   ├── supplier.png
│   ├── inventory.png
│   └── shipment.png
└── README.md
```

---

## Key Insights

1. **Samsung Vietnam** has the highest order quantity (20K) while also offering the fastest lead time (9 days) — ideal supplier.
2. **Maersk Line** has the most delays (87) — consider diversifying carrier mix.
3. **Galaxy S24 Ultra** leads in both inventory stock (25K) and defect rate (4.3K) — quality investigation needed.
4. **Carrier Capacity** is the #1 delay reason (90 delays) — a logistics planning opportunity.
5. **Amazon** is the top revenue platform (37M), closely followed by Flipkart and Best Buy.
6. Shipment cost spikes significantly in **Q4 (Nov–Dec)**, suggesting seasonal demand surges.
7. **Inventory turnover rate of 117%** indicates healthy stock movement overall.

---

## 👤 Author

**Viraj**
 Data Analyst 
Skills: Power BI | SQL (MySQL) | Python | Advanced Excel

 Pune, India


---
