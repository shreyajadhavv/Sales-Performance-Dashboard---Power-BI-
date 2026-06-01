# 📊 Sales Performance Dashboard — Power BI Assignment 2

An interactive **Sales Analytics Dashboard** built in Power BI, designed to provide end-to-end visibility into retail sales performance across regions, products, customers, and time periods.

## 🖥️ Dashboard Overview

This report is a single-page, fully interactive dashboard built on a **Star Schema** data model. It enables stakeholders to monitor KPIs, analyze trends, and drill into performance by region, product, and payment channel.

## 🗂️ Data Model

The report uses a classic **Star Schema** with one fact table and four dimension tables:

### Fact Table

| `FactSales` | OrderID, OrderDate, CustomerID, ProductID, StoreID, Quantity, UnitPrice, Discount, PaymentMode, DeliveryDays, SalesAmount, CostPrice, NetProfit |

### Dimension Tables
| `DimProduct` | ProductID, ProductName, Category, Brand, CostPrice |
| `DimCustomer` | CustomerID, CustomerName, Gender, Age, City, State, JoinDate |
| `DimStore` | StoreID, StoreName, City, Region, ManagerName |
| `DimDate` | Date, Year, Month Number, Month Name, Quarter, Day |

## 📐 DAX Measures

Custom DAX measures created in `FactSales`:
dax
TotalSales       = SUM(FactSales[SalesAmount])
TotalQuantity    = SUM(FactSales[Quantity])
TotalProfit      = SUM(FactSales[NetProfit])
AverageDeliveryDays = AVERAGE(FactSales[DeliveryDays])
ProfitMargin%    = DIVIDE([TotalProfit], [TotalSales], 0)

## 📊 Visuals Used
| **KPI Cards** | Total Sales, Total Profit, Total Quantity, Avg. Delivery Days, Profit Margin % |
| **Donut Chart** | Sales by Payment Mode (UPI, Credit Card, Card, etc.) |
| **Column Chart** | Total Sales by Region |
| **Line Chart** | Monthly Sales Trend (by Month Number) |
| **Clustered Bar Chart** | Top Products by Total Sales |
| **Table** | Product-level breakdown — Name, Category, Sales, Profit, Quantity |
| **Pivot Table** | Customer State × Order ID, Sales, Avg. Delivery Days |
| **Slicer** | Filter by Region |


## 🚀 How to Open

1. Download the `.pbit` file from this repository.
2. Open **Power BI Desktop**.
3. When prompted, connect to your data source or load sample data.
4. Explore the dashboard interactively!

## 🛠️ Tools & Technologies

- **Power BI Desktop**
- **DAX** (Data Analysis Expressions)
- **Star Schema** data modeling
- **Power Query** (data transformation)

## 📁 File Structure
📦 PowerBI-Sales-Dashboard
 ┣ 📄 PowerBi_ASSIGNMENT_2.pbit   ← Power BI Template file
 ┗ 📄 README.md
```
## 🙋‍♂️ Author

Built as part of a Power BI learning assignment.  
Feel free to fork, explore, and build on top of it!

