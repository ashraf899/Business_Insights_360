# Business_Insights_360
### **Project Overview**

AtliQ Hardware has experienced rapid growth in recent years and aims to solidify its position as a market leader. To achieve this, the company is implementing a data analytics solution using Power BI for the first time. This initiative is expected to empower stakeholders to make informed, data-driven decisions, giving AtliQ Hardware a competitive edge in the market.

The project focuses on addressing key questions from stakeholders across various domains, including Finance, Sales, Marketing, and Supply Chain Management.

I worked on this project by following the Codebasics Power BI Course. The link to the course is [here](https://codebasics.io/courses/power-bi-data-analysis-with-end-to-end-project).

You can view the live report here:  
[Live Report Link](https://app.powerbi.com/reportEmbed?reportId=02be4e10-01ea-40b3-8bc6-f42afdbe2e91&autoAuth=true&ctid=c6e549b3-5f45-4032-aae9-d4244dc5b2c4)

### Tech Stack

- **SQL**:
- **Excel**
- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**: Language used in Power BI for advanced data modeling and calculations.
- **DAX Studio**: A tool for optimizing DAX queries and performance tuning in Power BI reports.
- **Project Charter File**: A document that defines the scope, objectives, and stakeholders of the project, ensuring alignment across the team.


### Power BI Techniques Learned

- **Pre-project Questions:**
  - What are the project objectives and key deliverables?
  - Who are the stakeholders and what are their requirements?
  - What data sources will be used, and how will data be collected and cleaned?
  - What are the KPIs and success criteria for the project?
  - What is the timeline for the project, and what resources are required?
  - 
- **Creating Calculated Columns:**  
  - Adding calculated columns to your data model for custom calculations.

- **Creating Measures Using DAX:**  
  - Writing DAX formulas for dynamic calculations, aggregations, and advanced metrics.

- **Data Modeling:**  
  - Structuring data relationships, tables, and ensuring data integrity for reporting purposes.

- **Using Bookmarks to Switch Between Visuals:**  
  - Creating different views and using bookmarks to toggle between them.

- **Page Navigation with Buttons:**  
  - Setting up buttons for navigating between report pages.

- **Using the DIVIDE Function to Prevent Zero Division Errors:**  
  - Implementing the DIVIDE function in DAX to handle division by zero scenarios.

- **Creating Date Table Using M Language:**  
  - Automatically generating a date table in Power Query using M language for time-based analysis.

- **Dynamic Titles Based on Applied Filters:**  
  - Creating dynamic titles that change depending on the filters or slicers applied.

- **Using KPI Indicators:**  
  - Adding KPI visuals to track performance against target metrics.

- **Conditional Formatting Values in Visuals Using Icons or Background Color:**  
  - Applying conditional formatting to visual elements like tables or charts based on data thresholds.

- **Data Validation Techniques:**  
  - Ensuring data accuracy by applying validation techniques like range checks, data type checks, and consistency checks.

- **Power BI Services:**
  - **Publishing Reports to Power BI Services:**  
    - Uploading reports to Power BI service for online access and sharing.
  - **Setting Up Personal Gateway for Auto Refresh of Data:**  
    - Configuring gateways for automatic data refreshes.
  - **Power BI App Creation:**  
    - Creating and managing Power BI apps for distributing content to users.
  - **Collaboration, Workspace, and Access Permissions in Power BI Services:**  
    - Managing workspaces, user roles, and access permissions for report sharing and collaboration.

- **And More...** 😅
- 
### Business-Related Terms

- **Gross Price**
- **Pre-Invoice Deductions**
- **Post-Invoice Deductions**
- **Net Invoice Sale**
- **Gross Margin**
- **Net Sales**
- **Net Profit**
- **COGS (Cost of Goods Sold)**
- **YTD (Year to Date)**
- **YTG (Year to Go)**
- **Direct**
- **Retailer**
- **Distributors**
- **Consumer**

### **Company Background**

AltiQ Hardware is a rapidly growing company that has expanded its operations globally in recent years. The company specializes in selling computers and computer accessories through three primary channels:

- **Retailers**
- **Direct Sales**
- **Distributors**

Recently, AltiQ Hardware has faced an unforeseen loss from its store opening in the United States. This setback was based on surveys, intuition, and some preliminary Excel analysis. Meanwhile, the company's competitors have a well-established analytics team to perform in-depth analysis and make data-driven decisions. 

In light of this, AltiQ Hardware recognizes the need to build its own analytics team to leverage data insights for future decision-making and to remain competitive in the industry.

### **Project Kickoff Session**

The project kickoff session aims to clearly define the objectives and goals of the project. During this session, it’s crucial to answer key questions to ensure alignment and clarity for the entire team. These questions may include:

### **Questions to Ask Before Starting the Dashboard Project**

- **What is the primary objective of building this Power BI dashboard?**
- **How will the success of this project be measured (e.g., KPIs, business outcomes)?**
- **What is the expected timeline and deadline for completing the project?**
- **Do stakeholders expect to preview the dashboard before the final release? If so, when?**
- **What are the stakeholders' hopes and expectations for this project?**
- **What concerns or fears do stakeholders have regarding the development of this dashboard?**
- **Who will be using this dashboard, and what are their specific use cases or needs?**
- **What are the key expectations from stakeholders upon the completion of the project?**
- **What potential challenges or risks could arise during the development of the dashboard?**
- **What resources or data are required to successfully build this dashboard (e.g., data sources, tools)?**
- **Are there any specific inputs or preferences from stakeholders regarding the design, layout, and views of the dashboard?**

After the project kickoff meetings, the data engineering team will provide the data as per the request of the data analytics team. Let's begin exploring the provided data.

### **Dataset Understanding**

Understanding the available data is crucial for effective analysis. Before diving into the analysis, it’s important to thoroughly understand the structure and types of data available.

#### **Dimension Tables**
Dimension tables contain static data, which includes details of customers, products, markets, etc.

- **dim_customer**: 
  - 27 distinct markets (e.g., India, USA, Spain)
  - 75 distinct customers across the markets
  - 2 types of platforms: 
    - **Brick & Mortar**: Physical/offline stores
    - **E-commerce**: Online stores (e.g., Amazon, Flipkart)
  - Three sales channels: 
    - **Retailer**
    - **Direct**
    - **Distributors**

- **dim_market**:
  - 27 distinct markets (e.g., India, USA, Spain)
  - 7 sub-zones and 4 regions:
    - APAC
    - EU
    - NAN
    - LATAM

- **dim_product**:
  - **Divisions**: 
    - P & A (Peripherals and Accessories)
    - PC
    - Notebook
    - Desktop
    - N & S (Networking and Storage)
  - 14 different product categories (e.g., Internal HDD, keyboard)
  - Different variants available for the same product

#### **Fact Tables**
Fact tables store transactional data, which includes sales, forecasts, costs, etc.

- **fact_forecast_monthly**: 
  - Used to forecast customer demand in advance, which helps in:
    - Higher customer satisfaction
    - Reduced storage costs in warehouses
  - Denormalized by the data engineering team for analytical purposes.
  - Date of the month replaced with the start date of the month.
  - Includes forecast quantity needed by the customer.

- **fact_sales_monthly**: 
  - Similar to **fact_forecast_monthly**, but the final column contains the actual sold quantity instead of the forecast value.

#### **Additional Tables**

### **gdb041**

#### **dim_customer**
- **Markets**: 27 distinct markets (e.g., India, USA, Spain).
- **Customers**: 75 distinct customers throughout the markets.
- **Platforms**:
  - **Brick & Mortar**: Physical/offline stores.
  - **E-commerce**: Online stores (e.g., Amazon, Flipkart).
- **Sales Channels**:
  - **Retailer**
  - **Direct**
  - **Distributors**

#### **dim_market**
- **Markets**: 27 distinct markets (e.g., India, USA, Spain).
- **Sub-zones**: 7 sub-zones.
- **Regions**:
  - **APAC**
  - **EU**
  - **NAN**
  - **LATAM**

#### **dim_product**
- **Divisions**:
  - **P & A**:
    - **Peripherals**
    - **Accessories**
    - **PC**
    - **Notebook**
    - **Desktop**
  - **N & S**:
    - **Networking**
    - **Storage**
- **Categories**: 14 different categories (e.g., Internal HDD, Keyboard).
- **Variants**: Different variants are available for the same product.

#### **fact_forecast_monthly**
- Used for forecasting customer needs in advance, enabling:
  - Higher customer satisfaction.
  - Reduced warehouse storage costs.
- **Denormalized Structure**:
  - Designed by the data engineering team for analytical purposes.
- **Date Handling**:
  - All dates in the month are replaced with the start date of the month.
- **Forecast Quantity**:
  - Includes forecast quantity needed for each customer.

#### **fact_sales_monthly**
- Similar to the **fact_forecast_monthly** table.
- **Difference**:
  - The last column contains actual sold quantities instead of forecast values.

---

### **gdb056**

#### **freight_cost**
- Contains details of travel costs and other costs for each market with the fiscal year.

#### **gross_price**
- Provides details of gross prices associated with each product code.

#### **manufacturing_cost**
- Includes details of manufacturing costs for each product code along with the fiscal year.

#### **pre_invoice_deductions**
- Contains details of pre-invoice deduction percentages for each customer with the fiscal year.

#### **post_invoice_deductions**
- Provides details of post-invoice deductions and other deductions.


 
### **Importing Data into Power BI**

- As the database is MySQL in this project, we need to import the datasets from the MySQL database to Power BI by providing the database access credentials.  

### **Data Model**

- Data modeling plays a vital role and is considered the foundation of the report. All visuals will be built upon the data model.
- Poor data modeling affects the overall performance of the report.
- Following good practices of data modeling is a must. Refer to this click [here](https://addendanalytics.com/blog/data-modelling-best-practices) to learn more about good practices.
- In this project, we have followed Star and Snowflake data modeling method.

https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Model%20View.png?raw=true


### **Dashboard Designing**

Based on the mock-ups received as requirements, the team will start designing the visuals and create measures as needed.

- **Home View**:
  - Serves as the central hub.
  - Contains buttons for navigating to specific views.
  - Users can land on the desired view page by clicking the respective button.

- **Available Views**:
  - **Info**
  - **Finance View**
  - **Sales View**
  - **Marketing View**
  - **Supply Chain View**
  - **Executive View**
  - **Products**
  - **Support**

### Views

- **Home View**:
  ![Home View](https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Home.png?raw=true)

- **Finance View**:
  ![Finance View](https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Finance%20View.png?raw=true)

- **Sales View**:
  ![Sales View](https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Sales%20View.png?raw=true)

- **Marketing View**:
  ![Marketing View](https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Marketing%20View.png?raw=true)

- **Supply Chain View**:
  ![Supply Chain View](https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Supply%20Chain%20View.png?raw=true)

- **Executive View**:
  ![Executive View](https://github.com/ashraf899/Business_Insights_360/blob/main/Resource/BI%20360%20Executive%20View.png?raw=true)
