# AndroidvsIOS
Analyzed 2.3 million datasets from iOS and Android app stores to uncover key market trends. Identified significant disparities and User preferences in downloads, size, ratings, customer reviews, pricing, categories between the platforms.



# Comparative Analysis of Android and iOS Apps

title: "Final Project Report"
author: "Manohar Vellala"

---

CS 625, Fall 2023

### Project Details - Android vs iOS Apps

In recent years, there has been a significant surge in the adoption of smartphones. The two leading platforms, Android and iOS, dominate the market due to their user-friendly interfaces and robust computational capabilities, catering to a vast range of applications. This project involves a comprehensive comparison of Android and iOS apps sourced from their respective app stores. By extracting and analyzing data, we aim to discern disparities between these platforms in terms of downloads, size, ratings, customer reviews, pricing, and other factors. This analysis provides valuable insights into user preferences for the same apps on Android and iOS.

The objectives of this project are to: \* Clean and Perform exploratory data analysis on Android and iOS apps dataset.

### Datasets

[Android Dataset - First
Dataset](https://github.com/gauthamp10/Google-Playstore-Dataset) (2.3
million data)

Dataset taken through github, they collected the data with the help of Python and Scrapy running on a cluster of cloud virtual machines. The data was collected from Google play store on June 2021.
<https://github.com/gauthamp10/Google-Playstore-Dataset>

**Description of Android Dataset:**

We are using a csv file “android.csv”. Before getting into actual EDA,
we will familiarize with the variables:-

- App Name - Name of the App
- App Id - Id of the APP
- Category - Category under which the App falls.
- Rating count - Application’s rating on playstore
- Installs - Number of Installs of the App
- Minimum Installs - Maximum Installation Count of the App
- Maximum Installs - Minimum Installation Count of the App
- Free - Boolean (True/False)
- Price - Price of the app (0 if it is Free)
- Reviews - Number of reviews of the App.
- Size - Size of the App.
- Minimum Android - Supported Android Version
- Developer Id - ID of the Developer
- Developer Website - Developer webite
- Developer Email - Developer email is mentioned
- Released - App Release Date
- Last Updated - Date when the App was last updated
- Content Rating - Appropiate Target Audience of the App
- Privacy Policy - Link for the Privacy Policy Agreement
- Ad Supported - Is App is Ad Supported (Boolean)
- In App Purchases - Is App has in app purchases (Boolean)
- Editors Choice - Is app showed in Editors Choice (Boolean)
- Scraped Time - Data Scraped Time

[IOS Dataset - Second
Dataset](https://github.com/gauthamp10/apple-appstore-apps) (1.2 million
data)

IOS Dataset taken through github, they collected the data with the help of Python and Scrapy running on a cluster of cloud virtual machines. The data was collected from Apple AppStore on October 2021.
<https://github.com/gauthamp10/apple-appstore-apps>

**Description of IOS Dataset:**

We are using a json file “ios.json”. Before getting into Actual EDA, we
will familiarize with the Variables.

- App_Id: This column name represents the application unique Id
- App_Name: This column name represents the application name.
- AppStore_Url: This column name represents the application Store Url.
- Primary_Genre: This coloumn name represents the primary Genre under
  which the application falls.
- Content_Rating: This column name represents the Application content
  rating.
- Size_Bytes: This column name represents the application size (in
  bytes).
- Required_IOS_Version: This column name represents Required IOS version
  of the Application
- Released: This column name represents when the application is released
- Updated: This column name represents when the application is updated
- Version:This column name represents the application current version
- Price: This column name represents the price of the application
- Currency: This column name represents the Currency of the application
- Free: This column name represents whether the application is free or
  not to download
- DeveloperId: This column name represents the DeveloperId of the
  application
- Developer: This column name represents the application Developer name
- Developer_Url: This column name represents the developer Url of the
  application.
- Developer_Website: This column name represents the website of the
  developer of the application
- Average_User_Rating: This column name represents the Average users
  Rating on the application
- Reviews: This column name represents the end users Reviews on
  application
- Current_Version_Score: This column name represents the Current version
  score on the application
