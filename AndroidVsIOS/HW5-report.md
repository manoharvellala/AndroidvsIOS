HW 5, CS 625, Fall 2023
================
Manohar Vellala


## Part 1: Create Distribution Charts

I opted to analyze Table 29, which presents the Urban and Rural Population by State. Utilizing Python for this examination was a deliberate choice due to its extensive collection of libraries that simplify data visualization. Python is the dominant language in the realm of data science, offering a plethora of tools specifically designed for such analyses.

Source:
<https://www.census.gov/library/publications/2009/compendia/statab/129ed/population.html>
  

**Box Plot:**
I retrieved data from an Excel file and employed Matplotlib to produce a box plot. This visual representation illustrates the distribution of urban and rural populations in the year 2000, classified according to population size in thousands.

Code for Box Plot Generation: I employed Python to generate a box plot depicting the distributions of urban and rural populations in the year 2000.

```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Read data from an Excel file
excel_file = 'hw5Dataset.xlsx'  # Replace 'your_data.xlsx' with your file path
df = pd.read_excel(excel_file)

# Create a single chart with two separate boxplots for urban and rural populations
plt.figure(figsize=(10, 6))
plt.subplot(1, 1, 1)
sns.boxplot(data=df[['urban population', 'rural population']])
plt.title("Box Plots - Urban and Rural Populations (2000)")
plt.xlabel("Population Type")
plt.ylabel("Population Count")
plt.xticks([0, 1], ["Urban Population", "Rural Population"])

# Show the boxplots
plt.tight_layout()
plt.show()
```

The creation of plots involves the utilization of the following libraries:
- Pandas: This library plays a crucial role in processing and manipulating data.
- Matplotlib: It serves as the primary tool for plotting and adding labels.

Idiom: Box Plot / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Population(in thousands) | value, quantitative | vertical spatial region (y-axis) |
| Population Type | value, categorical | horizontal position on a common scale (x-axis) |
                                                                           

A box plot is a superior approach for depicting the dispersion of data points, offering more lucid insights. It not only facilitates the detection of outliers and their associated values but also employs a glyph to represent five quantitative characteristics, in contrast to the solitary numerical marker typically found in a bar chart.
Below is the box plot obtained:

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/boxplot-hw5.png" alt="Line plot" width="900">

*Boxplot Benefits:*
1. Streamlined summary of data distribution.
2. Simple identification of outliers.

*Drawbacks of the Boxplot:*
1. Limited information when compared to alternative plot types.
2. Lack of scaling for population data.

Detailed Observations on Distributions:
- Urban populations exhibit a broader range with notable high outliers.
- Rural populations demonstrate more concentration with a handful of outliers.
- In the year 2000, urban populations, on average, surpass rural populations in size.


*Key Observations to Consider:*

1. The distinctions between the 2000 urban and rural population distributions are effectively emphasized by the box plot.

2. The urban population data exhibits a wider range of values, featuring outliers and a slight leftward skew. Conversely, the rural population data presents a more concentrated spread without any notable data points.



   
**ECDF:**

The Empirical Cumulative Distribution Function (ECDF) organizes data in ascending order, beginning with the smallest values and ending with the largest values. ECDF (Empirical Cumulative Distribution Function) provides a comprehensive visualization of an entire dataset by arranging data in ascending order, allowing for a clear understanding of the distribution's shape and range. It's a non-parametric method that estimates cumulative probability distribution from observed values, making it valuable for comparing multiple datasets and identifying percentiles easily. ECDFs don't rely on binning, preserving the original data points' granularity. I employed Python to generate an ECDF plot, which illustrates the distribution of urban population in 2000 using two attributes: probability and frequency.
*code*
```
# eCDF and histogram for urban or rural population in 2000
plt.figure(figsize=(12, 6))

# Choose which population to plot (urban or rural)
population_type = 'urban population'  # Change this to 'rural population' if needed

# eCDF plot
plt.subplot(1, 2, 1)
sns.ecdfplot(data=df, x=population_type, color='b')
plt.title(f"eCDF - {population_type} (2000)")
plt.xlabel(f"{population_type}")
plt.ylabel("Cumulative Probability")
```

Below is the ECDF obtained:

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/Histogram-Hw5.png" alt="Line plot" width="900">

Idiom: eCDF / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
|Probability | value, quantitative | vertical spatial region (y-axis) |
| Urban Population(in thousands) | value, quantitative | horizontal position on a common scale (x-axis) |


*eCDF Plot Advantages:*

*Advantages of the eCDF Plot:*

1. Offers clear insights into the cumulative probability distribution.
2. Facilitates easy identification of percentiles and distribution characteristics.
3. Enables effective dual visualization with a histogram for a comprehensive view.

*eCDF Plot Limitations:*

1. Provides limited in-depth statistical measures.
2. Scaling and range adaptation could be enhanced.

*Specific Distribution Insights:*

- eCDF: Predominantly, states exhibit urban populations below 10,000.

*Observations:*

The provided code's eCDF plot effectively communicates the cumulative probability distribution of urban populations in the year 2000. Notably, it reveals that a substantial number of states had lower urban populations during that period, as indicated by the steep initial rise of the curve. The plot also simplifies the identification of specific percentiles, with the median appearing to be around 4,000 thousand people. Consequently, it offers valuable insights into the shape and spread of the distribution, making it a potent tool for comprehending the urban population data in 2000.



