# Ex-08 Data Visualization-1

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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

import pandas as pd

df=pd.read_csv('/content/Superstore.csv',encoding='windows-1252')

df.head()

df.isnull().sum()

import seaborn as sns

sns.boxplot(data=df)

import seaborn as sns

import matplotlib.pyplot as plt

sns.barplot(y=df['Sales'], x=df['Segment'])

plt.title("Highest Sales of the segment")

plt.show()

sns.barplot(y=df['Profit'], x=df['City'])

plt.title("Highest Profit based on the city")

plt.show()

sns.barplot(x=df['Ship Mode'],y=df['Profit'])

plt.title("Profitable ship")

plt.show()

sns.barplot(x=df['Region'],y=df['Sales'])

plt.title("Sales of product based  on region")

plt.show()

sns.lineplot(x=df['Sales'], y=df['Profit'])

plt.title("Relation between Sales and Profit")

plt.show()

grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()

fig, ax = plt.subplots()

ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')

ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')

ax.set_xlabel('Segment')

ax.set_ylabel('Value')

ax.legend()

plt.title("Sales and Profit based on Segment")

plt.show()

grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()

fig, ax = plt.subplots()

ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')

ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')

ax.set_xlabel('City')

ax.set_ylabel('Value')

ax.legend()

plt.title("Sales and Profit based on City")

plt.show()

grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()

fig, ax = plt.subplots()

ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')

ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')

ax.set_xlabel('State')

ax.set_ylabel('Value')

ax.legend()

plt.title("Sales and Profit based on States")

plt.show()

grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()

pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])

fig, ax = plt.subplots()

pivot_data.plot(kind='bar', ax=ax)

ax.set_xlabel('Segment')

ax.set_ylabel('Value')

plt.legend(title='Ship Mode')

plt.legend(loc="best")

plt.title("Sales and Profit based on Segment and Ship mode")

plt.show()

grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()

pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])

sns.set_style("whitegrid")

sns.set_palette("Set1")

pivot_data.plot(kind='bar', stacked=True, figsize=(8, 5))

plt.legend(title='Region')

plt.legend(loc='best')

plt.title("Sales and Profit based on Segment,Ship mode and Region")

plt.show()


## OUPUT

![op1](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/38af0e2d-dbee-4ce8-8c4f-b5e9db7266f6)
![op2](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/182a6fae-03f7-457a-94d6-6116e8b7e302)
![op3](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/aa255e27-f145-43e5-a5a0-ff5dd413266e)
![op4](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/fec14654-ac47-470f-b935-5469daa53bcb)
![op5](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/3edf622b-6a25-46d7-b42f-e0af9f03c5c2)
![op6](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/5f3d0697-b66f-4d55-8faa-0ac04d18a7b2)
![op7](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/b6ccc827-fed7-4443-93c2-b730003a4938)
![op8](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/46e3c7b5-4fd8-4b3a-b45b-d4a49f102741)
![op9](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/461b904f-2717-4a73-8efd-dc039252050d)
![op10](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/1d77e816-d3b7-4359-9a10-88f6397f0032)
![op11](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/5ebb8c17-2c4e-46c2-b55b-61c57f7510f4)
![op12](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/f3aae47b-ad16-4807-9542-fe49e2d5a11b)
![op13](https://github.com/Thirisaa/Ex-08-Data-Visualization-/assets/112301582/2c5e87c2-79b6-4cb9-ae01-4ed52834e27f)

## RESULT

Thus Data Visualization was performed on the given dataset and the results were displayed successfully.



