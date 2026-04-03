# Data Model Description

This document provides a comprehensive description of the data model used in the Airport Coffee Shop Sales Performance Analysis project.

## Tables Overview

The data model consists of the following tables:

1. **Sales**  
   - **Attributes:**  
     - SaleID (INT) - Unique identifier for each sale  
     - ProductID (INT) - Foreign key referencing Product table  
     - Date (DATE) - Date of sale  
     - Quantity (INT) - Quantity sold  
     - TotalAmount (DECIMAL) - Total sales amount  
   
2. **Products**  
   - **Attributes:**  
     - ProductID (INT) - Unique identifier for each product  
     - ProductName (VARCHAR) - Name of the product  
     - Category (VARCHAR) - Category of the product (e.g., Beverage, Snack)  
     - Price (DECIMAL) - Price of the product  
   
3. **Customers**  
   - **Attributes:**  
     - CustomerID (INT) - Unique identifier for each customer  
     - FirstName (VARCHAR) - Customer's first name  
     - LastName (VARCHAR) - Customer's last name  
     - Email (VARCHAR) - Customer's email address  
   
4. **Employees**  
   - **Attributes:**  
     - EmployeeID (INT) - Unique identifier for each employee  
     - Name (VARCHAR) - Name of the employee  
     - Role (VARCHAR) - Role of the employee (e.g., Barista, Manager)  
     - HireDate (DATE) - Date when the employee was hired  

## Data Types
- INT: Integer type  
- VARCHAR: Variable character string  
- DATE: Date type  
- DECIMAL: Decimal number type

## Relationships
- **Sales** table has a many-to-one relationship with the **Products** table (many sales can be associated with one product).
- **Sales** table also has a many-to-one relationship with the **Customers** table (many sales can be performed by one customer).
- **Employees** may be linked to sales for tracking who made each sale if this is included in future data collection.

## Star Schema Structure

The data model follows a Star Schema structure with the **Sales** table as the central fact table. The surrounding dimension tables are **Products**, **Customers**, and **Employees**:
- **Fact Table:** Sales
- **Dimension Tables:**  
  - Products  
  - Customers  
  - Employees

This structure allows for efficient querying and reporting, enabling trend analysis over sales, customer behavior, and employee performance.
