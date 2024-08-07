# SUPERMART-GROCERY-SALES-REPORT


# PROBLEM STATEMENT
This will help to identify trends, patterns and insights that can optimize inventory management, sales strategies and customer behavior with a focus on optimizing revenue and improving customer satisfaction.  
The Dataset contains the following columns:
* Customer Name
* Category
* Sales
* Profit
* Order Date etc.

Deliverables:
* Getting the Total sales per day
* Knowing the Top5 city by sales using Seaborn Library
* Showing the Discounts for all Regions
* Highlighting the Top10 Customers with the highest Profit.
* Getting the Sales Per Year and
* Getting the Category by Sales.

# LIBRARY USED
- Pandas
- Numpy
- Matplotlib
- Seaborn

# STEPS
- Loading in the Dataset and using the first column as my index column
- Changing the Order Date column type to a datetime type.
#### DELIVERY 1 - (TOTAL SALES PER DAY)
- SuperGrocery["Day_Name"]=SuperGrocery["Order Date"].dt.day_name()
- DaySales=SuperGrocery.groupby("Day_Name")["Sales"].sum()
- DaySales
- Name=DaySales.index
- Number=DaySales.values
- plt.bar(Name,Number,color="lime")
- plt.title("SALES PER DAY",fontstyle="italic", fontweight="bold", fontsize=15, c="black")
- plt.xlabel("Days")
- plt.ylabel("Sales per day")
- plt.savefig("Saales Per Day.png")
- plt.show()

![Saales Per Day](https://github.com/user-attachments/assets/4dcee6bb-1373-4108-8d54-2692f2029184)

#### DELIVERY 2 - (TOP5 CITY BY SALES)
- Top5=SuperGrocery.sort_values("Sales",ascending=False).head(5)
- Top5
- sns.barplot(x=Top5["City"],y=Top5["Sales"],data=Top5,palette="summer")
- plt.title("TOP 5 CITY BY SALES",fontsize=15,fontweight="bold",c="g")
- plt.xlabel("City")
- plt.ylabel("Sales")
- plt.savefig("T5 city by sales.png")
- plt.show()

![T5 city by sales](https://github.com/user-attachments/assets/08677bba-745c-4afc-9ef7-cfb96ea4b15a)

#### DELIVERY 3 - (DISCOUNTS PER REGIONS)
- RegDis=SuperGrocery.groupby("Region")["Discount"].sum()
- RegDis
- Name4=RegDis.index
- Number4=RegDis.values
- plt.plot(Name4,Number4,marker="o")
- plt.title("DISCOUNT BY REGION", fontsize=15, fontweight="bold", c="violet")
- plt.xlabel("Region")
- plt.ylabel("Discount")
- plt.savefig("DisReg.png")
- plt.show()

![DisReg](https://github.com/user-attachments/assets/1cae3048-51ac-47b7-8a14-030c7bd98e17)

#### DELIVERY 4 - (TOP10 CUSTOMERS WITH HIGHEST PROFIT)
- Top10=SuperGrocery.sort_values("Profit",ascending=False).head(10)
- Top10
- CustProfit=Top10.groupby("Customer Name")["Profit"].sum()
- CustProfit
- Name1=CustProfit.index
- Number1=CustProfit.values
- plt.barh(Name1,Number1,color="g")
- plt.title("TOP 10 CUSTOMERS WITH HIGHEST PROFIT", fontsize=15, fontweight="bold", c="#FF0000")
- plt.savefig("T10 cust.png")
- plt.show()

![T10 cust](https://github.com/user-attachments/assets/d452ad27-0324-4b4e-95d3-baa27b2368a5)

#### DELIVERY 5 - (SALES PER YEAR)
- SuperGrocery["Year"]=SuperGrocery["Order Date"].dt.year
- Year=SuperGrocery.groupby("Year")["Sales"].sum()
- Year
- Name3=Year.index
- Number3=Year.values
- plt.pie(Number3,labels=Name3,autopct="%1.0f%%",shadow=True,explode=[0,0.1,0,0.1])
- plt.title("SALES PER YEAR",fontsize=15, fontweight="bold", c="purple")
- plt.savefig("SPY.png")
- plt.show()

![SPY](https://github.com/user-attachments/assets/8583a388-b8bf-4140-9ffd-3fa1737ea06b)

#### DELIVERY 6 - (CATEGORY BY SALES)
- sns.boxplot(x=SuperGrocery["Category"],y=SuperGrocery["Sales"],data=SuperGrocery,palette="coolwarm")
- plt.title("CATEGORY BY SALES",fontsize=15,fontweight="bold",fontstyle="italic",c="b")
- plt.xlabel("Category Name")
- plt.ylabel("Total Sales")
- plt.savefig("CatSales.png")
- plt.show()

![CatSales](https://github.com/user-attachments/assets/2236c094-ba7d-4f3f-86cd-9d61fa8bd8ca)

# SCREENSHOT OF SUBPLOTS
- fig,SuperMart=plt.subplots(nrows=3,ncols=2,figsize=(12,12))
- fig.suptitle("SUPERMART GROCERY SALES REPORT",fontweight="bold",c="#800080",fontsize=30)
- SuperMart[0,0].bar(Name,Number,color="lime")
- sns.barplot(x=Top5["City"],y=Top5["Sales"],data=Top5,palette="summer",ax=SuperMart[0,1])
- SuperMart[1,0].plot(Name4,Number4,marker="o")
- SuperMart[1,1].barh(Name1,Number1,color="grey")
- SuperMart[2,0].pie(Number3,labels=Name3,autopct="%1.0f%%",shadow=True,explode=[0,0.1,0,0.1])
- sns.boxplot(x=SuperGrocery["Category"],y=SuperGrocery["Sales"],data=SuperGrocery,palette="coolwarm",ax=SuperMart[2,1])
- SuperMart[0,0].set(title="SALES PER DAY")
- SuperMart[0,1].set(title="TOP5 CITY BY SALES")
- SuperMart[1,0].set(title="DISCOUNT BY REGION")
- SuperMart[1,1].set(title="TOP10 CUSTOMERS WITH HIGHEST PROFIT")
- SuperMart[2,0].set(title="SALES PER YEAR")
- SuperMart[2,1].set(title="CATEGORY BY SALES")
- plt.tight_layout()
- plt.savefig("SuperMart.png")
- plt.show()

![SuperMart](https://github.com/user-attachments/assets/e9c8df09-caac-4e75-be2a-266655fff8f0)
