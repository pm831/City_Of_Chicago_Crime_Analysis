# Chicago Crime Data Visualization & Severity Modeling
### Pujan Malavia

![chicagocity](https://user-images.githubusercontent.com/19572673/62322030-1b5f1b80-b472-11e9-8b62-a8f5b56383f7.jpg)

### Abstract:

Every day, there are a numerous amount of crimes that occur across the country and the world. This can include major metropolitan areas with high populations and business activity. In this analysis, we look at the city of Chicago. What makes a Chicago dangerous? What types of crimes occur in within Chicago, primarily at the zip level? Which zips/areas have the highest concentration of crimes? What is the level of 'seriousness' for these crimes? Which zips/areas have the highest concentration of serious crimes? And after find that out, what days/times do they occur?  All of these questions are looked at in the analysis below.

### Industry:

Government Administration

### Overview:

Crime in Chicago has been tracked by the Chicago Police Department's Bureau of Records since the beginning of the 20th century. The city's overall crime rate, especially the violent crime rate, is higher than the US average. Chicago was responsible for nearly half of 2016's increase in homicides in the US, though the nation's crime rates remain near historic lows. The reasons for the higher numbers in Chicago remain unclear. An article in The Atlantic detailed how researchers and analysts had come to no real consensus on the cause for the violence.

https://en.wikipedia.org/wiki/Crime_in_Chicago

https://www.chicago.gov/city/en.html

Approximately 10 people are shot on an average day in Chicago.

http://www.chicagotribune.com/news/data/ct-shooting-victims-map-charts-htmlstory.html 

http://www.chicagotribune.com/news/local/breaking/ct-chicago-homicides-data-tracker-htmlstory.html 

http://www.chicagotribune.com/news/local/breaking/ct-homicide-victims-2017-htmlstory.html

### Use Case:
Building a model to predict the severity of a crime in Chicago as well as visualizing the frequency of crimes when compared to poverty rates.

### Initial Dataset(s):
Chicago Crimes Dataset 

### Software:
Python, PowerBI, Tableau

### Techniques: 

Random Forest

### Data Context:

This dataset reflects reported incidents of crime (with the exception of murders where data exists for each victim) that occurred in the City of Chicago from 2001 to present, minus the most recent seven days. Data is extracted from the Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting) system. In order to protect the privacy of crime victims, addresses are shown at the block level only and specific locations are not identified. This data includes unverified reports supplied to the Police Department. The preliminary crime classifications may be changed at a later date based upon additional investigation and there is always the possibility of mechanical or human error. Therefore, the Chicago Police Department does not guarantee (either expressed or implied) the accuracy, completeness, timeliness, or correct sequencing of the information and the information should not be used for comparison purposes over time.

https://www.kaggle.com/chicago/chicago-crime

Update Frequency: Daily

Fork this kernel to get started.

Acknowledgements

https://bigquery.cloud.google.com/dataset/bigquery-public-data:chicago_crime

https://cloud.google.com/bigquery/public-data/chicago-crime-data

Dataset Source: City of Chicago

This dataset is publicly available for anyone to use under the following terms provided by the Dataset Source —https://data.cityofchicago.org — and is provided "AS IS" without any warranty, express or implied, from Google. Google disclaims all liability for any damages, direct or indirect, resulting from the use of the dataset.

Banner Photo by Ferdinand Stohr from Unplash. 

### Data Fields:

** unique_key: Unique identifier for the record.

** case_number: The Chicago Police Department RD Number (Records Division Number), which is unique to the incident.

** Date Date: when the incident occurred. this is sometimes a best estimate.

** Block: The partially redacted address where the incident occurred, placing it on the same block as the actual address.

** Iucr: The Illinois Unifrom Crime Reporting code. This is directly linked to the Primary Type and Description. See the list of IUCR codes at https://data.cityofchicago.org/d/c7ck-438e.

** primary_type: The primary description of the IUCR code.

** Description: The secondary description of the IUCR code, a subcategory of the primary description.

** location_description: Description of the location where the incident occurred.

** Arrest: Indicates whether an arrest was made.

** Domestic: Indicates whether the incident was domestic-related as defined by the Illinois Domestic Violence Act.

