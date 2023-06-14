<h1 align="center">SQL Mock Questions</h1>

<br>

## Database Schema

<img src="https://user-images.githubusercontent.com/105283676/190654507-66e261f2-68ad-4e57-b8f9-1077acf9849b.png" alt="Database Design" align="center"/>

<br>

## Sample Customers Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929266-ac75d71e-3aa9-4db5-882a-6b37085d5351.png" alt="Database Design" align="center"/>

<br>

## Sample Orders Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929314-60bebbf6-5558-4f5d-8707-a368f0f97c48.png" alt="Database Design" align="center"/>

<br>

## Sample OrderDetails Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929361-b34a09a6-c05e-4a36-b775-30edd64b0b8b.png" alt="Database Design" align="center"/>

<br>

## Sample Products Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929434-843d756a-26ec-49ae-b50c-a77bb768dbb2.png" alt="Database Design" align="center"/>

<br>

## Sample Payments Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929508-7c3c4438-7d39-493b-8815-991080a94c80.png" alt="Database Design" align="center"/>

<br>

## Sample Shippers Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929577-200d2d3e-f929-4aa4-8e8b-5f35aa4a9f2d.png" alt="Database Design" align="center"/>

<br>

## Sample Suppliers Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929678-7b4f7074-9f29-46f3-b13e-9ff45079e252.png" alt="Database Design" align="center"/>

<br>

## Sample Category Table : 

<br>

<img src="https://user-images.githubusercontent.com/105283676/191929737-15c27c2b-c8f4-4749-b787-a8c6ce32fc0d.png" alt="Database Design" align="center"/>

<br>

## <!---------------------------------------------- Questions of Mock ---------------------------------------------->

<br>
<br>
<br>

## Print Customer ID, First Name, Last Name, City, State and Country details of customers who either belong to the city of Brussels or the state of Hamburg or the Country Australia.Sort the result set in ascending order of Customer ID.

<br>

```js
SELECT CustomerID,FirstName,LastName,City, State,Country 
FROM Customers 
WHERE CITY="Brussels" OR STATE="Hamburg" OR Country="Australia"
ORDER BY CustomerID ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/110474637/214608963-87f713c7-dd2e-4e7e-9deb-4c12dd8dc952.png" alt="Sample Output" align="center"/>

<br>
<br>

## Print all details of customers whose First names are 4 letter words which start with the letter 'R'.Sort the result set in ascending order of Customer ID.

<br>

```js
SELECT * 
FROM Customers 
WHERE LENGTH(FirstName) = 4 AND FirstName LIKE 'R%' 
ORDER BY CustomerID ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/110474637/214616405-5820934f-2a7a-4ed0-b3b7-9270f1e10312.png" align="center"/>

<br>
<br>

## Print all details of Orders which were placed by Customers whose ID is a multiple of 10, payment method by Payment with ID 4, shipped by Shipper with ID 3 and which are greater than 30,000 in order value.Sort the result set in descending order of Customer ID.

<br>

```js
SELECT * 
FROM Orders 
WHERE CustomerID%10=0 AND PaymentID=4 AND ShipperID=3 AND Total_order_amount>30000 
ORDER BY CustomerID DESC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/110474637/214618088-863d5e52-cb3d-4b30-819e-3b373186e287.png" align="center"/>

<br>
<br>

## Print Customer ID, First Name, Last Name, Date of Birth, City, State, Country and Email ID of customers from the Country 'Poland' whose first and last names start with the letter C.Sort the result set in ascending order of Customer ID

<br>

```js
SELECT CustomerID,FirstName,LastName,Date_of_Birth,City,State,Country,Email 
FROM Customers 
WHERE Country="Poland" AND FirstName Like "C%" AND LastName Like "C%" 
ORDER BY CustomerID ASC;
```

<br>
<br>

## Print the Total Revenue Generated and the Average Order Amount of orders which were paid with payment method 5 and were shipped by shipper with ID 1. You need to print 2 columns in the output - 1 for the Total Revenue Generated, 1 for the Average Order Amount.

<br>

```js
SELECT SUM(Total_order_amount) , AVG(Total_order_amount) 
FROM Orders 
WHERE PaymentID=5 AND ShipperID=1;
```

<br>
<br>

## Print distinct combinations of Order Date, Shipping Date and Delivery Date of Orders.Sort the result set in ascending order of Order Date.

<br>

```js
SELECT DISTINCT OrderDate,ShipDate,DeliveryDate 
FROM Orders 
ORDER BY OrderDate ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/79314126/214805801-69b9ccae-ad15-46a2-b1bf-ab0ccf5b44be.png" align="center"/>

