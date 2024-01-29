[8:17 PM, 10/6/2023] Manohar: ---
title: "Homework 3"
author: "Manohar Vellala"
---


CS 625, Fall 2023


## Choice of visualization tools
Visualization is accomplished using Python's Seaborn library and Excel. Seaborn, an extension of matplotlib, is employed for data visualization in Python. It boasts a user-friendly graphical interface that simplifies the creation of attractive and informative statistical graphics. Meanwhile, Excel is employed as a spreadsheet application for data organization and visualization.

## Data and Data Description

*Data*
1. For Bar Chart, the data used is from Table 78 - Live Births,Marriages,Deaths and Divorces.
link:<https://www2.census.gov/library/publications/2011/compendia/statab/131ed/tables/12s0078.xls>
3. For the Multiline Chart, the data used is fr…
[8:17 PM, 10/6/2023] Manohar: ---
title: "Homework 3"
author: "Manohar Vellala"
---


CS 625, Fall 2023


## Choice of visualization tools
Visualization is accomplished using Python's Seaborn library and Excel. Seaborn, an extension of matplotlib, is employed for data visualization in Python. It boasts a user-friendly graphical interface that simplifies the creation of attractive and informative statistical graphics. Meanwhile, Excel is employed as a spreadsheet application for data organization and visualization.

## Data and Data Description

*Data*
1. For Bar Chart, the data used is from Table 78 - Live Births,Marriages,Deaths and Divorces.
link:<https://www2.census.gov/library/publications/2011/compendia/statab/131ed/tables/12s0078.xls>
3. For the Multiline Chart, the data used is from Table 78 - Live Births,Marriages,Deaths and Divorces. <https://www2.census.gov/library/publications/2011/compendia/statab/131ed/tables/12s0078.xls>
4. For the Scatter Plot, the data used is from Table 78 - Live Births,Marriages,Deaths and Divorces. <https://www2.census.gov/library/publications/2011/compendia/statab/131ed/tables/12s0078.xls>

*Data Description*
The provided dataset contains a series of footnotes that offer contextual information and specific details regarding the data presented in a broader report or dataset. Footnote 1 clarifies that the infant mortality rate pertains to infants under one year of age, excluding fetal deaths. Footnotes 2 and 3 explain that data related to marriages and divorces, along with their rates, are categorized by the place where they occurred, with some exceptions and provisional data. Footnotes 4 to 8 exclude specific states from certain data sets and rates, adjusting the population accordingly. Footnote 9 specifically excludes Louisiana from a particular dataset. The source of this data is identified as the U.S. National Center for Health Statistics, primarily derived from "Vital Statistics of the United States" and "National Vital Statistics Reports (NVSR)." These footnotes help users interpret and understand the dataset's limitations, sources, and specific conditions that may apply to the data.

# Data Cleaning:

1) Numeric Format Conversion: To transform selected columns containing numeric values stored as strings into their appropriate numeric formats, one often employs functions or methods provided by data processing libraries (e.g., pd.to_numeric).

2) Dealing with Extraneous Characters: It becomes imperative to remove superfluous characters from within strings to effectively handle them. String manipulation functions are a useful tool for accomplishing this task. In the realm of data processing, it's frequently necessary to eliminate specific characters that hold no relevance to numerical values, such as currency symbols, percent signs, commas, or any other non-numeric characters.

3) Trimming White Spaces: The removal of leading or trailing white spaces from string representations of numeric values is essential. The presence of excess spaces has the potential to disrupt the data conversion process into a numerical format.

4) Convert the data to list format to make the required manipulation.

Code -

numberOfInfantsDeath=data['Infant (1,000)'].tolist()
year=pd.read_excel("data.xls",header=0)['Year'].tolist()[3:]
plottingData={"Years":year,"Births":numberOfInfantsDeath}

print(len(year))


# Visualization Idioms -

1. Bar plot -

A bar plot, commonly referred to as a bar chart, visually presents data categories using rectangular bars, with the length or height of each bar reflecting its corresponding value. Bar plots can be shown in either horizontal or vertical orientations, offering a visual means to compare different groups. In this type of chart, one axis displays the specific categories being compared, while the other axis represents the measured values associated with those categories. This graphical representation effectively illustrates comparisons among distinct groups.

| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Number Of Infant Deaths | key, quantitative| vertical spatial region (y-axis) |
| Year  | value, ordinal| horizontal position on a common scale (x-axis) |



Why bar plot is appropriate here?

The bar graph displaying the number of infant deaths on the y-axis and the year on the x-axis is appropriate for several reasons. Firstly, it effectively visualizes the trend in infant mortality over time, allowing for easy identification of any patterns or changes in the data. Secondly, the choice of a bar graph is suitable because it presents discrete data points for each year, making it clear and concise. Additionally, the use of years on the x-axis, which is typically a time-based variable, is appropriate for illustrating how infant mortality rates have evolved over different time periods.

Inference: It is evident from the bar graph that there has been a significant decrease in infant mortality over the years, and this reduction could likely be attributed to technological advancements.