- Current_Version_Reviews: This column name represents the end users
  Reviews on current version of the application

### Exploration of First Dataset (Android Datset)

### Number of categories of apps in the store and their respective count.

## Bar Chart:

- Idiom Used - Bar Chart

- Marks Used - Line (to encode attributes)

- Channels Used - X-axis, Y-axis and color (to encode attributes)

- Data Attributes, their attribute types, and channels used to encode
  those attributes

1.  Category - Categorical - Horizontal position (X-axis)
2.  Count - Quantative - Vertical Position (Y-axis)
3.  Count - Quantative - Color

![](./Img1.png)

- A bar chart is a type of chart that represents data with rectangular bars of lengths proportional to the values they represent.

- Bar charts are commonly used to compare and contrast various data points across several categories or groupings, such as quantities,
  frequencies, or percentages. The height or length of each bar reflects the size of the data being shown, and the bars can be horizontally or vertically oriented.

- To further distinguish between various categories or sub-groups, the bars can be colored or patterned. Labels or values can be be placed to each bar to provide further details.

- From the above bar chart, we can see that the top most category is Education followed by Music&Audio, Tools, Business and Entertainment.

### Exploring the Second Dataset (iOS Dataset)

### Number of categories of apps in the store and their count.

## Bar Chart

- Idiom Used - Bar Chart
- Marks Used - Lines
- Channels Used - X-axis, Y-axis
- Data Attributes, their attribute types and channels used to encode
  these attributes.

1.  Primary_Genre - Categorical - Horizontal position (X-axis)
2.  Count - Quantitative - Vertical Position (Y-axis)

![](./img3.png)

- A bar chart is a type of chart that represents data with rectangular bars of lengths proportional to the values they represent.

- Bar charts are commonly used to compare and contrast various data points across several categories or groupings, such as quantities,
  frequencies, or percentages. The height or length of each bar reflects the size of the data being shown, and the bars can be horizontally or vertically oriented.

- From the above bar chart, we can see that the top most category is Games followed by Business, Education, Utilities and Lifestyle.

### Genearting Specific Questions and Propose a Chart:

### Question 1: How are app ratings distributed across categories for both Android and iOS platforms?

#### Proposed Chart 1: Bar Chart

The average app rating for each category for both Android and iOS apps is displayed in the above bar graph. We can see the distribution of app ratings for Android and iOS apps in each category by comparing the bar heights for each category. When the bar for Android in a certain category is higher than the bar for iOS, it means that Android apps in that category have received higher ratings than iOS apps. In contrast, if the iOS bar in a given category is higher than the Android bar, it means that iOS apps in that category have received higher ratings than Android apps. So, the distribution of app ratings for Android and iOS apps in each category can be seen using this bar chart and compared.

- Idiom Used - Bar Chart

- Marks Used - Lines

- Channels Used - X-axis, Y-axis and color (to encode categories of iOS
  and Android)

- Data Attributes, their attribute types, and channels used to encode
  those attributes

1.  Category - Categorical - Horizontal position (X-axis)
2.  Average Rating - Quantitative - Vertical Position (Y-axis)
3.  Platform (iOS and Android) - Categorical - Color

![](./img6.png)

From the above graph, it is clear that, both android and iOS apps in the weather category have received highest ratings when compared with the other categories. iOS has received lowest rating in the productivity category and android has received lowest rating in food & drink category.

#### Proposed Chart 2: Line Chart

The utilization of a Line Chart is another method to address this inquiry. By creating a line chart with axes representing the mean ratings of each category for Android and iOS platforms, respectively, 'Category' names are presented on the x-axis, while 'Average Rating' values are depicted on the y-axis. The Android line is represented in blue, and the iOS line is portrayed in orange. To enhance clarity, labels for the x and y-axes, as well as a legend, can be incorporated into the plot.

- Idiom Used - Line Chart

- Marks Used - Lines (Dots)

- Channels Used - X-axis, Y-axis and color (to encode platform - iOS and
  Android)

- Data Attributes, their attribute types, and channels used to encode
  those attributes

1.  Category - Categorical - Horizontal position (X-axis)
2.  Average Rating - Quantitative - Vertical Position (Y-axis)
3.  Platform (Android/iOS) - Categorical - Color

