<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Visualize data with QuickSight

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-analytics-quicksight)

**Author:** Abdulrahman Abdulkadir  
**Email:** abdabdulkadir62@gmail.com

---

![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_6c7f7ef0)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create a full data visualization pipeline using Amazon QuickSight. I'm doing this project to learn how to work with AWS services, specifically S3 and QuickSight, and to gain hands-on experience in turning raw data into meaningful insights.

### Tools and concepts

The services I used were Amazon S3 and Amazon QuickSight. I used S3 to store and manage my dataset files, including the CSV file and the manifest.json file, and I used QuickSight to connect to that data, create visualizations, and publish an interactive dashboard.

Key concepts I learnt include how to set up and configure an S3 bucket, how to structure and use a manifest.json file to guide data imports, how to connect QuickSight to external data sources, and how to build meaningful visualizations with filters, chart types, and dashboard layouts. I also learned how to refresh data, publish dashboards, and export them as PDFs for sharing.


### Project reflection

This project took me approximately a few hours to complete, including data preparation, connecting services, creating visualizations, and finalizing the dashboard. The most challenging part was making sure the data was correctly structured and ensuring QuickSight could properly read it through the manifest.json file. It was most rewarding to see the final dashboard come together, with clean, interactive visualizations that clearly communicated insights from the dataset.


After this project, I plan to work on a new data analysis project that focuses on user engagement metrics from a web or app dataset. This will help me practice working with time-series data, user behavior patterns, and more advanced dashboard interactions. I will start this project on the coming Monday, giving myself enough time to gather a suitable dataset and outline the key questions I want to explore.


---

## Upload project files into S3

S3 is used in this project to store two files, which are the CSV dataset file and the manifest.json file. The CSV file contains the raw data that will be analyzed and visualized in Amazon QuickSight, while the manifest.json file tells QuickSight where to find the CSV file in the S3 bucket and how to interpret its structure.


I edited the manifest.json file by updating the "URIs" field to include the exact S3 URI of my uploaded CSV file. It’s important to edit this file because Amazon QuickSight uses the manifest.json to locate the dataset within the S3 bucket and understand how to load it. If the URI is incorrect or missing, QuickSight won’t be able to access the data for analysis.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_3c3cd85a)

---

## Create QuickSight account

Creating a QuickSight account while using the AWS Free Tier costs nothing **if you choose the Standard edition and activate the free trial**. The free trial gives you 30 days of access to Amazon QuickSight with up to 4 users. During this period, you can explore its features without incurring charges, as long as you don’t exceed the limits or upgrade to the Enterprise edition. Always make sure to select the Standard edition and double-check that the free trial is activated during signup to avoid unexpected costs.


Creating an account took me about 10 to 15 minutes. This included signing in to my AWS account, choosing the correct region, selecting the Standard edition with the free trial, configuring permissions to allow QuickSight access to S3, and completing the setup process.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_f4ab4214)

---

## Download the Dataset

I connected the S3 bucket to QuickSight by visiting the QuickSight console, going to the "Manage QuickSight" section, and selecting "Security & permissions." From there, I enabled access to Amazon S3 and selected the specific S3 bucket where my dataset and manifest.json file are stored. After saving the changes, QuickSight was able to access the data from my bucket.


The manifest.json file was important in this step because it tells QuickSight exactly where to find the CSV file in the S3 bucket and how to interpret its structure. It includes the S3 URI of the dataset and specifies details like the file format, whether it contains headers, and how the data is delimited. Without this file, QuickSight wouldn’t be able to locate or properly load the data for analysis.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_6f874996)

---

## My first visualization

To create visualizations on QuickSight, I first selected the dataset I imported from S3. Then, I clicked on "New analysis" and chose the dataset as the source. From there, I used the fields pane to drag and drop different columns into the visual editor. I selected various chart types like bar charts, line graphs, and pie charts depending on the kind of insight I wanted to show. I also customized each visualization by adjusting the axes, applying filters, changing colors, and renaming titles to make the visuals clearer and more meaningful.


