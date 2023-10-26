# Ex-09-Data-Visualization-

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
```py
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
print(df)
```
```py
df.isnull().sum()
```
```py
plt.figure(figsize=(5,5))
plt.title("Data with outliners")
df.boxplot()
plt.show()
```
```py
plt.figure(figsize=(5,5))
cols=['size','tip','total_bill']
Q1=df[cols].quantile(0.25)
Q3=df[cols].quantile(0.75)
IQR=Q3-Q1
df=df[~((df[cols]<(Q1-1.5*IQR))|(df[cols]>(Q3+1.5*IQR))).any(axis=1)]
plt.title("Dataset after removing outliners")
df.boxplot()
plt.show()
```
```pysns.barplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()
```
```py
sns.boxplot(x=df['smoker'],y=df['tip'],hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")
```
```py
df["tip_percent"]=df["tip"]/df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
```py
sns.boxplot(x=df['sex'],y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")
```
```py
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")
```
```py
sns.histplot(data=df,x="total_bill",hue="time",element="step",stat="density")
plt.title("Diste=ibution of Total Bill Amount by Time of  Day")
plt.show()
```
```py
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average total bill amount by dining party size")
plt.show()
```
```py
sns.boxplot(x="day",y="tip",data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
```py
sns.violinplot(x="time",y="tip",data=df)
plt.title("Tip Amount by Time of Day")
plt.show()
```
```py
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

# OUPUT
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/458ff235-8253-4aa7-8793-658179daa239)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/7982380c-4fa6-427c-ac31-4d85df0add3e)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/003f98c8-306e-414a-8c20-59c191da0be3)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/8c561f53-6c2c-4416-ac2e-b26bc6e0438f)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/f7efdd41-c5c5-44c1-af09-a86be755bdb5)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/29383526-89cd-47e9-a175-ab202c5a5cee)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/963615a5-83da-4947-9ef3-54e4e3f909d2)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/bcc37378-b39b-4f4e-b50f-ed13a84d98f2)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/b35c8b83-6ec3-45d2-8bee-f60215ee64c9)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/76c69280-1c15-4cb3-8172-29d626a0953b)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/b754ec82-5e83-43ed-bbdf-72f4d62c1f7c)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/984e886e-e7bd-4603-86bc-8b93cc83e9dc)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/db310a74-7301-44dc-a8c4-69e04fdff721)
![image](https://github.com/kanishka2305/ODD2023-Datascience-Ex-09/assets/113497357/cab7f5fd-d340-48c2-aaa3-f800e39142c4)