![](./img8.png) From the above line graph, it appears that the weather category has the highest average rating for both Android and iOS apps, while the productivity category has the lowest average rating for iOS apps and the food & drink category has the lowest average rating for Android apps.

### Question: 2 - To find the distribution of app ratings for free and paid android and iOS apps

#### Proposed Chart: Grouped Bar Chart

This question can be answered using grouped bar chart. To visualize the distribution of app ratings for free and paid Android
and iOS apps, Grouped bar chart has been generated. The ratings data are separated into four subsets: free Android apps, paid Android apps, free iOS apps, and paid iOS apps. Afterwards, lists of app rating data are generated for each group. Then set the width of each bar in a figure with a single subplot. Furthermore, it changes the x-axis tick labels to “Free” and “Paid.”

The mean ratings for each subset are then plotted using bars, with the Android and iOS data side-by-side for easy comparison. The orange bars show iOS apps, whereas the blue bars show Android apps. Then added labels, a title, and a legend to the plot, with the title being “Distribution of App Ratings for Free and Paid Applications” and the x-axis and y-axis labels shows “App Type (free and paid)” and “Average Rating” respectively. The legend identifies which operating system is represented by which color. The chart’s overall comparison of average app ratings for free and premium Android and iOS apps is very apparent.

- Idiom Used - Grouped Bar Chart

- Marks Used - Lines (to encode attributes)

- Channels Used - X-axis, Y-axis and color (to encode attributes)

- Data Attributes, their attribute types, and channels used to encode
  those attributes

1.  App Type - Categorical - Horizontal position (X-axis)
2.  Average Rating - Quantitative - Vertical Position (Y-axis)
3.  Platform (Android/iOS) - Categorical - Color

![](./img10.png)

From the above grouped bar chart, we can say that the mean rating of
free iOS apps is higher than free android apps. The mean rating of paid
iOS apps is lower than the paid android apps.

### Conclusion and Final Thoughts

My final visualizations include a Line Chart illustrating the average ratings of Android and iOS apps across various categories. This chart reveals platform trends and identifies which platform has a higher average rating in each category. Notably, the weather category exhibits the highest average rating for both Android and iOS apps, while the productivity category shows the lowest average rating for iOS apps, and the food & drink category has the lowest average rating for Android apps. The chart's title, "Distribution of app ratings for Android and iOS apps in each category," aptly captures the comparison between the two platforms within each category.

The second chart, a "Grouped Bar Chart" titled "Distribution of app ratings for free and paid Android and iOS apps," portrays the average ratings for each app type (free and paid) on both platforms. This chart facilitates the comparison of ratings between different app types. Observing the bar graph, it becomes evident that free iOS apps generally have higher mean ratings compared to free Android apps, whereas paid Android apps tend to have higher mean ratings than paid iOS apps. The chosen title and chart style are appropriate, offering a clear comparison of average ratings for free and paid apps across both Android and iOS platforms.

Breaking down the project into three separate assignments allowed me to concentrate on specific tasks extensively, fostering a deeper understanding of the required techniques. Crafting detailed reports for each assignment, including the challenges encountered, provided a comprehensive overview of the completed work. This segmented approach not only enhanced comprehension but also offered a more profound understanding of the concepts compared to a single final project.

Link to the Google Collab can be found here:
<https://drive.google.com/file/d/1lvTx8XXKVtT5knvHumG8O7fGp6uR5l4Y/view?usp=sharing>

### References

- <https://pandas.pydata.org/docs/user_guide/merging.html>

- <https://plotly.com/python/pie-charts/>

- <https://plotly.com/python/bar-charts/#stacked-bar-chart>

- <https://www.journaldev.com/33492/pandas-dropna-drop-null-na-values-from-dataframe>

- <https://www.geeksforgeeks.org/applying-lambda-functions-to-pandas-dataframe/>

- <https://www.markdownguide.org/basic-syntax/>

- <https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.fillna.html>

- <https://pandas.pydata.org/pandas-docs/version/0.23/generated/pandas.core.groupby.DataFrameGroupBy.agg.html>
