---
title: "Homework 4"
author: "Manohar Vellala"
---

CS 625, Fall 2023

# Dataset 1
Table 91 - Women Who Have Had a Child in the Last Year by Age

## Data Cleaning

Numeric Format Conversion: The chosen columns containing numeric data stored as strings should be converted into their corresponding numerical formats. This typically involves using functions or methods provided by data processing tools (e.g., pd.to_numeric).

Dealing with Unwanted Characters: It's essential to remove unnecessary characters from strings to manage them effectively. String manipulation functions can be employed to accomplish this task. In the context of data processing, it's often necessary to eliminate specific characters that don't pertain to numerical values, such as currency symbols, percentage signs, commas, or other non-numeric characters.

Trimming White Spaces: Get rid of any leading or trailing white spaces from string representations of numerical values. Extra spaces can potentially disrupt the process of transforming data into a numerical format.

After cleaning and converting the data, it can be saved as a CSV file.

```
i = 0
while i < len(total_births_columns):
    column = total_births_columns[i]
    
    # Remove commas and fill NaN values with 0
    data_frame[column] = data_frame[column].str.replace(',', '')
    data_frame[column] = data_frame[column].fillna(0)
    # Convert the column to integers
    data_frame[column] = data_frame[column].astype(int)
    i += 1  # Move to the next column

    i += 1  # Move to the next column if an exception occurs

# Fill remaining NaN values with 0
data_frame = data_frame.fillna(0)
# Fill remaining NaN values with 0
```

## Questions 

### Q1: Compare the ages of women at the time of the birth of their first child between 1990-2008. For instance, is there any evidence that women in the US are waiting longer to have their first child?

#### Solution -
1) Between 1990 and 2008, there was a consistent upward trend in the average birth rates for women aged 40-44 and 35-39, indicating an increase in childbirth within these age brackets.

2) The average birth rates for women aged 25-29 displayed variability over the years. They decreased between 1995 and 2004 but demonstrated an increase in 1990 and 2008. These fluctuations suggest that birth rates within the 25-29 age group experienced changes during the specified time frame.

3) In 1994, women aged 20-24 and 30-34 experienced a simultaneous increase in their average birth rates. However, between 1995 and 2002, there was a decline in birth rates within these age groups. Subsequently, there was a slight resurgence in 2004, followed by another decrease in 2006 and 2008. These fluctuations highlight the volatility in birth rates for women in the 20-24 and 30-34 age categories during the specified period.
Conclusion of the chart
The average age of women at first birth increased from 25.0 in 1990 to 25.6 in 2008, an increase of 0.6 years. This suggests that women in the US are waiting slightly longer to have their first child.

However, the increase in average age at first birth is relatively small, and there is some variation from year to year. For example, the average age at first birth dipped slightly in 1995 and 1998. Additionally, the image shows that the proportion of first births to women in their 20s remained relatively stable between 1990 and 2008.

Overall, the evidence suggests that women in the US are waiting slightly longer to have their first child, but the change is relatively small and there is some variation from year to year.


As you can see, the proportion of first births to women in their 20s remained relatively stable between 1990 and 2008. However, the proportion of first births to women in their 30s and 40s increased slightly.

These trends offer valuable insights into the evolving patterns of birth rates among different age groups over time.

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/firstChildImage.png" alt="Line plot" width="900">

```

# Define the columns of interest for first births
first_births_columns = ['1990_First_Births', '1992_First_Births', '1994_First_Births', '1995_First_Births', '1998_First_Births', '2000_First_Births', '2002_First_Births', '2004_First_Births', '2006_First_Births', '2008_First_Births']

# Select the columns of interest for first births
first_births_data_frame = data_frame[['Age of mother', '1990_First_Births', '1992_First_Births', '1994_First_Births', '1995_First_Births', '1998_First_Births', '2000_First_Births', '2002_First_Births', '2004_First_Births', '2006_First_Births', '2008_First_Births']]

# Reshape the data for visualization
expanded_DataFrame = pd.melt(first_births_data_frame, id_vars='Age of mother', var_name='Year', value_name='First Births')
expanded_DataFrame['Year'] = expanded_DataFrame['Year'].str.replace('_First_Births', '').str.strip()
expanded_DataFrame = expanded_DataFrame.reset_index(drop=True)

# Define a custom color palette
custom_palette = sns.color_palette("Set1")

# Create a line plot to visualize the data for first births with custom colors
plt.figure(figsize=(18, 18))
sns.lineplot(data=expanded_DataFrame, x='Year', y='First Births', hue='Age of mother', style='Age of mother', markers=True, dashes=True, palette=custom_palette)

# Customize the plot
plt.title("Ages of Women at the Time of Their First Child's Birth (1990-2008)")
plt.xlabel("Year")
plt.ylabel("First Births Total")
plt.xticks(rotation=45)
plt.legend(title='Age of mother', loc='upper right')
plt.tight_layout()

# Show the plot
plt.show()


```
Idiom: Multiple Line Chart / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Total Births of First Child | value, quantitative | vertical spatial region (y-axis) |
| Year | value, Temporal | horizontal position on a common scale (x-axis) |
| Age of mother |value, categorical | Hue |


