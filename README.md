# website-traffic-analysis

To replicate the analysis and generate visualizations using IBM Cognos and Python for the project website traffic analysis, you can follow these steps:

#### **IBM Cognos:**

1. Create a new Cognos report.
2. Add the following data sources to the report:
    * The website traffic analysis dataset
    * The geomap data source (optional)
3. Create a new query to calculate the page loads, unique visits, first-time visits, and returning visits for each day, day of the week, and source.
4. Create a new report item to visualize the results of the query. For example, you could create a bar chart to show the page loads by day of the week or a pie chart to show the unique visits by source.
5. Run the report and review the results.

#### **Python:**

1. Install the necessary Python libraries, including pandas, matplotlib.pyplot, and geopandas (optional).
2. Load the website traffic analysis dataset into a Pandas DataFrame.
3. Calculate the page loads, unique visits, first-time visits, and returning visits for each day, day of the week, and source.
4. Create visualizations using the matplotlib.pyplot library. For example, you could create a line chart to show the trend of page loads over time or a bar chart to show the distribution of traffic by source.
5. Save the visualizations to files.

#### **Replicating the analysis:**

To replicate the analysis, you can use the following Python code:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load the data set into a Pandas DataFrame
df = pd.read_csv('daily-website-visitors - daily-website-visitors.csv')

# Calculate the page loads per day
page_loads_per_day = df['Page.Loads'].groupby(df['Date']).sum()

# Create a line chart showing the trend of page loads over time
plt.plot(page_loads_per_day.index, page_loads_per_day.values)

# Set the title and axis labels
plt.title('Trend of Page Loads over Time')
plt.xlabel('Date')
plt.ylabel('Page.Loads')

# Show the plot
plt.show()

page_loads_by_day = data.groupby('Day.Of.Week')['Page.Loads'].sum()

# Define labels for the pie chart (day names)
labels = page_loads_by_day.index

# Define the sizes (page loads)
sizes = page_loads_by_day.values

# Explode a specific slice if needed (e.g., 'Sunday')
explode = (0.1, 0, 0, 0, 0, 0, 0)  # 0.1 means 'Sunday' slice will be slightly separated

# Create a pie chart
plt.figure(figsize=(8, 8))
plt.pie(sizes, explode=explode, labels=labels, autopct='%3.3f%%', startangle=140)
plt.title('Distribution of Page Loads by Day of the Week')
plt.axis('equal')  # Equal aspect ratio ensures that pie is drawn as a circle.

# Display the pie chart
plt.show()

This code will generate two visualizations:

* A line chart showing the trend of page loads over time
* A pie chart showing the distribution of traffic by source

![Screenshot (263)](https://github.com/dataanalytics-project/website-traffic-analysis-phase1/assets/146163978/ad05c299-b13c-4390-a4f5-f19727cbb13f)
![Screenshot (265)](https://github.com/dataanalytics-project/website-traffic-analysis-phase1/assets/146163978/606cbc51-2133-4e82-a1e0-3a1ac591640c)



You can use these visualizations to replicate the analysis that was performed in IBM Cognos.

#### **Generating visualizations:**

To generate visualizations using Python, you can use the matplotlib.pyplot library. This library provides a variety of functions for creating different types of charts.

For example, to create a bar chart showing the Unique Visits by Day of Week, you could use the following code:

```python
import matplotlib.pyplot as plt
plt.figure(figsize=(10, 6))
sns.barplot(x='Day.Of.Week', y='Unique.Visits', data=data, ci=None)
plt.title('Unique Visits by Day of Week')
plt.xlabel('Day of Week')
plt.ylabel('Unique Visits')
plt.show()

For example, to create a bar chart showing the Boxplot of Page Loads by Day of Week, you could use the following code:

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt

# Read the data from the CSV file
data = pd.read_csv('daily-website-visitors - daily-website-visitors.csv')

# Create a boxplot of the Page.Loads column
sns.boxplot(
    x=data['Day.Of.Week'],
    y=data['Page.Loads'],
    showmeans=True
)

# Set the title and labels of the plot
plt.title('Boxplot of Page Loads by Day of Week')
plt.xlabel('Day of Week')
plt.ylabel('Page Loads')

# Show the plot
plt.show()

For example, to create a bar chart showing the Source Analysis by Day of the Week, you could use the following code:

import pandas as pd
import matplotlib.pyplot as plt

# Group the data by source, e.g., 'Day.Of.Week' or 'Date'
# You can choose the appropriate column for your source analysis
source_data = df.groupby('Day.Of.Week')['Page.Loads'].sum()

# Plot the source data
plt.figure(figsize=(10, 6))
source_data.plot(kind='bar')
plt.title('Source Analysis by Day of the Week')
plt.xlabel('Day of the Week')
plt.ylabel('Page Loads')
plt.show()

For more visualizations and for more data refer our documents 
