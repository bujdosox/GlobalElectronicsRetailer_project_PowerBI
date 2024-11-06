## Global Electronics Retailer project
### Sales of fictive electronics retailer company 
The analysis provides a deep insight into the key areas of the company and gives valuable information about it’s performance. Looking for trends and patterns regarding sales, profit and orders can be the base of predictions for the following period. Based on gained information business decisions and further inspections also can be made in order to improve necessary areas and increase market share of the company. With comparing previous month sales/profit and targets actual performance can be easily followed.

![Riport 1](https://github.com/user-attachments/assets/a62f82ca-19c1-45b5-8193-1d9661dfd0aa)
![Riport 2](https://github.com/user-attachments/assets/015ca823-b803-4061-a8df-0fa9cc2e1632)
![Riport 3](https://github.com/user-attachments/assets/7fb61a08-2b7c-4782-95e4-75c1ed443e35)
![Riport 4](https://github.com/user-attachments/assets/64b0c607-d994-4b6c-bb05-40e270d9161f)
![Riport 5](https://github.com/user-attachments/assets/1bd8e7e4-daa3-4db1-bac9-f0896c8b2038)
### Goal
-	Looking for patterns by temporal distribution of transactions (orders, sales, profit, average profit)
-	Following month over month sales and profit, in addition year over year sales
-	Looking for best selling product categories
-	Getting overall picture about individual products sales and top selling products by cathegory
-	Scenario analysis - how unit price change of an individual product affects it’s profit
-	Defining average delivery time
-	Getting information about customers (geographic distribution, top customers by continents and countries, sales distribution by age groups and genders)
-	Defining in-store vs. online sales ratio
-	Getting insight into performance and contribution % of countries and states
-	Looking for connection between m2 of stores and order volumes
### Outcome
-	Sales, profit and amount of orders basically show increasing tendency with periodic regressions in the whole investigation period (January of 2016 – February of 2021). Peaks detected in winter seasons presumably due to the Chrismas holidays, lowest points are consistently in March and April. Average daily profit/moving average daily profit and sales% month over month also highlight this pattern by definition.
-	Outstandingly Computer is the best selling product category ($ 19.3M), which is followed by Home appliences ($ 10.8M). Cameras, Cell phones and TV/video stand head to head on the 3. place with almost the same amount (~$ 6.0-6.5M).
-	Top 3 products by each categories can be seen in a matrix visualization, but decomposition tree about sales + matrix about quantity sold and profit gives a best detailed picture on individual product level. Previous data also can be obtained by brands.
-	Impact of unit price change of individual products can be investigated as scenario-testing. According to the %-change of the unit price profit increasement/decreasement can be realized.
-	The average delivery time within the investigation period is 4,53 days.
-	The distribution map shows that customers are almost completely from North America, Europe and Australia with a few exceptions. List of top customers also confirms this statement.
-	Investigation of sales by age group shows a relatively balanced picture except 0-25 age range:
o	0-25 age range: ~5%
o	25-45 age range: ~30%
o	45-65 age range: ~29%
o	65+ age range: 35%
-	Distribution of sales shows that United States provides the most significant part, which is followed by online transactions and United Kingdom with a serious difference:
o	United States: 42.62% ($ 23.76M)
o	Online: 20.45% ($ 11.40M)
o	United Kingdom: 10.31% ($ 5.75M)
o	Other 6 countries: under 10% ($ 14.85M)
-	The online transactions vs. in-store shopping ratio is 20.45% vs. 79.55%
-	Sales of regions within each countries also can be followed, best and least performed states can be detected and further actions can be made if necessary
-	Number of orders and size of stores shows a mild correlation, but exact pattern isn’t detectable
### Methods and steps
-	Loading row data as multiple CSV files into Power BI Desktop
-	Checking coloumn quality, coloumn distribution, coloumn profile and data types regarding the whole data set in Power Query editor
-	Transforming data in Power Query editor in order to prepare analysis
-	As calendar table wasn’t available, it had to be created with DAX measure in order to ensure continuity of dates, proper filter context and data normalization (preserve data integrity)
-	Creating data model in Model view
o	Connecting data/fact table (Sales) to dimension/lookup tables (Customers, Products, Stores, Calendar) based on common ID’s and dates
o	Organizing dimension tables above the fact table in order to vizualize filters flow from up to down
o	Setting one-to-many cardinality and one-way filter dierctions
o	Hiding all foreign keys from Report view prevent to use them for filtering

![Model](https://github.com/user-attachments/assets/0dd28f2d-aecd-4b9b-8da5-adf1fe1b03f7)
-	Creating separate table for measures + create DAX calculations in order to use them anywhere in the report, referenced by other DAX measures and provide more complex calculations. Some of the most important measures:

![Calendar](https://github.com/user-attachments/assets/2ce92f92-176b-45db-92da-0e43ed7919e6)
![Total Sales](https://github.com/user-attachments/assets/8e2aa6c9-2ed9-4b22-8978-a64fd1587ce9)
![Top 3 Products by Sales](https://github.com/user-attachments/assets/9a32440a-3e22-4dbe-b146-652db4034a7d)
![Sales % of Countries](https://github.com/user-attachments/assets/9150898a-66f0-401d-a2ba-2d4cf7e5834f)
![Sales % of States](https://github.com/user-attachments/assets/f0cecb47-28f0-4671-b843-e35f557fc57c)
![Price adjustment](https://github.com/user-attachments/assets/a367b0e3-f816-4c35-b8e8-c3e7b44c46f2)
![Moving AVG profit](https://github.com/user-attachments/assets/defba4d9-8cb0-4da1-88fa-69d71f88261a)
![AVG delivery day](https://github.com/user-attachments/assets/6b17a256-3f93-448d-85ef-7b3d403050fe)
-	Beyond common visualization methods some practical solution was applied too.
-	Sales, Profit and Order measures were used as field parameters to create the Metric Selection table, which was the input of a line chart. In this way users easily can change between measures above on the same chart, keeping the dashboard clear without overcrowding.
-	Decomposition tree ensures parallelly a global picture and a detailed insight into sales of product categories, subcategories and individual products.
-	Scenario analysis also can be applied due to possibility to change the unit price of indivudal products or all products thereby checking impact on profit.