A multiple line chart is well-suited for visually representing and comparing the variations in "Age at Birth" across different age groups of mothers over time, as indicated by the "Year" variable. In this figure, each horizontal line represents a specific age cohort, making it easy to compare the trends and fluctuations in the age at which individuals in each group give birth over multiple years. This chart effectively highlights the changes in age groups over the years, with a focus on the common variable, which is the year. As a result, it simplifies the identification of temporal trends and patterns within the data spanning from 1990 to 2008.

### Q2: How does this compare to the number of women in each age group who had a child (not necessarily their first) in that year? What does this say about the age of women giving birth in the US?

#### Solution -
1) Within the age brackets of 40-44, 35-39, and 30-34, the average birth rates for women exhibited a consistent increase from 1990 to 2008.

2) Among women aged 25-29, the average birth rates experienced a drop between 1995 and 2004, followed by an increase in 2004 and 2008. This suggests a fluctuation in birth rates within this age group over the years.

3) The average birth rates for women aged 20-24 declined, with a notable upswing occurring in 1994. These findings highlight the higher level of volatility in birth rates within these specific age groups during the specified period. These observations offer valuable insights into the evolving patterns of birth rates among different age groups over time.


<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/TotalBirthsImage.png" alt="Line plot" width="900">

```
# Select the columns of interest for analysis
selected_data_frame = data_frame[['Age of mother', '1990_Total_Births', '1992_Total_Births', '1994_Total_Births', '1995_Total_Births', '1998_Total_Births', '2000_Total_Births', '2002_Total_Births', '2004_Total_Births', '2006_Total_Births', '2008_Total_Births']]

# Reshape the data for visualization
expandedDataFrame = pd.melt(selected_data_frame, id_vars='Age of mother', var_name='Year', value_name='Total Births')
expandedDataFrame['Year'] = expandedDataFrame['Year'].str.replace('_Total_Births', '').str.strip()
expandedDataFrame = expandedDataFrame.reset_index(drop=True)

# Create a line plot to visualize the data
plt.figure(figsize=(18, 18))
sns.lineplot(data=expandedDataFrame, x='Year', y='Total Births', hue='Age of mother', marker='o')

# Customize the plot
plt.title("Ages of Women at the Time of Birth (1990-2008)")
plt.xlabel("Year")
plt.ylabel("Total Births")
plt.xticks(rotation=45)
plt.legend(title='Age of mother', loc='upper right')
plt.tight_layout()

# Show the plot
plt.show()

```

Idiom: Multiple Line Chart / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Total Births  (Not Necessarily the first) | value, quantitative | vertical spatial region (y-axis) |
| Year | value, Temporal | horizontal position on a common scale (x-axis) |
| Age of mother |value, categorical | Hue |


A multi-line chart is an ideal choice for visually depicting and contrasting the changes in "Age at Birth" across various maternal age groups over time, as represented by the "Year" variable. Each horizontal line within the graph corresponds to a specific age category, making it easy to compare how the ages at which individuals in each group give birth vary over multiple years. This chart effectively showcases the fluctuations in age groups concerning the common variable, namely the year, making it easier to discern temporal trends and patterns within the data spanning from 1990 to 2008.

### Further Questions: What further questions does this prompt? What hypotheses do you have about what the answers might be? Are there other tables that might help you address these questions?

#### Solution -

1. *Question* - Which elements have played a role in the steady increase in birth rates for women aged 40-44 and 35-39 during the last decade? One possible theory is that advancements in healthcare and fertility treatments might have extended the window for older women to conceive. Additionally, shifts in societal norms and expanded career opportunities could have influenced decisions related to family planning.

2. *Question* - Why did the fertility rate for women aged 25-29 fluctuate between 1995 and 2004, then increase between 2004 and 2008?
   *Hypothesis* - It's plausible that economic and social circumstances played a significant role. A stable economy may have led to a rise in pregnancies, while economic uncertainty might have caused delays in family planning.

Link to the Python Notebook - https://colab.research.google.com/drive/1FxkWL1QvkThdarBii5A3c9we0ETvsOHO?usp=sharing

## References -

1. https://seaborn.pydata.org/