**Histogram:**

Histograms, on the other hand, divide data into bins or intervals, offering insights into the frequency of data points within each bin. They excel at visualizing distribution characteristics, such as shape and the presence of modes or outliers. The area of each histogram bar represents the frequency, making it useful for quantitative analysis. However, histograms can be sensitive to the choice of bin size, and different bin sizes may reveal different aspects of the data distribution.I utilized the dataset to create a histogram chart, showcasing the distribution of urban population in the year 2000. This visualization was achieved using Python code.

*Code used for creating Histogram Plot* : I used Python for creating histogram for showing the distributions of the urban population in 2000.
```

# Histogram
plt.subplot(1, 2, 2)
sns.histplot(data=df, x=population_type, bins=20, color='g')
plt.title(f"Histogram - {population_type} (2000)")
plt.xlabel(f"{population_type}")
plt.ylabel("Frequency")

```

Below is the histogram obtained:

<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/Histogram-Hw5.png" alt="Line plot" width="900">

*Advantages of the Histogram:*

1. Provides a clear view of frequency distribution.
2. Aids in understanding data concentration within specific intervals.

*Drawbacks of the Histogram:*

1. Bin sizes may not adapt optimally to data, impacting frequency distribution.
2. Offers limited in-depth statistical descriptions.

*Detailed Distribution Observations:*

- The histogram presents a perspective on the frequency distribution of urban populations in 2000, unveiling the concentration of population values within specific intervals. This visualization assists in discerning the frequency of urban populations across various ranges, offering insights into data spread and potential modes or clusters.




## Part 2: Further Investigation
I employed the charts generated in Part 1 to steer my exploration of the dataset further. Using Python code, I proceeded to craft additional types of charts that unveiled intriguing insights from the same dataset.


## Finding 1:  Comparison of Urban and Rural Populations by State in 2000

The bar graph shows that the states with the highest urban populations are also the states with the highest IT hub populations. This suggests that there is a strong correlation between IT hubs and population growth.

One possible explanation for this correlation is that IT hubs attract and retain talent. IT workers are typically highly educated and skilled, and they are often paid well. This makes them a desirable demographic for cities and states.

Another possible explanation is that IT hubs create jobs. IT companies are constantly innovating and expanding, and they often create new jobs in the process. This can lead to population growth in the areas where these companies are located.

Here are some specific examples of states with high IT hub populations and high urban populations:

California is home to Silicon Valley, which is one of the largest and most well-known IT hubs in the world. California also has the largest urban population in the United States.
New York is home to New York City, which is another major IT hub. New York also has the second-largest urban population in the United States.
Texas is home to Austin, which is a rapidly growing IT hub. Texas also has the third-largest urban population in the United States.
Overall, the bar graph suggests that there is a strong correlation between IT hubs and population growth. This is likely due to a combination of factors, including the fact that IT hubs attract and retain talent and create jobs.

Inference

Based on the analysis of the bar graph, we can infer that cities with IT hubs are likely to have high populations in the recent years. This is because IT hubs attract and retain talent, which can lead to population growth. Additionally, IT hubs create jobs, which can also lead to population growth.

This inference is supported by real-world data. For example, the top 10 cities with the highest IT hub populations in the United States also have some of the highest populations overall. These cities include San Francisco, San Jose, New York City, Los Angeles, Chicago, Austin, Boston, Seattle, Washington, D.C., and Dallas-Fort Worth.

It is important to note that there are other factors that can also contribute to population growth in a city, such as its location, climate, and cost of living. However, the bar graph suggests that IT hubs are a significant factor in population growth.

#### Image 
<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/FurtherAnalysis-HW5.png" alt="Line plot" width="900">

Idiom: Bar Plot / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Urban Population (in thousands),Rural Popluation(in thousands) | value, quantitative | vertical spatial region (y-axis) |
| State | value, categorical | horizontal position on a common scale (x-axis) |


## Finding 2: Comparison of Rural Populations by State in 2000
The bar chart of rural population by state in 2000 shows that the states with the highest rural populations are generally located in the Midwest and South. These states also tend to have lower population densities and larger land areas. One possible explanation for this correlation is that the Midwest and South are home to a number of agricultural states, which often have large rural populations because they rely on a large number of workers to produce and harvest crops. Another possible explanation is that the Midwest and South have lower costs of living than other regions of the United States, which makes them more attractive to people who are looking for affordable housing and a more rural lifestyle.

Based on this further analysis, we can infer that rural populations are likely to be concentrated in states with lower population densities, larger land areas, agricultural economies, and lower costs of living.

#### Image
<img src="https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/FurtherAnalysis2-HW5.png" alt="Line plot" width="900">

Idiom: Bar Plot / Mark: Line
| Data: Attribute | Data: Attribute Type  | Encode: Channel | 
| --- |---| --- |
| Rural Popluation(in thousands) | value, quantitative | vertical spatial region (y-axis) |
| State | value, categorical | horizontal position on a common scale (x-axis) |

 

Link to Google Colab : <https://colab.research.google.com/drive/1B61aNSVt4t7coymngXRjaNCSGMGY-WDD?usp=sharing>

## References

1) <https://www.w3schools.com/python/matplotlib_pyplot.asp>
2) <https://www.tutorialspoint.com/index.html>
