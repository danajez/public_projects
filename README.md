# Bank`s credit card approval data
---

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/danajez/public_projects/blob/main/CC_approval_data.ipynb)


## Objective
The task is to process and analyze data that contains information about the bank's clients and their credit card requests. With this project, we simulate a real environment - we have limited knowledge about data, we encounter problems whithout solutions which weren`t provide to us and no one gives us clear tasks.

---
## Data 

We have two data sets available. In both files, the values ​​as well as the characteristics themselves are anonymized to protect sensitive client data, which of course makes our work more difficult, as the data is less interpretable. The data is stored in 2 files in JSON format. 

Dataset 1: socio-demographic data about the bank's clients.

Dataset 2: Bank data contains bank-related information for that client.

---
## Project Steps

1.   Downloading data (ETL)
2.   Data preparation (ETL - merging 2 tables, mapping with readible values, investigating missing values)
3.   Data description
4.   Visualisations
5.   Conclusion

---

## Data exploration

### Categorical data overview

`data_g.describe(include = 'object')`

![image](https://user-images.githubusercontent.com/116874735/202749493-0143475f-653a-4034-8cb4-1f887dcf65e6.png)

The most of the clients are gender b, are married, work in energy industry, are white, are born in the country. They have bank account, debt in bank and credit card wasn`t approved to them.

To find out more about distribution in selected categorical data we can use for example `data_g.industry.value_counts(normalize = True)*100` which shows % distribution of industry where clients work.

![image](https://user-images.githubusercontent.com/116874735/202753254-d4bff279-1f67-4170-99d8-c8c798299ca5.png)


### Numerical column's overview

`data_g.describe()`

![image](https://user-images.githubusercontent.com/116874735/202751205-45030f22-3acf-4622-a6a1-3b4ed927ec9a.png)

Graphical overview of numerical categories

![image](https://user-images.githubusercontent.com/116874735/202753710-30e8a85c-39e2-45b3-92cf-5aa2b5768abc.png)

The half of the clients are younger than 28 years, average age of the clients is 31 years, the oldest client is 77 years old and the youngest one is 14 years old.
The half of the clients were employed 1 year, average of them are employed 2 years, the longest epmployment period is 28 years.
The half of the clients have debt 3, 75% of them have debt 7.5, average debt is 4.8 and the maximal debt is 28.
Average credit score is 2.5, maximum credit score is 67.
Average income is 883, maximum income is 51100. Most of the clients have income below 10000.

![image](https://user-images.githubusercontent.com/116874735/202754451-0ec3b1a8-52a7-412c-95b0-d264258b4a12.png)
There is relationship between credit score and credit card approval. The higher credit score is, the higher posibility of credit card approval is. People with credit score over 30 will get the credit card. It is probably intern policy. This value can be calculated from other client`s data which are not known to us.

![image](https://user-images.githubusercontent.com/116874735/202756870-29bbcbe3-d6c2-4f22-b9b9-4c9eca105666.png)
There is higher chance of credit card approval if client works in material sector, IT, utilities sector.

There is higher chance of credit card disapproval if client works in communication services, financial sector, energy industy, real estate, consumer dicretionary or healthcare.

![image](https://user-images.githubusercontent.com/116874735/202757486-b68750b3-e234-444b-9ddd-5d0c2d27c539.png)
Here I have 3 hypothesis:
1. The credit card was approved although there was insolvency in the past and not approved if there was not prior insolvency.
2. The client got the credit card and then became insolvent.
3. The mapping of the source data is wrong.

This issue needs to be discussed with domain expert.



---

## Conclusion of the project
Who is the average client who has approved credit card? The average client who has approved credit card is white or black, married, employed, born in the country, works in IT, materials or utilities sector.

Who is the average client who has not approved credit card? The average client who has not approved credit card has asian or latino ethnicity, is single, unemployed, don`t have opened bank account, works in financial sector or healthcare.


---
The data were processed in Google Colaboratory (Colab). Colab is a free Jupyter notebook environment that runs on Google’s cloud servers. This lets you do everything you can in a Jupyter notebook hosted in your local machine, without requiring the installations and setup for hosting a notebook in your local machine.
