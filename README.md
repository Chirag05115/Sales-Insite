# Sales-Insite
Developed a data-driven Sales Insights project to analyze sales performance, identify trends, and support business decision-making using real-world or simulated sales data

CREATE TABLE SalesData (
    SaleID INT PRIMARY KEY,
    SaleDate DATE,
    ProductName NVARCHAR(50),
    Quantity INT,
    UnitPrice DECIMAL(10, 2),
    Discount DECIMAL(5, 2),
    Region NVARCHAR(50),
    Salesperson NVARCHAR(50)
);
INSERT INTO SalesData

(SaleID,SaleDate,ProductName,Quantity,unitPrice,Discount,Region,Salesperson)
VALUES(1,'2023-02-03','Furniture',18,267.22,0.9,'North','BOB')
(2,'2023-04-21','Furniture',17,3816.39,0.11,'North','BOB'),
(3,'2023-09-21','Food',30,371.4,0.2,'South','David'),
(4,'2023-08-24','Clothing',39,4467.75,0.2,'South','Rody'),
(5,'2023-03-24','Electronics',13,692.71,0.8,'East','Charlie'),
(6,'2023-02-11','Food',32,1106.51,0.21,'West','Emma'),
(7,'2023-04-11','Furniture',29,2624.09,0.14,'West','BOB'),
(8,'2023-01-06','Furniture',46,3964.650,0.12,'South','Eve'),
(9,'2023-06-29','Furniture',30,1095.45,0.5,'South','David'),
(10,'2023-10-09','Clothing',18,2682.34,0.13,'West','Charlie'),
(11,'2023-11-16','Furniture',13,2517.6,0.23,'North','Eve'),
(12,'2023-08-14','Food',43,1137.44,0.08,'West','BOB'),
(13,'2023-11-11','Food',21,641.09,0,'West','Eve'),
(14,'2023-12-31','Furniture',30,4270.65,0.2,'South','Alice'),
(15,'2023-08-17','Food',21,2869.6,0.29,'South','Charlie'),
(16,'2023-10-16','Furniture',48,487.65,0.18,'North','David'),
(17,'2023-05-30','Furniture',17,4420.15,0.4,'North','Rody'),
(18,'2023-10-04','Electronics',40,5034.35,0.1,'East','Alice'),
(19,'2023-07-17','Clothing',19,3209.22,0.26,'West','Charlie'),
(20,'2023-03-11','Clothing',15,2790.1,0.7,'South','BOB'),
(21,'2023-04-22','Electronics',9,4439.12,0.18,'North','Eve'),
(22,'2023-01-04','Electronics',10,5074.42,0.12,'East','Rody')

**Monthly Top Sales**
SELECT 
    FORMAT(SaleDate, '2023-2') AS [Month],
    SUM(Quantity * UnitPrice * (1 - Discount)) AS TotalSales
FROM 
    SalesData
GROUP BY 
    FORMAT(SaleDate, '2023-2')
ORDER BY 
    [Month];

**Top Products**
SELECT 
    ProductName,
    SUM(Quantity * UnitPrice * (1 - Discount)) AS Revenue
FROM 
    SalesData
GROUP BY 
    ProductName
ORDER BY 
    Revenue DESC

**Revenue By Region**
SELECT 
    Region,
    SUM(Quantity * UnitPrice * (1 - Discount)) AS Revenue
FROM 
    SalesData
GROUP BY 
    Region

