# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
## TO CAPTURE A TREND
# 1. Line Chart
```
import matplotlib.pyplot as plt
import numpy as np
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.plot(x,y)
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/6ed32ef8-6b3d-43b9-9646-37947f2a1096)

# 2.Multi-Line Chart
```
x1=[1,2,3]
y1=[2,4,1]
plt.plot(x1,y1,label="line 1")
x2=[1,2,3]
y2=[4,1,3]
plt.plot(x2,y2,label="line 2")
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('Multi-Line Chart')
plt.legend()
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/217f8555-b087-4339-a0df-051ef4167108)

# 3.Area Chart
```
x=[1,2,3,4,5]
y1=[10,12,14,16,18]
y2=[5,7,9,11,13]
y3=[2,4,6,8,10]
plt.fill_between(x,y1,color='blue')
plt.fill_between(x,y2,color='green')
plt.plot(x,y1,color='red')
plt.plot(x,y2,color='black')
plt.legend(['y1','y2'])
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/0702a941-516f-4a09-84d0-4e15b00ea4aa)

# 4.Stacked Area Chart
```
plt.stackplot(x,y1,y2,y3,labels=['Line 1','Line 2','Line 3'])
plt.legend(loc='upper left')
plt.title('Stacked Line Chart')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/e0c6163f-bae7-4712-9fe8-44982d0b5fe8)

# 5.Spline Chart
```
from scipy.interpolate import make_interp_spline
x=np.array([1,2,3,4,5,6,7,8,9,10])
y=np.array([2,4,5,7,8,8,9,10,11,12])
spl=make_interp_spline(x,y)
x1=np.linspace(x.min(),x.max(),100)
y1=spl(x1)
plt.plot(x,y,'*',label='data')
plt.plot(x1,y1,'-',label="spline")
plt.legend()
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/2bf2f2a8-d3b4-451c-b650-73a25be5e0ec)

## TO VISUALIZE RELATIONSHIPS
# 1.Bar Chart
```
val=[5,6,3,7,2]
names=["A","B","C","D","E"]
plt.bar(names,val,color="blue")
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/0deb2948-b9b1-4254-a603-82e788f0f543)

# 2.Scatter Plot
```
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.scatter(x,y,s=30,color="red")
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/40b27f91-0f04-444a-a4c1-1e286293f106)

# 3.Bubble Chart
```
x = [1, 2, 3, 4, 5]
y = [10, 15, 20, 25, 30]
sizes = [100, 200, 300, 400, 500]
plt.scatter(x, y, s=sizes, alpha=0.5)
plt.xlabel('x_values')
plt.ylabel('y_values')
plt.title('Bubble Chart')
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/e4d17763-616f-41f8-b4cb-0857f1a460fc)

## TO CAPTURE DISTRIBUTIONS
# 1.Histogram
```
ages=[2,5,70,40,30,45,50,45,43,40,44,60,7,13,57,18,90,77,32,21,20,40]
range=(0,100)
bins=10
plt.hist(ages,bins,range,color='purple',histtype='bar',rwidth=0.8)
plt.xlabel('age')
plt.ylabel('No. Of People')
plt.title('Histogram')
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/a8c64c0a-ae3c-454b-8150-6d0d381c2065)

# 2.Box Plot
```
np.random.seed(0)
data=np.random.normal(loc=0,scale=1,size=100)
data
fig,ax=plt.subplots()
ax.boxplot(data)
ax.set_xlabel('Data')
ax.set_ylabel('Values')
ax.set_title('Box Plot')
```
# Output
![image](https://github.com/user-attachments/assets/e625e339-16d4-40b0-918d-f4384e42ae80)

# 3.Violin Plot
```
data = [np.random.normal(loc=0, scale=1, size=100),
        np.random.normal(loc=2, scale=1, size=100),
        np.random.normal(loc=1, scale=2, size=100)]
plt.violinplot(data)
plt.xlabel('Groups')
plt.ylabel('Values')
plt.title('Violin Plot')
plt.xticks([1, 2, 3], ['Group 1', 'Group 2', 'Group 3'])
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/d9cba128-9b2c-4edc-906d-ba255384e675)

# 4.Density Chart
```
data = np.random.normal(0, 1, 1000)
plt.hist(data, bins=30, density=True, alpha=0.5)
plt.title('Density Plot Example')
plt.xlabel('Values')
plt.ylabel('Density')
from scipy.stats import gaussian_kde
kde = gaussian_kde(data)
x_vals = np.linspace(min(data), max(data), 1000)
plt.plot(x_vals, kde(x_vals), 'r')
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/b86667c6-7780-4a03-8765-8015b21de767)

# 5.Pie Chart
```
act=['eat','sleep','work','play']
slices=[3,7,8,6]
color=['r','y','g','b']
plt.pie(slices,labels=act,colors=color,startangle=90,shadow=True,explode=(0.1,0.1,0.1,0.1),radius=1.2,
autopct='%1.1f%%')
plt.legend()
plt.show()
```
# Output
![image](https://github.com/user-attachments/assets/a9b4874b-2327-4baf-8bc4-d84ebae31fc7)

# Result:
 Thus, the data visualization techniques using matplotlib has been executed successfully.
