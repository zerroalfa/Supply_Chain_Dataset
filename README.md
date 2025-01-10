# Supply_Chain_Dataset
this is my 5th project with Quantum Analytics

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Recommendations](#recommendations)

### Project Overview
---

**Project Overview: Supply Chain Analysis for Enhanced Efficiency and Value Creation**  

This project focuses on analyzing the supply chain, which encompasses the network of production, logistics, and delivery systems involved in bringing goods to customers. By conducting a detailed **Supply Chain Analysis**, we aim to evaluate various components of the supply chain to identify areas for improvement, enhance operational efficiency, and create greater value for customers.  

### Objectives:  
1. **Evaluate Supply Chain Performance**: Assess key performance metrics such as production efficiency, delivery timelines, and inventory management.  
2. **Identify Bottlenecks**: Pinpoint inefficiencies and delays in the supply chain to streamline operations and reduce costs.  
3. **Optimize Logistics**: Analyze transportation and distribution channels to ensure timely delivery while minimizing expenses.  
4. **Improve Customer Satisfaction**: Enhance the end-to-end supply chain process to meet customer expectations in terms of quality, cost, and delivery.  
5. **Sustainability Analysis**: Incorporate environmental impact metrics to identify ways to reduce carbon footprint and embrace green logistics.  

### Key Areas of Analysis:  
- **Production Efficiency**: Analyze manufacturing processes to ensure optimal resource utilization and reduce waste.  
- **Inventory Management**: Assess stock levels and turnover rates to avoid overstocking or stockouts.  
- **Transportation and Logistics**: Evaluate delivery routes, freight costs, and transportation methods for optimization.  
- **Supplier Performance**: Monitor supplier reliability and lead times to strengthen the supply chain network.  
- **Customer Demand Patterns**: Align production and delivery schedules with customer demand to improve service levels.  

### Value of the Analysis:  
This project delivers actionable insights for:  
- **Businesses**: Enhancing operational efficiency and reducing costs to remain competitive.  
- **Supply Chain Managers**: Identifying areas for process improvement and ensuring seamless operations.  
- **Sustainability Teams**: Integrating eco-friendly practices and reducing emissions in the supply chain.  

### Potential Use Cases:  
1. **Cost Reduction**: Identify cost-saving opportunities in procurement, transportation, and warehousing.  
2. **Lead Time Optimization**: Reduce delays by improving coordination between suppliers, manufacturers, and distributors.  
3. **Customer-Centric Supply Chain**: Align supply chain strategies with customer expectations to boost satisfaction.  
4. **Risk Management**: Mitigate risks by identifying and addressing vulnerabilities in the supply chain network.  
5. **Data-Driven Decision Making**: Leverage insights to make informed strategic decisions and plan for future growth.  

This project will result in a more efficient, resilient, and customer-focused supply chain, driving business growth and sustainable operations while delivering greater value to customers.

![Dashboard]![5 Supply Chain Dataset](https://github.com/user-attachments/assets/6fab3a35-5273-4974-918e-45e1d9a0ffc0)



### Data Sources

Supply Chain dataset: The primary dataset used for this analysis is the "supply_chain_data.csv" file, containing detailed information about Supply Chain.

### Tools

- Excel - Data Cleaning
  - [Download here](https://microsoft.com)
- SQL Server - Data Analysis
- PowerBI - Creating reports


### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis

EDA involved exploring the sales data to answer key questions, such as:

- What is the overall sales trend?
- Which products are top sellers?
- What are the peak sales periods?

### Data Analysis

Include some interesting code/features worked with

**Price vs. Revenue Analysis**
```sql
SELECT 
    Price,
    SUM(Revenue_generated) AS Total_Revenue
FROM 
    supply_chain_data
GROUP BY 
    Price;
```

**Percentage of Sales by Product**
```sql
SELECT 
    Product_type,
    (SUM(Number_of_products_sold) * 100.0 / (SELECT SUM(Number_of_products_sold) FROM supply_chain_data)) AS Sales_Percentage
FROM 
    supply_chain_data
GROUP BY 
    Product_type;
```

**Stock Level by SKU**
```sql
SELECT 
    SKU,
    Stock_levels
FROM 
    supply_chain_data;
```

**Revenue by Carrier**
```sql
SELECT 
    Shipping_carriers,
    SUM(Revenue_generated) AS Total_Revenue
FROM 
    supply_chain_data
GROUP BY 
    Shipping_carriers;
```

**Revenue by SKU**
```sql
SELECT 
    SKU,
    SUM(Revenue_generated) AS Total_Revenue
FROM 
    supply_chain_data
GROUP BY 
    SKU;
```

**Shipping Cost by Carrier**
```sql
SELECT 
    Shipping_carriers,
    SUM(Shipping_costs) AS Total_Shipping_Cost
FROM 
    supply_chain_data
GROUP BY 
    Shipping_carriers;
```

**Cost Distribution by Transport Mode**
```sql
SELECT 
    Transportation_modes,
    SUM(Shipping_costs) AS Total_Cost
FROM 
    supply_chain_data
GROUP BY 
    Transportation_modes;
```

**Defect Rate by Product and Transport Mode**
```sql
SELECT 
    Product_type,
    Transportation_modes,
    AVG(Defect_rates) AS Average_Defect_Rate
FROM 
    supply_chain_data
GROUP BY 
    Product_type, Transportation_modes;
```

**Total Revenue**
```sql
SELECT 
    SUM(Revenue_generated) AS Total_Revenue
FROM 
    supply_chain_data;
```

**Total Defect Rate**
```sql
SELECT 
    AVG(Defect_rates) AS Total_Defect_Rate
FROM 
    supply_chain_data;
```

**Total Revenue by SKU**
```sql
SELECT 
    SKU,
    SUM(Revenue_generated) AS Total_Revenue
FROM 
    supply_chain_data
GROUP BY 
    SKU;
```

**Total Cost per Unit**
```sql
SELECT 
    SKU,
    SUM(Shipping_costs) / SUM(Number_of_products_sold) AS Total_Cost_Per_Unit
FROM 
    supply_chain_data
GROUP BY 
    SKU;
```

**Profit per Unit**
```sql
SELECT 
    SKU,
    (SUM(Revenue_generated) - SUM(Shipping_costs)) / SUM(Number_of_products_sold) AS Profit_Per_Unit
FROM 
    supply_chain_data
GROUP BY 
    SKU;
```

**Sales Percentage**
```sql
SELECT 
    SKU,
    (Number_of_products_sold * 100.0 / (SELECT SUM(Number_of_products_sold) FROM supply_chain_data)) AS Sales_Percentage
FROM 
    supply_chain_data;
```


### Results/Findings

The analysis results are summarized as follows:

**Price vs. Revenue Analysis**

Certain price points correlate with higher revenue, indicating optimal pricing strategies for specific products.

**Percentage of Sales by Product**

A few product types may dominate sales, suggesting a concentration of consumer preference.

**Stock Level by SKU**

Some SKUs may be overstocked or understocked, affecting inventory management efficiency.

**Revenue by Carrier**

Specific carriers may generate significantly more revenue, indicating potential partnerships or negotiations for better rates.

**Revenue by SKU**

Certain SKUs contribute disproportionately to total revenue, highlighting key products for marketing focus.

**Shipping Cost by Carrier**

Variations in shipping costs among carriers can impact profitability, suggesting the need for cost analysis.

**Cost Distribution by Transport Mode**

Different transport modes incur varying costs, which could inform logistics strategies.

**Defect Rate by Product and Transport Mode**

Identifying products with higher defect rates can guide quality control measures.

**Total Revenue**

The overall revenue figure provides a benchmark for financial performance.

**Total Defect Rate**

A high average defect rate may indicate systemic issues requiring immediate attention.

**Total Revenue by SKU**

This analysis identifies top-performing SKUs, crucial for inventory and sales strategies.

**Total Cost per Unit**

Understanding costs per unit helps in pricing strategies and profit margin calculations.

**Profit per Unit**

Identifying profitable SKUs assists in focusing on high-margin products.

**Sales Percentage**

Insights into sales distribution can guide marketing and promotional strategies.

### Recommendations

Based on the analysis, we recommend the following actions:


**Pricing Strategy Optimization**

Adjust prices based on the findings from the Price vs. Revenue analysis to maximize revenue.

**Inventory Management**

Implement just-in-time inventory practices for overstocked items and increase stock for high-demand SKUs.

**Carrier Negotiations**

Explore partnerships with high-revenue carriers and negotiate better shipping rates with costlier ones.

**Quality Control Improvements**

Focus on products with high defect rates to enhance quality assurance processes.

**Marketing Focus**

Increase marketing efforts on top-performing SKUs to capitalize on their popularity.

**Cost Analysis**

Conduct a detailed analysis of shipping costs by carrier and transport mode to identify savings opportunities.

**Sales Promotions**

Develop targeted promotions for lower-selling products to boost their performance.

**Regular Reviews**

Establish a routine for reviewing sales and inventory data to stay responsive to market changes.

### Limitations

**Data Quality**

The accuracy of the findings is contingent on the quality and completeness of the data collected.

**External Factors**

Market conditions, consumer behavior changes, and economic factors can influence results and may not be reflected in the data.

**Temporal Analysis**

The analysis may not account for seasonal variations in sales and demand, potentially skewing results.

**Assumptions in Calculations**

Some calculations, such as averages, may obscure significant variations within the data.

**Limited Scope**

The analysis focuses solely on the provided dataset and may not encompass broader supply chain dynamics.

**Static Analysis**

The findings are based on historical data and may not accurately predict future trends without continuous monitoring.
### References

`column_1`

**bold**

*italic*