<br>
<br>

## Print the Customer First Name which comes last according to the alphabetical order.

Hint: Apply MAX function on the relevant column.

<br>

```js
SELECT MAX(FirstName) 
FROM Customers;
```

<br>
<br>

## Print all details of customers whose Postal code starts with the number 7 and who reside in the cities of Belfast or New York.Sort the result set in ascending order of CustomerID.

<br>

```js
SELECT * 
FROM Customers 
WHERE PostalCode Like "7%" AND (City="Belfast" OR City="New York") 
ORDER BY CustomerID ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215025125-e1b6d00a-473a-4a71-b1b4-b11bd3b3dac7.png" align="center"/>

<br>
<br>

## Print CustomerID, First Name, Last Name, City, Email and Phone number of Customers whose Phone number starts with the digit 9 and ends with the digit 8.Sort the output on ascending order of CustomerID.

<br>

```js
SELECT CustomerID,FirstName,LastName,City,Email,Phone 
FROM Customers 
WHERE Phone Like "9%" and Phone Like "%8" 
ORDER BY CustomerID ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215025543-d4aee4b2-cb43-45ee-95cd-48ce2c99dbe1.png" align="center"/>

<br>
<br>

## Print all details of Customers whose first name is a 4 letter word which starts with the letter A or whose last name is a 5 letter word.Sort the result in ascending order of CustomerID.

<br>

```js
SELECT * 
FROM Customers 
WHERE (LENGTH(FirstName)=4 AND FirstName Like "A%") OR LENGTH(LastName)=5 
ORDER BY CustomerID ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215025894-9897c371-b34a-4600-9590-de2e30d6bfcf.png" align="center"/>

<br>
<br>

## Print all details of Products which contain 'Rice' in their names, are produced by the brand 'Safe Harvest' and whose market price is less than 85. Sort the result in ascending order of ProductID.

<br>

```js
SELECT * 
FROM Products 
WHERE Product Like "%Rice%" AND Brand='Safe Harvest' AND Market_Price<85 
ORDER BY ProductID ASC;
```

<br>

SAMPLE OUTPUT - (Final Result might be More the 4 rows): 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215026491-02f4c28f-b286-4567-8dc9-099796fc21ef.png" align="center"/>

<br>
<br>

## Print all details of Customers whose last name is either Williams or Lawson and who reside in the United States.Sort the result set in ascending order of CustomerID.

<br>

```js
SELECT * 
FROM Customers 
WHERE (LastName='Williams' OR LastName='Lawson') AND Country='United States' 
ORDER BY CustomerID ASC;
```

<br>

SAMPLE OUTPUT - (Final Output might be more than one rows): 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215026882-426bb1a7-c9f8-49dd-b586-8e781f3063da.png" align="center"/>

<br>
<br>

## Print the average spend per order and the total spend across all orders, made by Customer with ID 57100.

<br>

```js
SELECT AVG(Total_order_amount) , SUM(Total_order_amount) 
FROM Orders 
WHERE CustomerID = 57100;
```

<br>

SAMPLE OUTPUT - (Numbers are not actual) : 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215027320-d71881a2-dd58-4bb6-8e76-3972176d58bd.png" align="center"/>

<br>
<br>

## Print the count of Suppliers whose contact email address ends with '.com' .

<br>

```js
SELECT COUNT(Email) 
From Suppliers 
WHERE Email Like "%.com";
```

<br>
<br>

## Identify unique dates on which details of the customers were entered into the database.Sort the resut in descending order of Date Entered.

<br>

```js
SELECT DISTINCT DateEntered FROM Customers 
ORDER BY DateEntered DESC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/118887002/215027841-98edb59f-7dd9-4b05-92eb-b6c1d7317ab6.png" align="center"/>

<br>
<br>

## Print the average sale price and the average market price of products produced by the Brand Fresho.

<br>

```js
SELECT AVG(Sale_Price) , AVG(Market_Price) 
FROM Products 
WHERE Brand='Fresho';
```

<br>
<br>

## Print all details of customers whose Phone Numbers consist of the digit 9 at least four times.Sort the result set in ascending order of Phone Number.

<br>

```js
SELECT * 
FROM Customers 
WHERE Phone LIKE '%9%9%9%9%' 
ORDER BY Phone ASC;
```

<br>

SAMPLE OUTPUT : 

<br>

<img src="https://user-images.githubusercontent.com/110474637/214611300-1f00fa75-ccf0-455a-bb5b-2321e134e3c6.png" align="center"/>