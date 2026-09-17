# ECE-2112 - Programming Assignment 4
**By: Macni, Julian Diether J. | 2ECE-B**
### Overview
This repository contains the Programming Assignment43 for ECE 2112 - Advanced Computer Programming and Algorithms. The problems for this assignment covers Module 4, which focuses on Data Wrangling and Visualization using the Pandas and Matplotlib libraries as well as concepts like combining datasets, conditional indexing, generating visual data, and more.

Before proceeding with the different problems, the following code should be created in order for the program to function correctly:

• `import pandas as pd` - gives access to the Pandas library for creating and editing data structures.

• `import matplotlib.pyplot as plt` - gives access to the Matplotlib library for generating plots and charts.

• `pd.read_excel()` - imports the given excel file, in which for this assignment, the `board.xlsx` file is used to load the table.

• `.mean()` - used to get the overall grade average of each student.

## A. VISAYAS COMMUNICATION DATAFRAME
**Objective:** Create a DataFrame containing students from Visayas and has a track of Communication, as well as only display specific columns, which are: Name, Gender, Math, Electronics, and Average. The number of rows should be displayed as well.

The following functions or methods were used in this problem:

• **Boolean Indexing** - used to only display rows or columns that satisfy certain conditions.

Example:
```python
VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication'), ['Name', 'Gender', 'Math', 'Electronics', 'Average']]
```
which will filter the table so that it only displays students from Visayas which has a track of communication, as well as the specific columns.

• **len()** - displays the number of rows

Example: `len(VisComm)` will display 5, which is the number of rows of the DataFrame VisComm.

These methods were combined in order to create and display the final Visayas Communication DataFrame along with its row count:
```python
VisComm = df.loc[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication'), ['Name', 'Gender', 'Math', 'Electronics', 'Average']]
len(VisComm)
```




## B. VISAYAS FEMALE DATAFRAME
**Objective:** Create a DataFrame containing female students from Visayas, as well as only display specific columns, which are: Name, Track, GEAS, Electronics, and Average. After that, display only rows of the created DataFrame that has an average of at least 60.

The following functions or methods were used in this problem:

• **Boolean Indexing** - used to only display rows or columns that satisfy certain conditions.

This method, similar to the first problem, was used in order to create and display the final Visayas Female DataFrame, as well as display only the rows of the created DataFrame that has at least 60 in the average grade: 
```python
VisFemale = df.loc[(df['Hometown'] == 'Visayas') & (df['Gender'] == 'Female'), ['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
VisFemale.loc[(VisFemale['Average'] >= 60)]
```




## C. CATEGORY-AVERAGE VISUALIZATION
**Objective:** Calculate the mean average scores across the different categories, which are track, gender, and hometown. After that, create a figure containing bar charts from the categories.

The following functions or methods were used in this problem:

• `.loc[[M],[N]]` - selects rows and columns using label names or even Boolean conditions instead of just numerical values.

Example:
```python
df.loc[(df['Track'] == 'Communication'), 'Average']
```
which will select all values from the average column for students whose track is communication.

• `.mean()` - used to get the mean average of each categories.

• `pd.
