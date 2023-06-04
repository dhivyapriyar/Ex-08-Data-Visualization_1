# Ex-08-Data-Visualization-

## AIM

To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation

Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM

### STEP 1
Read the given Data

### STEP 2
Clean the Data Set using Data Cleaning Process

### STEP 3
Apply Feature generation and selection techniques to all the features of the data set

### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE

NAME: DHIVYAPRIYA.R

REG.NO.:212222230032

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)

df.isnull().sum()

Handling Outliers
plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

Removing Outliers
plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

1) Which day of the week has the highest total bill amount?
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()

2) What is the average tip amount given by smokers and non-smokers?
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

7) Which dining party size group tends to have the highest average total bill amount?
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

8) What is the distribution of tip amounts for each day of the week?
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

10) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()

# OUPUT

![Screenshot 2023-06-04 103819](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/cc9e18d7-80e2-447e-ab89-7679698ebce3)
![Screenshot 2023-06-04 103854](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/8352392a-b1d1-4c7b-94db-9dd9889b36f1)
![Screenshot 2023-06-04 104032](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/579e1f18-7528-4d30-91af-a059f85c241a)
![Screenshot 2023-06-04 104117](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/22030f1f-f090-4a26-baaa-6107c6a59a5d)
![Screenshot 2023-06-04 104129](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/fd09eee1-f8b3-457e-8f4f-dbd248c83517)
![Screenshot 2023-06-04 104138](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/a83f9982-69ae-4d4b-8c59-48a570846477)
![Screenshot 2023-06-04 104149](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/7eb8d01d-6987-4eec-9625-e9432b7bad6d)
![Screenshot 2023-06-04 104201](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/a81c18c1-6bd0-4648-b6b4-7811c5e5b596)
![Screenshot 2023-06-04 104210](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/9cd5d43e-0dc6-4911-afd6-4da35ec2154e)
![Screenshot 2023-06-04 104235](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/ceba33be-0211-4f95-be15-29aa74f48af1)
![Screenshot 2023-06-04 104243](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/9febd6bd-a691-49e2-a394-98d1d29029a3)
![Screenshot 2023-06-04 104253](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/a40602b4-f086-4e76-990c-df2222a9840c)
![Screenshot 2023-06-04 104304](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/56b3df4b-711b-4e16-82a2-c0c7fd45ee20)
![Screenshot 2023-06-04 104313](https://github.com/dhivyapriyar/Ex-08-Data-Visualization_1/assets/119477552/6da5d577-6eed-42d0-b556-90770ab29fd9)

#RESULT

Thus the Data Visualization method is performed to the given data and to predict the outcome for the given questions.