The chart shown here is a breakdown of the number of titles released each year. This helps visualize trends over time and shows which years had the highest or lowest number of releases.
To create this visualization, I dragged the release\_year field into the graph area. QuickSight automatically generated a bar chart, showing the count of titles for each year. This simple chart gives a clear view of how content production has changed over time, and it can be further customized by adding filters, sorting by year, or grouping by categories like genre or country.



I created this graph by dragging and dropping the release\_year and type fields into the visual editor in QuickSight. This allowed me to break down the number of Netflix titles by year and separate them based on whether they are movies or TV shows. The result is a clear visual that shows how content production has changed over time and highlights the differences between movie and TV show releases.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_aff3aad7)

---

## Using filters

Filters are useful for narrowing down the data to focus on specific segments, which makes it easier to analyze patterns and answer targeted questions. They allow you to exclude irrelevant information and view only the data that matches certain criteria, such as a particular country, genre, release year, or rating. This helps in drawing more accurate insights and comparing specific subsets within the larger dataset.


This visualization shows a breakdown of the number of movies and TV shows released each year. Here, I added a filter by type to separate the two categories and used a 100% stacked bar chart to compare the proportion of each per year. This made it easier to see how the balance between movies and TV shows has changed over time.

Based on this, Netflix's data team requested further insights. I continued building the dashboard by duplicating visuals and applying new filters. For example, I used filters to isolate specific genres like “Action & Adventure”, “TV Comedies”, and “Thrillers”, and another filter to show how many of those titles were released from 2015 onward. Each chart answered a specific question, helping build a detailed and organized visual report.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_c32248c5)

---

## Setting up a dashboard

ChatGPT said:
As a finishing touch, I added clear, descriptive titles to each of my charts so that anyone viewing the dashboard can immediately understand what each visualization is showing. I matched titles like “# of Movies/TV Shows by Release Year,” “# of Titles Added by Date,” and “# of Thrillers, TV Comedies, Action & Adventure (released ≥ 2015)” to the appropriate graphs. These titles not only improve readability but also make the insights more accessible to others reviewing the dashboard.

Did you know you could export your dashboard as PDFs too? I did this by clicking on the Export icon in the top right corner of the QuickSight dashboard. From the dropdown, I selected Generate PDFs, waited a few moments for the file to process, and then clicked Download once the green banner appeared. This gave me a clean, shareable version of my dashboard that I can include in reports or presentations.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_6c7f7ef0)

---

## Refreshing source data

In this project's extension, I downloaded fresh data that's different from my original dataset because the initial dataset was either outdated or missing key information needed to answer more advanced questions. Using an updated dataset allows for more accurate and meaningful insights, especially when trends or content availability may have changed over time.

Analysing incomplete data brings the risk of drawing incorrect conclusions, overlooking important patterns, or making decisions based on outdated or irrelevant information. Refreshing the dataset ensures that the analysis remains reliable and reflective of the most current reality.


Once I downloaded new data, I had to update my S3 bucket because QuickSight pulls its data directly from there, and keeping the bucket updated ensures that all visualizations reflect the most recent information. Replacing the old CSV file with the new one in the bucket allows QuickSight to access the fresh dataset without changing the overall setup.
I also uploaded a new manifest.json file that points to the updated CSV file and accurately describes its structure, including the correct S3 URI, file format, and other configuration details. This ensures QuickSight can properly read and load the new data for analysis.


I initially couldn't see my updated data in QuickSight, so I had to refresh the dataset manually. I did this by going to the dataset settings in QuickSight and selecting the option to **refresh** or **ingest** the data again. This step was necessary because QuickSight doesn't automatically detect changes in the S3 files. After the refresh, the updated data appeared correctly in my visuals and dashboard.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-analytics-quicksight_86415f4e3)

---

---