2. Scatter plot -


| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Number of Births | value, quantitative | vertical spatial region (y-axis) |
| Year | value, ordinal | horizontal position on a common scale (x-axis) |

Why scatter plot is appropriate here? 

A scatter plot is an appropriate choice for representing the number of births in different years with years on the x-axis for several reasons. Firstly, it effectively displays individual data points, allowing for a clear visualization of the distribution and relationship between the number of births and time. Secondly, scatter plots are particularly useful for identifying any potential outliers or anomalies in the data that may not be as evident in other chart types. Additionally, this chart format is well-suited for examining trends, correlations, or clusters within the data, making it a valuable tool for analyzing how the number of births has varied over different years and identifying any underlying patterns or irregularities in the dataset.

Inference- We can see from the scatter plot that the number of births has increased as time pasees.

3. Multi Line plot -

| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Number of Marriages | value, quantitative | vertical spatial region (y-axis) |
| Number of Divorces| value, quantitative | vertical spatial region (y-axis) |
| Year | value, ordinal| horizontal position on a common scale (x-axis) |

Why multi line plot is appropriate here? 

A multi-line chart is appropriate for visualizing the number of divorces and marriages over the years because it enables a clear and simultaneous comparison of these two related variables within the same time frame. With years on the x-axis, it effectively portrays how both divorces and marriages have changed year by year, facilitating the observation of trends and patterns over time. This chart format enhances clarity, context, and the ability to discern long-term trends, making it a suitable choice for understanding the dynamics of these vital statistics.

Inference: We can see from the line chart that the number of divorces drastically increased from 2000 to 2010.

**Creating Charts**

1. Bar Chart -

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/bargraph.png" alt="Bar plot" width="500">


**Plotted the same bar graph using Excel:**




<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/excelbarGraph.jpeg" alt="Bar plot" width="500">

Code:-
numberOfInfantsDeath=data['Infant (1,000)'].tolist()
year=pd.read_excel("data.xls",header=0)['Year'].tolist()[3:]
plottingData={"Years":year,"Births":numberOfInfantsDeath}

print(len(year))

data = pd.DataFrame(plottingData)


plt.figure(figsize=(12, 6))  # Set the figure size

sns.barplot(x='Years', y='Births', data=data,color='blue')
plt.title('Number of Infants Death by Year')
plt.xlabel('Year')
plt.ylabel('Number of Infants Death')

plt.xticks(rotation=45)  # Rotate x-axis labels for better readability

plt.show()


2. Scatter Plot -

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/scatterplot.png" alt="Scatter plot" width="500">



Code:-
newData=pd.read_excel("data.xls",header=2)
numberofBirths=newData['Births  (1,000)']
data = pd.DataFrame({'Years': year, 'Births': numberofBirths})


plt.figure(figsize=(10, 6))


plt.scatter(data['Years'], data['Births'], marker='o', color='blue', label='Births')


plt.title('Scatter Plot of Births Over the Years')
plt.xlabel('Year')
plt.ylabel('Number of Births')


plt.legend()
plt.grid(True)
plt.show()
 

3. Multi-line Plot

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/linechart.png" alt="Multi-line plot" width="900">


 Code:-
  
data = pd.DataFrame({'Year': year, 'Marriages': numberOfMarriages, 'Divorces': numberOfDivorces})

plt.figure(figsize=(12, 6))


sns.lineplot(x='Year', y='Marriages', data=data, label='Marriages')
sns.lineplot(x='Year', y='Divorces', data=data, label='Divorces')


plt.title('Marriages and Divorces Over the Years')
plt.xlabel('Year')
plt.ylabel('Count')


plt.legend()

plt.xticks(rotation=45)


plt.show()




The code for generating the plots is in the notebook - Cs625_HW_3.ipynb
Link - <https://colab.research.google.com/drive/1_JW6_dcz5GrmH-59RDJKAaKobhXe9BEF>

# Reflection 

Seaborn provides a heightened level of flexibility and a broader array of customization options for crafting intricate and personalized data visualizations. It empowers users with precise control over various aspects of plot aesthetics, including colors, styles, and annotations. This level of control allows for the creation of visualizations that meet the stringent standards of academic publications while also catering to individual preferences.

This software excels in generating statistical visualizations, encompassing a variety of options such as box plots, violin plots, and regression graphs. It comes equipped with built-in tools for visualizing relationships between variables and presenting statistical summaries, making it a robust tool for data examination and interpretation.

Seaborn seamlessly integrates with widely-used data analysis libraries like pandas and NumPy, enabling direct data manipulation, transformation, and subsequent visualization of results. This integration streamlines the data analysis process, making it a logical choice when working in a Python environment for data analysis and manipulation.

Moreover, Seaborn facilitates the creation of data visualization scripts that lend themselves to effortless automation and reusability. This approach proves advantageous in scenarios involving extensive datasets or the need for frequent updates to visual representations.
# References

 1. https://seaborn.pydata.org/
 2. https://www.datacamp.com/tutorial/visualizing-data-in-excel