** Beat: Indicates the beat where the incident occurred. A beat is the smallest police geographic area – each beat has a dedicated police beat car. Three to five beats make up a police sector, and three sectors make up a police district. The Chicago Police Department has 22 police districts. See the beats at https://data.cityofchicago.org/d/aerh-rz74.

** District: Indicates the police district where the incident occurred. See the districts at https://data.cityofchicago.org/d/fthy-xz3r.
** Ward: The ward (City Council district) where the incident occurred. See the wards at https://data.cityofchicago.org/d/sp34-6z76.
community_area: Indicates the community area where the incident occurred. Chicago has 77 community areas. See the community areas at https://data.cityofchicago.org/d/cauq-8yn6.

fbi_code: Indicates the crime classification as outlined in the FBI's National Incident-Based Reporting System (NIBRS). See the Chicago Police Department listing of these classifications at http://gis.chicagopolice.org/clearmap_crime_sums/crime_types.html.

x_coordinate: The x coordinate of the location where the incident occurred in State Plane Illinois East NAD 1983 projection. This location is shifted from the actual location for partial redaction but falls on the same block.

y_coordinate: The y coordinate of the location where the incident occurred in State Plane Illinois East NAD 1983 projection. This location is shifted from the actual location for partial redaction but falls on the same block.

Year: Year the incident occurred.

updated_on: Date and time the record was last updated.

Latitude: The latitude of the location where the incident occurred. This location is shifted from the actual location for partial redaction but falls on the same block.

Longitude: The longitude of the location where the incident occurred. This location is shifted from the actual location for partial redaction but falls on the same block.

Location: The location where the incident occurred in a format that allows for creation of maps and other geographic operations on this data portal. This location is shifted from the actual location for partial redaction but falls on the same block.

### Summary:
The bottom-line goal is to figure out specific Chicago Zips with the highest number of crimes reported within a period of time. Up on the User Interface, there is a 'date range' slicer to which the user can select the appropriate time frame. To drill down, there is a 'Primary Type' slicer which defines the type of crime. To test the severity of the crime, there are the 'Arrest?' and Domestic? slicers. To figure out what type of location crime happened, there is the 'Location' slicer.
When the end-user clicks on one of the options, the entire dashboard/UI drills down further to get into the point of interest, including the 'Word Cloud' and 'Heat Map'. The word cloud provides a more detailed description of the crime. The Heat Map provides the latitude and longitude coordinates of the zip as well as a special color scheme. The higher the number of crimes in the zip, the bigger and darker the circle. So from a simple 'business' perspective, the problem solving process to decrease the rate of a particular type of crime within a Zip/Area would start at the aforementioned.

### Data Curation Process:

The two classification algorithm I used was the Random Forest. The Random Forest is a bagging technique where a certain number of decision trees are grown on different subsets of the training data. It is also known to have low bias and high variance and has an equal amount of say in the final decision in modeling. 

I performed the following data preparation/data visualization techniques.

Data Preparation/Data Visualization

Python (Jupyter Notebook) Visualization:
https://github.com/pm831/City_Of_Chicago_Crime_Analysis/blob/master/Chicago%20Crime%20Analysis.ipynb

1. Imported Chicago crimes dataset and zip code dataset.

2. Treated missing values by removing NAs (Chicago crimes dataset).

3. Filtered the dataset to reflect years with the most activity (Chicago crimes dataset).

4. Joined the zip code dataset to existing Chicago Crimes dataset based on lat and long coordinates. 

5. Filtered only Top 25 'Primary Type' counts for Crime (for relevance) and dropped 'OTHER'.

6. Created a defined list of severe crimes where:

7A. If 'Primary Type' equals one of defined list of severe crimes, the new column would mark it as severe (1). 

7B. If 'Primary Type' does not equal one of defined list of severe crimes, new column would be labeled as not severe (0).

7C. Crime severity column eventually becomes the response variable. 

8. Filtered only Top 25 Location Description counts for Crime (for relevance).

9. Filtered only Top 22 District counts for Crime (for relevance) and rename levels of District levels of taxonomy.

10. Created dummy variables for 'Primary Type' and 'District' which would be used later in the random forest model.

11. Created new columns from the date column (time_24hour, Timeblock, Date_no_time, Weekday).

12. Create dummy variables for Timeblock and Weekday respectively.

13. After this process, dropped NaNs in the dataframe.

14. Imported and joined the provertys dataset to exisitng Chicago crimes dataset. 

