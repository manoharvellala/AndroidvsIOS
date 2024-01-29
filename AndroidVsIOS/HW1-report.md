# HW 1 - CS 625, Fall 2023

Manohar Vellala
Due: September 6, 2023

## Git, GitHub

*What is the URL of the GitHub repo that you created in your personal account?
https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala
   
*In which direction does the 'pull' command work (send local changes to remote OR send remote changes to local)?*
   
*If you have committed a change on your local machine, but do not see the update on GitHub.com, what step might have you forgotten?*

## Markdown

- First list
- Second List
- Third List
* Write a single paragraph that demonstrates the use of italics, bold,bold italics, and code and includes a link. The paragraph does not have to make sense*

Understanding the material is *crucial* for gaining insight into the concepts of marks and channels, their interrelation, and the significance of luminance, saturation, and hue in visualization. __Equally__ important are the concepts of ***accuracy***, discriminability, `separability`, popout, and grouping. The link for this website is https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/edit/main/HW1-report.md

*Create a level 3 heading*
### Hello world

*Insert an image of an animal, sized appropriately*
<img src="lion.jpg" height="100" alt="This is a picture of myself.">

## Tableau

*Insert your the image of your final bar chart here. Reminder, this should show data from a region other than the South.*


## Google Colab

https://colab.research.google.com/drive/1xI25_FxFJP9PWo1Po_cs4Xinw5Scv3tX?usp=sharing

## Python/Seaborn

*Insert the first penguin chart here*
![jpg2](https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/jpg2.jpeg)

*Describe what the figure is showing.*
Represents the scatter plot depending on the corelation between the length and depth of the penguin's beak.

*Insert the second penguin chart here*
![jpg1](https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/jpg1.jpeg)

*Describe what the figure is showing.*
shows the bar plot of penguin's body mass broken by sepices.


*What happened when you removed the outer parentheses from the code? Why?*
The removal of the external brackets does not impact the code's functionality. Instead, it enhances readability and comprehension. This simplifies code composition, taking advantage of Python's support for method chaining.

## Observable and Vega-Lite

*What happens when you replace `markCircle()` with `markSquare()`?*
The effect of this replacement depends on the specific context and the programming or visualization library in use. Typically, when data points are generated on a graph or visualization using the methods markCircle() or markSquare(), the shape of the data points will transition from circles to squares.

*What happens when you replace `markCircle()` with `markPoint()`?*

The marker type undergoes another alteration when markPoint() is employed instead of markCircle(). In most cases, markPoint() is used to represent data points as dots with arbitrary shapes, which means your chart will depict data points as basic dots, as opposed to circles.

*What change do you need to make to swap the x and y axes on the scatterplot?*
To adjust the configuration of the x and y axes in the scatterplot's code, you can modify the variables assigned to them. For instance, consider the original code using markCircle(). You can make changes like switching from encode(x='variable1', y='variable2') to markCircle().encode(x='variable2', y='variable1') as an illustrative example.

*Insert the bar chart image here*
![barchart](https://github.com/odu-cs625-datavis/fall23-asv-manoharvellala/blob/main/barchart.jpeg)


*Why do you think this chart is the result of this code change?*

Initially Snipped Code:

In the first code snippet, the "Origin" field is used to group data on the Y-axis, while the X-axis represents the number of records for each origin.

Second Snippet of Code:

In the second code snippet, the Y-axis grouping based on the "Origin" field has been removed. Instead, the X-axis represents the count of all records, and there is no classification by origin. To display the record count without any Y-axis grouping based on the "Origin" column, the second code snippet only encodes the X-axis in a bar chart. This absence of Y-axis encoding results in a different visual representation.

## References

*Every report must list the references (including the URL) that you consulted while completing the assignment. Replace the items below with the references you consulted*

* Reference 1, <https://www.google.com>
* Reference 2, <https://www.chatgpt.com
