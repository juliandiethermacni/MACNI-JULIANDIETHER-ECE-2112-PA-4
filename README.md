# ECE-2112 - Programming Assignment 4
**By: Macni, Julian Diether J. | 2ECE-B**
### Overview
This repository contains the Programming Assignment 4 for ECE 2112 - Advanced Computer Programming and Algorithms. The problems for this assignment covers Module 4, which focuses on Data Wrangling and Visualization using the Pandas and Matplotlib libraries as well as concepts like combining datasets, conditional indexing, generating visual data, and more.

Before proceeding with the different problems, the following code should be created in order for the program to function correctly:

• `import pandas as pd` - gives access to the Pandas library for creating and editing data structures.

• `import matplotlib.pyplot as plt` - gives access to the Matplotlib library for generating plots and charts.

• `pd.read_excel()` - imports the given excel file, in which for this assignment, the `board2.xlsx` file is used to load the table.

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

• `pd.DataFrame()` - used to turn the mean average scores of each category into a table.

Example:
```python
pd.DataFrame({'Mean Average': [Male, Female]},
                      index = ['Male', 'Female'])
```
will make a table of the mean average scores of the gender category.

• Matplotlib - used to construct a visual representation of the tables, in which for this problem, bar charts were used. The following Matplotlib functions were used:

  - `plt.figure(figsize=(x, y))` - creates a new figure and sets the display dimensions, in which x is the width and y is the height.
  - `plt.subplot(x, y, z)` - creates multiple plots within a single figure by specifying the grid dimensions. x is the number of rows, y is the number of columns, and z is the index.
    
    Example: `plt.subplot(1, 3, 1)` will divide the figure into a 1-row by 3-column grid, and selects the first subplot.

  - `plt.bar()` - creates a bar chart.
  - `plt.title()` - assigns a title for the given bar chart.
  - `plt.ylabel()` - assigns a name for the y-axis.
  - `plt.show()` - shows the created figure.

These methods were combined in order to make a figure that shows bar charts of the average mean of the three different categories:
```python
#mean average of each track
Communication = df.loc[(df['Track'] == 'Communication'), 'Average'].mean()
Instrumentation = df.loc[(df['Track'] == 'Instrumentation'), 'Average'].mean()
Microelectronics = df.loc[(df['Track'] == 'Microelectronics'), 'Average'].mean()

Track = pd.DataFrame({'Mean Average': [Communication, Instrumentation, Microelectronics]},
                      index = ['Communication', 'Instrumentation', 'Microelectronics'])


#mean average of each gender
Male = df.loc[(df['Gender'] == 'Male'), 'Average'].mean()
Female = df.loc[(df['Gender'] == 'Female'), 'Average'].mean()

Gender = pd.DataFrame({'Mean Average': [Male, Female]},
                      index = ['Male', 'Female'])


#mean average of each hometown
Luzon = df.loc[(df['Hometown'] == 'Luzon'), 'Average'].mean()
Visayas = df.loc[(df['Hometown'] == 'Visayas'), 'Average'].mean()
Mindanao = df.loc[(df['Hometown'] == 'Mindanao'), 'Average'].mean()

Hometown = pd.DataFrame({'Mean Average': [Luzon, Visayas, Mindanao]},
                      index = ['Luzon', 'Visayas', 'Mindanao'])


#displays the figure containing bar charts
plt.figure(figsize=(18, 4))

plt.subplot(1, 3, 1)
plt.bar(Track.index, Track['Mean Average'])
plt.title('Mean Average by Track')
plt.ylabel('Mean Average')

plt.subplot(1, 3, 2)
plt.bar(Gender.index, Gender['Mean Average'])
plt.title('Mean Average by Gender')

plt.subplot(1, 3, 3)
plt.bar(Hometown.index, Hometown['Mean Average'])
plt.title('Mean Average by Hometown')

plt.show()
```

From the results of this problem, the communication track, the male gender, and the region of Luzon have the highest sample mean within their respective categories.

Thank you for reading!
