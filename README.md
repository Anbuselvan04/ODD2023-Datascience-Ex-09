# Ex-09-Data-Visualization-

### Name : ANBUSELVAN A
### Reg No : 212221040013

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


## CODE
```py

import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset('tips')

# Drop rows with all missing values
tips.dropna(how='all', inplace=True)
sns.barplot(x='day', y='total_bill', data=tips)
plt.show()

# a) Which day of the week has the highest total bill amount?

# Group by day and sum total_bill
total_bill_by_day = tips.groupby('day')['total_bill'].sum()

# Sort by descending order and select the first row
highest_total_bill_day = total_bill_by_day.sort_values(ascending=False).index[0]

print("The day with the highest total bill amount is:", highest_total_bill_day)

# b) What is the average tip amount given by smokers and non-smokers?

sns.barplot(x='smoker', y='tip', data=tips)
plt.show()

# Group by smoker and calculate mean of tip
tip_by_smoker = tips.groupby('smoker')['tip'].mean()

print("Average tip amount given by smokers:", tip_by_smoker['Yes'])
print("Average tip amount given by non-smokers:", tip_by_smoker['No'])

# c) How does the tip percentage vary based on the size of the dining party?

tips['tip_percentage'] = tips['tip'] / tips['total_bill'] * 100
sns.pointplot(x='size', y='tip_percentage', data=tips)
plt.show()

# Create a new column for tip percentage
tips['tip_percentage'] = tips['tip'] / tips['total_bill']

# Group by size and calculate mean of tip percentage
tip_percentage_by_size = tips.groupby('size')['tip_percentage'].mean()

print("Tip percentage by size of dining party:")
print(tip_percentage_by_size)

# d) Which gender tends to leave higher tips?

sns.boxplot(x='sex', y='tip', data=tips)
plt.show()

# Group by gender and calculate mean of tip
tip_by_gender = tips.groupby('sex')['tip'].mean()

print("Average tip amount by gender:")
print(tip_by_gender)

# e) Is there any relationship between the total bill amount and the day of the week?

sns.scatterplot(x='total_bill', y='day', data=tips)
plt.show()

# f) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?

sns.boxplot(x='time', y='total_bill', data=tips)
plt.show()

# g) Which dining party size group tends to have the highest average total bill amount?

sns.barplot(x='size', y='total_bill', data=tips)
plt.show()

# Group by size and calculate mean of total_bill
total_bill_by_size = tips.groupby('size')['total_bill'].mean()

print("Average total bill amount by size of dining party:")
print(total_bill_by_size)

# h) What is the distribution of tip amounts for each day of the week?

sns.boxplot(x='day', y='tip', data=tips)
plt.show()

# i) How does the tip amount vary based on the type of service (lunch vs. dinner)?

sns.boxplot(x='time', y='tip', data=tips)
plt.show()

# j) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x='total_bill', y='tip', data=tips)
plt.show()
correlation = tips['total_bill'].corr(tips['tip'])
print("Correlation coefficient between total_bill and tip:", correlation)
```
## OUTPUT
![278807375-808d8a79-94ae-43e1-8033-e259d9200419](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/37492d63-0702-41e4-8d53-438ffe85a0e9)

![278807384-cd1818a9-e95b-49f1-bf37-c47656effa1a](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/4716def0-ed26-4153-9b13-be27c478bcf0)

![278807392-a1d16d34-e52c-409c-866b-17b9810be9de](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/caec9cba-1cc7-4beb-8cb6-c82992602c7b)

![278807402-cdf50f2b-5dbc-475d-bab4-cf87023e408e](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/d489bfd7-4cb9-4bc5-b14a-d9887ab406f9)

![278807409-45fcd3b6-3573-48b6-915d-8c3caa269943](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/4743e1d8-f171-405d-bcf2-79cc4f07f956)

![278807415-3897fa5e-5de4-47f5-b3f7-53d322d6c245](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/562b36f0-aad7-4b71-823e-739e9d6fb736)

![278807428-4b3ffe16-6895-4e5e-9ec3-3019e3e638ca](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/c4e0cca1-4c33-4084-985a-f536a31bdb40)

![278807447-e99a599a-788b-4090-b40c-668fccfdf321](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/9f5489cc-73ba-44d8-92e2-14d37dd91e83)

![278807467-1f912fc1-010d-4adf-bff5-deef6cf5957b](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/9009c7a3-4ffe-475d-8104-7e4387093051)

![278807475-a0913b22-f852-4431-8979-b6401f4f1c20](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/7e4c5972-921d-44be-af77-952a2f0b36a3)

![278807484-86bec457-a294-4e98-8fd9-b5834338a149](https://github.com/Anbuselvan04/ODD2023-Datascience-Ex-09/assets/119410896/06114d94-78eb-492b-864b-9b3b8291f5b8)





## RESULT
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.