15. Created dummy variables for 'Location Description' and dropped 'OTHER'.

16. Created Horizontal bar plot for 'Number of crimes by type'.

Number of Crimes by Type:

![output_43_0](https://user-images.githubusercontent.com/19572673/85777642-cbbfb900-b6ef-11ea-9d1a-617670106ada.png)

17. Calculated Occurrence rates of the various types of crime, Location Description and plotted via bar plot.

Occurence Rate: Types of Crimes:

![output_45_1](https://user-images.githubusercontent.com/19572673/85777645-cbbfb900-b6ef-11ea-9edb-d66986a5594d.png)

Occurence Rate: Scene of Crimes:

![output_48_1](https://user-images.githubusercontent.com/19572673/85777646-cbbfb900-b6ef-11ea-9d98-5b03e14118e9.png)

18. Created new columns from the date column (time_hour, month).

19. Calculated Occurrence rates of the hour of crime, day of crime, month of crime and plotted via bar plot.

Occurence Rate: Hour Crime Occured:

![time_hour](https://user-images.githubusercontent.com/19572673/85807848-19084e80-b721-11ea-97f0-d54b746d850e.png)

Occurence Rate: Day Crime Occured:

![day](https://user-images.githubusercontent.com/19572673/85807843-17d72180-b721-11ea-829b-8b805371e07f.png)

Occurence Rate: Month Crime Occured:

![month_occurence](https://user-images.githubusercontent.com/19572673/85807844-186fb800-b721-11ea-9b16-f9da02debc97.png)

20. Created a new column (from pre-built function) that would take the top 4 types of 'Primary Type' and label the rest as 'Other' for 5 levels of the new taxonomy.

21. Plotted Normalized Crime Types by Location, Time, Day, Month (from pre-built function).

Normalized Crime Types by Location:

![Normalized_Crime_By_Location](https://user-images.githubusercontent.com/19572673/85807846-186fb800-b721-11ea-8a71-62c76ac14967.png)

Normalized Crime Types by Time:

![Normalized_Crime_By_Hour](https://user-images.githubusercontent.com/19572673/85808259-4f929900-b722-11ea-9977-966c165b1fe7.png)

Normalized Crime Types by Day:

![Normalized_Crime_By_Day](https://user-images.githubusercontent.com/19572673/85807845-186fb800-b721-11ea-9d62-251c2f568007.png)

Normalized Crime Types by Month:

![Normalized_Crime_By_Month](https://user-images.githubusercontent.com/19572673/85807847-186fb800-b721-11ea-8986-99de6d18a558.png)

22. Plotted Time Series Graph (in 30 day intervals) of crime rates types.

Crime Rates: Forecast:

![output_68_0](https://user-images.githubusercontent.com/19572673/85777648-cc584f80-b6ef-11ea-9813-a553ce41edd0.png)

23. Plotted heat map of crime types correlation based on arrest or domestic (to note seriousness of crime).

Heatmap: Crime types correlation based on arrest or domestic (to note seriousness of crime)

![output_69_1](https://user-images.githubusercontent.com/19572673/85777649-cc584f80-b6ef-11ea-978e-d4b8ced1c64c.png)

24. Plotted heat map of the following: Hour by Location, Hour by Type, Hour by Week, Day of Week by Location, Day of Week by Type, Location by Type.

Heatmap: Hour by Location

![output_73_1](https://user-images.githubusercontent.com/19572673/85777650-ccf0e600-b6ef-11ea-8fcd-dd940d4158b1.png)

Heatmap: Hour by Type

![output_74_1](https://user-images.githubusercontent.com/19572673/85777651-ccf0e600-b6ef-11ea-899b-7648f8649161.png)

Heatmap: Hour by Week

![output_75_1](https://user-images.githubusercontent.com/19572673/85777652-ccf0e600-b6ef-11ea-9bb5-02339b2a39f9.png)

Heatmap: Day of Week by Location

![output_76_1](https://user-images.githubusercontent.com/19572673/85777654-ccf0e600-b6ef-11ea-851f-a620f41cc7af.png)

Heatmap: Day of Week by Type

![output_77_1](https://user-images.githubusercontent.com/19572673/85777655-ccf0e600-b6ef-11ea-9a6d-c79b245a2c98.png)

Heatmap: Normalized location frequency for each crime:

![output_78_0](https://user-images.githubusercontent.com/19572673/85777656-cd897c80-b6ef-11ea-9858-ec3454df0f75.png)

25. Wrote this dataset out which would then be used in PowerBI/Tableau for other visualization purposes.

Old PowerBI Data Visualization (by Zip Code):
https://github.com/pm831/City_Of_Chicago_Crime_Analysis/blob/master/Chicago_Crimes_Visualization.pbix

![Chicago_Zip_Code_Crime_Analysis](https://user-images.githubusercontent.com/19572673/57345072-8f11b680-7117-11e9-90d0-8a55e88f4544.PNG)

Date Range:

![Chicago_Crimes_Slicers](https://user-images.githubusercontent.com/19572673/60401626-8dca9c00-9b52-11e9-9918-5ee940b8040d.PNG)

Word Cloud:

![Chicago_Crimes_WordCloud](https://user-images.githubusercontent.com/19572673/60401686-3b3daf80-9b53-11e9-8f85-a523b2b5976a.PNG)

Zip Heat Map:

![Chicago_Crimes_HeatMap](https://user-images.githubusercontent.com/19572673/60401685-3b3daf80-9b53-11e9-9fc2-81c5e6cfe324.PNG)

PowerBI Data Visualization (new and modified):

![Map Viz](https://user-images.githubusercontent.com/19572673/85783658-84d4c200-b6f5-11ea-8caf-9a5a2c09ebc9.PNG)

Tableau Data Visualization (new and modified):
https://public.tableau.com/profile/pujan.malavia#!/

![Crimes vs  Poverty Viz](https://user-images.githubusercontent.com/19572673/85777591-c2cee780-b6ef-11ea-98c3-439e6d88437e.PNG)

Modeling

26. Took a sample of 100000 to reduce the time it takes to run the model.

27. Dropped columns that were categorical in nature as variables that are numerical or categorical columns that are ordinal in nature are used as predictors.

28. Plotted out normalized z-score graphs that compares severity (Severe vs. Nonsevere) of Latitude, Longitude, House_below_poverty, Unemployed, Under_18_over64, Income, and Hardship Index.

![output_95_0](https://user-images.githubusercontent.com/19572673/85777657-cd897c80-b6ef-11ea-9e80-d5d85b7e7218.png)

29. Plotted out normalized z-score graphs that compares severity (Severe vs. Nonsevere) of Latitude, Proportion of House Below Poverty, Proportion Unemployed, Proportion with Age Under 18 Over 64, and Income per Capita. 

![output_96_0](https://user-images.githubusercontent.com/19572673/85777659-cd897c80-b6ef-11ea-8205-9d75a79045ba.png)

30. Plotted indicator variables ('Police District 11', 'Time: 3am-6am', 'Time: 9am-12pm', 'Time: 12pm to 3pm', 'Location: apartment', 'Location: street') that will be good predictor for whether a crime will be severe or not.

![output_97_0](https://user-images.githubusercontent.com/19572673/85777660-ce221300-b6ef-11ea-9c06-025c3fe39a2f.png)

31. Created baseline model of Severe vs. Non-Severe where would take the number of case numbers that are severe/not severe and dividing it by the total to get the %.

32. Built a random forest model which gave roughly a 95% accuracy for the training set and a 67% accuracy for the test set.

Training Accuracy comparison between Baseline model and Random Forest

![output_104_1](https://user-images.githubusercontent.com/19572673/85777661-ce221300-b6ef-11ea-847d-1a35592ef12c.png)

Testing Accuracy comparison between Baseline model and Random Forest

![output_105_1](https://user-images.githubusercontent.com/19572673/85777662-ce221300-b6ef-11ea-95bc-aeabb4eeb4e0.png)

### Communication of Results to Business Partner:

To a business partner, I would explain that the Random Forest (all else equal) would work better for complex data (high variance, low bias) that’s a bit more unknown in terms of predictors’ effect on the response variable since it looks at all predictor variables equally in terms of its importance. 

### Future Work: 

Continue to do hyperparameter tuning of the model and creating new features/removing old features to help increase the prediction accuracy of the model

Try other types of models to see if the accuracy rate improves

More data visualization/patterns within the dataset (external sources) that can lead to more insights and decision-making from a business perspective
