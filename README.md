BellaBeats Analysis Documentation and Insights
Ask
The goal is to analyze smart device usage data from fitabase  in order to gain insight into how people are already using their smart devices. Then, using this information to give high-level recommendations for how these trends can inform Bellabeat marketing strategy.

Prepare
The data is downloaded from the https://www.kaggle.com/datasets/arashnic/fitbit in two sets. 3.12.16 to 4.11.16 and 4.12.16 to 5.12.16 as a zip file. Then extracted as a csv file from the zipped folder. Data is presented according to the activity recorded. 
R - Reliable:
	The data contains different all activities recorded by the smart devices
O - Original
	The data is original. Collected from the fitabase app.
C - Comprehensive
	The dataset isn’t complete but cleaned to remove incomplete data, leaving a comprehensive dataset.
C - Current
	The dataset isn’t current, but covers more than 4 weeks to notice trends.
C - Cited
	The source of the data is identified and cited for reference.
Process
The data analysis tool used is Microsoft PowerBI. This is chosen because of its ability to work with large datasets and easier to use transformation tools.

Each of the csv file is loaded into powerbi.
A relationship is created between all table by joining the dailyActivity_merged table to other tables using the ID as the common connector in a many-to-many relationship.
Activity day name and Activitydayofweek column is created in dailyactivity_merged table.
A Datetable Calendar is created to analyze data by weekday. 
DateTable = CALENDAR(MIN(hourlySteps_merged[ActivityHour]), MAX(hourlySteps_merged[ActivityHour]))
A timeperiod is created for morning, afternoon, evening, night and midnight in heartrate_seconds_merged table.
Morning: 6:00 AM – 11:59 AM
Afternoon: 12:00 PM – 4:59 PM
Evening: 5:00 PM – 8:59 PM
Night: 9:00 PM – 11:59 PM
Midnight: 12:00 AM – 2:59 AM
A measure is created in hourlyCalories_merged and hourlySteps_merged table to get the percentage change in calories and steps day to day. 
Calories2 Percentage Change = 
DIVIDE(([Total Daily Calories2] - [Previous Day Calories2]), [Previous Day Calories2], 0)


Analyze
Goal: Analyze how people are using their smart devices.
Calculated the distinct count of people using each of the available feature. Sedentary, steps, heartrate, calorie, and weight.
Analyze the percentage change in values for steps counted by weekdays.
Compare average calories by distance traveled. (light and medium)
Compare sum of distant traveled by activityday name.
Compare sum of steps total by period of the day.
Share
https://drive.google.com/drive/folders/1FsI0kRmygjU2ptFhmc6P7it-XTLK3u1t?usp=drive_link

Act
The following are the recommendations based on the insights from the analysis
Feature Usage Insights: Analysis reveals that the sedentary, heart rate, and step counter features are the most popular among users. These should be the primary focus in marketing efforts to maximize user engagement and product appeal.
Peak Days for Steps Counter Usage: Data shows that Wednesdays and Fridays have the highest activity for the steps counting feature. To capitalize on this trend, the marketing team could organize promotional events, such as fitness challenges or visits to high-traffic exercise centers, on these days to drive brand visibility and product adoption.
Correlation Between Steps and Heart Rate: A strong correlation exists between the steps taken and heart rate, indicating that an increase in steps also results in an elevated heart rate. This suggests that users who monitor their steps are also keen to track their heart rate.
However, a unique pattern emerges at night:
Steps drop to nearly zero due to inactivity.
Heart rate spikes, deviating from the usual trend.
This indicates significant user interest in heart rate monitoring while asleep, even when steps are not being tracked. This insight can be used to market Bellabeat as a convenient product for nighttime heart rate tracking, emphasizing its utility during sleep.
Calories Burned vs. Distance Traveled: Calories burned generally increase with distance traveled. Notably, light activity distance shows a higher calorie burn sensitivity compared to moderate activity distance. To support users focused on calorie-burning goals, a feature prompting light activity at regular intervals could be developed. This feature could specifically target users who have set calorie-burning as a priority, providing actionable nudges to achieve their fitness goals.

Google drive documents: https://drive.google.com/drive/folders/1FsI0kRmygjU2ptFhmc6P7it-XTLK3u1t?usp=sharing
