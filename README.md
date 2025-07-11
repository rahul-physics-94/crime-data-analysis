# crime-data-analysis
Libraries used:
1. pandas
2. matplotlib.pyplot
3. seaborn
4. numpy
5. plotly.express

The data has been read through the csv and date fields have been converted into the datetime fields using the to_datetime function of pandas
We have used lambda function to iterate over each subsequent row value and add new month and year columns. 

Data Specifications:
1. The data contains information about the incidence, occurrence reporting, area, time of the crime, nature of the crime, current status of the crime, and remarks about the crime.
2. The crime level is a categorical value with 1 denoting a non-serious offence and 2 denoting a serious offence
3. There are missing values in the vict descent, vict sex, vict age, and there are additional values that we will have to drop to make sense of the data
4. No information has been provided on the vict descent and what the code words mean

Needs to be checked: Outliers need to be removed, and the data range needs to be checked in order to accurately understand the trends and predict the data.

Data Analysis Tasks:
1. Clear, distinct trends between Age, Gender, Ethnicity, and Date range
2. Check the outliers of each segment and remove them
3. Commenting and adding in your notes in the coding sheets
4. Consolidation of graphs and data trends
Matplot lib is not able to plot the graphs properly hence we will use seaborn and plotly express to plot subplots and grpahs


You can iterate over the column names to obtain the unique values in each column and create bar graphs better to understand the distribution of data within the structure.

We will have to use a groupby function of the dataframe to count the number of crimes, and we can build models based on this; however, we will lose additional data on serious vs nominal crimes. 
We need one-hot encode the categorical data and create a separate dataframe using this. 

I have been able to get the data out of the system and clean the categorical values. We can create additional tables using the first one to create more understandable graphs and charts. 

The next step would include:
1. Create meaningful graphs and charts to understand the pattern of the data
2. Calculate the probability of crimes by various categories
3. Understand the trend in data and location trends using the main Excel sheet

Possible points of analysis:
1. Month-on-Month Trend
2. Year-on-Year Trend
3. Daily Trend
4. Age Distribution and Descent distribution while calculating the probability of a crime happening because of certain age brackets
5. Weapon and Crime Type Analysis

Future Steps:
1. Clean the data further
2. Implement the ARIMA and SARIMA models
3. Predict the future crime rates based on gender, ethnicity, and age

After the code is implemented:
1. Cleaning the code and leaving fewer remarks would be best. 
2. Adding comments is important
3. Creating a readme file
4. Uploading the code and graphs to GitHub
There are discrepancies between the crime occurrence date and reported date, this is concentrated around covid but the numbers are not substantial.

1. Find a method to display the data more efficiently
2. Check if the discrepancies are enough to train model to predict the age and crimes that are more likely to go unreported or get reported late
3. Find the kind of serious crimes that have been less reported or have a huge time gap between occurrence and reporting
This can be your further point of analysis and after this implement the ARIMA and SARIMA Models
 
Questions to be noted:
- [ ] Covid had an impact on crime reporting. What has been the impact of covid on crime reporting? The delay can be calculated based on the difference between the reporting day and occurrance days. 
    - [ ] We need to create a different new to include more information about the crime nature and reporting delays
    - [ ] As per the data, we can see that delay in reporting the crimes have reduced over the period between 2020 - 2025. This means that Covid had an impact on reporting of the crimes
        - [ ] Probability of miss reporting
        - [ ] Months of highest miss reporting and most amount of crimes
        - [ ] Probability of crime happening in a year and month period: both serious and nominal 
- [ ] Among the nominal and serious crime, which type of it is being committed the most?
- [ ] Areas with highest probability of a serious crime being committed
- [ ] What’s the distribution of Age groups and nature of the crime 
- [ ] Probability of committing a serious crime in terms of Age groups

ARIMA and SARIMA Implementation:
1. ARIMA to Implement prediction model to check
    1. Age
    2. Descent
    3. Sex
2. SARIMA
    1. Age
    2. Descent
    3. Sex
Final part will be adding in an article to wind up the entire project. 
This should be done by this weekend. 

1. Need to create a data frame will all the data points and outliers removed.
2. Create grouped data frames for each particular case
3. The graphs and probabilities need to be calculated based on these grouped data frames
Data frames already present in the code
1. df
2. Df_time
3. Df_report
4. Df1
5. df_main
6. Df_desc
Df_report has been normalised and categorical values have been one-hot coded
I am create another main Df with all the information, outliers removed, and categorical values intact. The name of the data frame is df_main
Df_desc is the grouped version of df_main.

Wide format and long format of data frame
Long format helps with creating graphs and better control over the flow of the graphs 
Wide format is better for data analysis

Need to use merge (joins) to create multiple views and get proper information from the tables
Table Columns:
1. Year
2. Crime Level
3. Reported Cases
4. Total number of cases for each of them
5. Probability
6. Average 

I have made some changes to the main df, I have removed all the values with no vict age. This will help us remove the skew from the data.

So I have a general idea of how I want to spread the charts and tables
1. The Reporting delay and probabilistic analysis is done
2. The charts need automation and can be done using ipywidgets
3. Using Dash for better tabular representation of data
4. Area-wise data is charted out
5. Now arima representation
