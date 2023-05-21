# Revenue and Product report
---
## Objective
The task is to create report showing data about the sales of product.
There are 2 views:
1. View by salesmen
2. View by products

---
## Data
Data used in the report are from Microsoft learning database [Adventure WorksDW](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms).

---
## Project Steps
1. Data Gathering
2. Data Preparation (ETL)
3. Data Modeling
4. Visualization Design
5. Interactive Features
6. Conclusion

---
### Data Gathering
I started to gather data by identifying the data sources required for my project. This involved extracting data from learning database.

### Data Preparation (ETL)
Once I had the data, I performed data cleaning and transformation tasks to ensure its quality and compatibility with Power BI. This included handling missing values, removing duplicates, and applying necessary data type conversions.

![image](https://github.com/danajez/public_projects/assets/116874735/451c1d28-664f-4896-b6d8-87b7c8a9ed0b)

### Data Modeling
In Power BI, I created a data model by defining relationships between the different tables in my dataset. This enabled me to combine data from multiple sources and establish meaningful connections between them.
Model view shows all of the tables and columns in the model, and the relationships between them.

![image](https://github.com/danajez/public_projects/assets/116874735/9397c2ee-1a7d-42a6-970a-7ecc5d3c0a17)

### Visualization Design
With the data model in place, I designed visually appealing and informative reports and dashboards. I used Power BI's wide range of visualizations, such as gauge, cards, treemap, charts, and matrix, to represent the data effectively.

### Interactive Features
I enhanced the user experience by adding interactive features to the reports and dashboards. This included slicers, filters, and drill-through functionality, allowing users to explore and analyze the data in a more dynamic and personalized way.

## Report
### Main paige
Only main paige is visible to users. On the maine paige are info about the source of data and 2 buttons: Revenue and Products. By clicking to any of this button user will be redirected to either Revenue view or to Product view. 
![image](https://github.com/danajez/public_projects/assets/116874735/92362f15-0692-47cb-984c-0b1f36508be7)

### Revenue view
In the middle of screen is Menu buttow which will redirect user back to the Main page.
![image](https://github.com/danajez/public_projects/assets/116874735/3da25097-52d9-4661-89e1-dfbad37db934)

There are 5 parts in the Revenue view.
1. User can use slicer to filter the quarter and reporting year. 
   ![image](https://github.com/danajez/public_projects/assets/116874735/48029d5e-178a-4402-b0f3-953e5b810a60)

2. User can see Revenue, Plan and % fullfilment of the plan vs budget in numbers. The gauge is used to show those numbers in visualization.
   ![image](https://github.com/danajez/public_projects/assets/116874735/c76be23c-c990-48f5-9eea-91cb26cf12e7)
   
3. We can see which salesmen was the most active. By hoovering over the name, user is able to see exact revenue numbers for the person.
   ![image](https://github.com/danajez/public_projects/assets/116874735/cf1dee88-f700-4dbc-8fc4-1a536ad7a70d)

4.In this view we can see revenue vs budget in abslute numbers and in % per quarter for filtered year.
   ![image](https://github.com/danajez/public_projects/assets/116874735/89d8c4a0-3196-4956-88b0-f834fb14a79a)
   
5. In this view user can see revenue per quarter compared to last year`s revenue per quarter and % expression of the comparisson as well.
   ![image](https://github.com/danajez/public_projects/assets/116874735/1968bf8d-1567-4e41-922a-026d5e80586c)

