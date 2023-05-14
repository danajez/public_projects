# Bank`s credit card approval data
---

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/danajez/public_projects/blob/main/CC_approval_data.ipynb)


## Objective
The task is to process and analyze data that contains information about the bank's clients and their credit card requests. With this project, we simulate a real environment - we have limited knowledge about data, we encounter problems without solutions that weren`t provided to us and no one gives us clear tasks.

---
## Data 

We have two data sets available. In both files, the values ​​as well as the characteristics themselves are anonymized to protect sensitive client data, which of course makes our work more difficult, as the data is less interpretable. The data is stored in 2 files in JSON format. 

Dataset 1: socio-demographic data about the bank's clients.

Dataset 2: Bank data contains bank-related information for that client.

---
## Project Steps

1.   Downloading data (ETL)
2.   Data preparation (ETL - merging 2 tables, mapping with readable values, investigating missing values)
3.   Data description
4.   Visualisations
5.   Conclusion

---

## Data Exploration

### Categorical data overview

`data_g.describe(include = 'object')`

![image](https://user-images.githubusercontent.com/116874735/202749493-0143475f-653a-4034-8cb4-1f887dcf65e6.png)

Most of the clients are gender b, are married, work in the energy industry, are white, are born in the country. They have a bank account, debt in the bank and theri credit card wasn`t approved for them.

To find out more about distribution in selected categorical data we can use for example `data_g.industry.value_counts(normalize = True)*100` which shows the % distribution of industry where clients work.

![image](https://user-images.githubusercontent.com/116874735/202753254-d4bff279-1f67-4170-99d8-c8c798299ca5.png)


### Numerical column's overview

`data_g.describe()`

![image](https://user-images.githubusercontent.com/116874735/202751205-45030f22-3acf-4622-a6a1-3b4ed927ec9a.png)

Graphical overview of numerical categories

![image](https://user-images.githubusercontent.com/116874735/202753710-30e8a85c-39e2-45b3-92cf-5aa2b5768abc.png)

Half of the clients are younger than 28 years, the average age of the clients is 31 years, the oldest client is 77 years old and the youngest one is 14 years old.
Half of the clients were employed for 1 year, an average of them are employed for 2 years, and the longest employment period is 28 years.
Half of the clients have a debt of 3. 75% of clients have a debt 7.5, the average debt is 4.8 and the maximal debt is 28.
The average credit score is 2.5, the maximum credit score is 67.
The average income is 883, the maximum income is 51100. Most of the clients have an income below 10000.

![image](https://user-images.githubusercontent.com/116874735/202754451-0ec3b1a8-52a7-412c-95b0-d264258b4a12.png)
There is a relationship between credit score and credit card approval. The higher credit score is, the higher possibility of credit card approval is. People with a credit score over 30 will get the credit card. It is probably an intern policy. This value can be calculated from other client`s data that are not known to us.

![image](https://user-images.githubusercontent.com/116874735/202756870-29bbcbe3-d6c2-4f22-b9b9-4c9eca105666.png)
There is a higher chance of credit card approval if the client works in the material sector, IT or utility sector.

There is a higher chance of credit card disapproval if the client works in communication services, the financial sector, the energy industry, real estate, consumer discretionary, or healthcare.

![image](https://user-images.githubusercontent.com/116874735/202757486-b68750b3-e234-444b-9ddd-5d0c2d27c539.png)
Here I have 3 hypotheses:
1. The credit card was approved although there was insolvency in the past and not approved if there was no prior insolvency.
2. The client got a credit card and then became insolvent.
3. The mapping of the source data is wrong.

This issue needs to be discussed with the domain expert.



---

## Conclusion of the project
Who is the average client who has an approved credit card? The average client who has an approved credit card is white or black, married, employed, born in the country, and works in IT, materials, or utility sector.

Who is the average client who has not been approved for credit card? The average client who has not been approved for credit card has Asian or Latino ethnicity, is single, unemployed, doesn`t have opened bank account, or works in the financial sector or healthcare.


---
The data were processed in Google Colaboratory (Colab). Colab is a free Jupyter notebook environment that runs on Google’s cloud servers. This lets you do everything you can in a Jupyter notebook hosted in your local machine, without requiring the installations and setup for hosting a notebook in your local machine.
