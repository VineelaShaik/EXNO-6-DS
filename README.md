# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
```

```
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
```

```
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/e144788f-fc25-486e-aee7-587b040f4513)

```
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/2da36bd9-e5be-4ab1-800c-3e83aa7c3634)

```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")

```
![image](https://github.com/user-attachments/assets/a7bddc5b-477e-4ae8-9e74-033df1e98d98)

```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
```

```
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/9036e4b6-eae8-42a9-b6a5-dc0588495b7a)

```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/4b8a21f8-508f-42bb-b2ba-8d6837ca2ee2)

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/103fd31a-d13f-4df2-b064-66a7832f2cf1)

```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
```

```
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/ff5b040e-39d7-4958-9f18-45f46cd61eee)

```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/ca230e74-dd61-44d1-8489-963b6b53a6c0)

```
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/30aaa080-ade7-4699-a2b9-a9e7e54bfd4a)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/da0e3aee-506d-4f80-9044-2fc988f4673e)

```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/36211dac-0941-4625-890a-4ccf3b8e5d49)

```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/f1ab2651-8b2b-493b-92aa-8e4f4b4724bc)

```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/cef8abd8-7965-4950-b5a7-9360bad02a4f)

```
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/0093459e-a217-4dc0-8f1b-aa2fd527c3ee)

```
sns.histplot(data=tit,x="Pclass",hue="Survived",kde=True)
```
![image](https://github.com/user-attachments/assets/1cbbfac0-a1db-4c03-910b-011ea7c8aff6)


```
import matplotlib.pyplot as plt
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks
```
![image](https://github.com/user-attachments/assets/ec17c306-44ac-4652-85a8-d0f97f95235f)

```
sns.histplot(data=marks,bins=10,kde=True,stat='count',cumulative=False,multiple='stack',element='bars',palette='Set1',shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Student Marks')
```
![image](https://github.com/user-attachments/assets/8cd82af1-74d7-4ae9-8fb6-6b6ce142c9e4)

```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'],y=tips['total_bill'],hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/6dcaada0-8103-4548-9a16-ce07991be0a3)

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,boxprops={"facecolor":"lightblue","edgecolor":"darkblue"},
            whiskerprops={"color":"black","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```
![image](https://github.com/user-attachments/assets/22c01787-aa41-42bf-bef3-bd24f0f519f4)

```
sns.boxplot(x='Pclass',y='Age',data=tit,palette='rainbow')
plt.title("Age by Passenger Class,Titanic")
```
![image](https://github.com/user-attachments/assets/30f773ef-42b8-47a4-a7aa-24f04b09f34f)

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set3",inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/32cab249-2bb3-484c-99b7-edfefde8487b)

```
import seaborn as sns
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip)
```
![image](https://github.com/user-attachments/assets/b97071a6-757c-40ba-9c43-c01358431d71)

```
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![image](https://github.com/user-attachments/assets/494c842c-91ad-4a47-8340-72b25bb13cb5)

```
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x="tip",y="day",data=tip)
```
![image](https://github.com/user-attachments/assets/5cad244e-4082-4349-9d8a-fc7a4b875f16)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set3',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/91d72ec6-a576-49d4-a0eb-9be06c702f2b)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/347da61a-70f0-4f4b-8356-43dd60a59aa2)

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack',linewidth=3,palette='Set2',alpha=0.8)
```
![image](https://github.com/user-attachments/assets/42583242-0049-4517-96c5-ad2a45c43e07)

```
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)
```
![image](https://github.com/user-attachments/assets/f6854c5a-1d19-439f-8707-6c0fce3b89d2)

```
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/91c4b368-3380-4af9-913a-67aee54a747e)

```
tips=sns.load_dataset('tips')
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr()
sns.heatmap(corr,annot=True,cmap="plasma",linewidth=0.5)
```
![image](https://github.com/user-attachments/assets/62ebe2c0-2548-4cab-a90d-671f0e91f53c)

# Result:
 Thus, the Data Visualization using seaborn python library for the given data is implemented successfully
