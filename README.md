# UltimateChallenge
Ultimate Interview Challenge

PART 1: Exploratory Data Analysis

From the plot (right), we can see that Saturday and Sunday have a similar shape over the course of a day (24-hours) on average. Weekends logins show a peak around 4 AM, perhaps related to the end of nightlife, when users may need a safe ride home. On weekdays, there are 2 login peaks, one around 11 AM and the other around 10 PM (22:00). Average weekend logins are higher than average weekday logins from the start of the day until 6 AM (00:00-06:00). 


PART 2: Experiment and Metrics Design

Q1: What would you choose as the key measure of success of this experiment in encouraging driver partners to serve both cities, and why would you choose this metric?
A1: I'd choose the daily average number of bridge crossings for partner drivers during an active session as the key success metric for this experiment. I'd choose this metric since we could easily compare the pre-experimental data with the experimental data and if there is a significant difference, we could assert that the toll-reimbursement program was successful. We can assume that Ultimate desires a local increase in driver availability resulting in decreased wait times and increased customer satisfaction.

Q2: Describe a practical experiment you would design to compare the effectiveness of the proposed change in relation to the key measure of success.
A2: Assuming that we have trip location data for past trips, we can use the previous daily averages of bridge crossing data as our baseline metric. Our hypothesis is that Toll-Free bridge crossings will increase the daily average number of bridge crossings for active Ultimate drivers. 

a. To implement the experiment, we could offer the toll-reimbursement program to a random sample of all active Ultimate drivers in the 2 cities. Perhaps the sample represents 20% of all active drivers. We would record each individual driver's average number of bridge crossings per day in the previous 30 days. It is quite possible that the average number of bridge crossings per active driver is less than one or zero. We could run the experimental offer for 30 days and record the average daily bridge crossings for our sample group. If there is a statistically significant increase in the number of bridge crossings, we could conduct a similar experiment with a larger subset of the active driver population for greater confidence. 

Hypothesis: "Toll-Free" bridge crossings will increase the daily average number of bridge crossings for active Ultimate drivers.

NULL Hypothesis: "Toll-Free" bridge crossings will have no effect on the daily average number of bridge crossings for active Ultimate drivers.



b. We would use a one-tail T-test to verify the significance of the observation. A significant T-value would indicate that the hypothesis may be valid and could merit further experimentation with a larger subset.

Recommendations:
1. If the hypothesis is verified with statistical significance, we would recommend running the experiment with a larger subset.
2. We would recommend scaling up the experiment to the full population slowly.
3. The program should be scaled with the caveat that it is temporary and only available on a trial-basis.
4. The program's success metric should be constantly observed and assessed to ensure to verify on-going success of the program.

Caveats:
1. The solution may not scale up well as there may be other variables when the entire local active driver population is given the toll-free offer such as competition and saturation.
2. The experiment does require more experimentation on a larger cohort to determine if there is a point of diminishing returns given the unique dynamics of the local market.
3. A detailed cost-benefit analysis should be conducted to determine if the program is practical when implemented at scale.  


PART 3: Predictive Modeling

A. User Retention: What fraction of the observed users were retained?
There is 41.1% user retention. 17,035/41,445 are retained users from the cleaned dataset.

B. Discuss why you chose your approach, what alternatives you considered, and any concerns you have. How valid is your model? Include any key indicators of model performance.

We experimented with five (5) different machine learning classification models to determine which features are the most important. We eventually chose XGB Classifier as it had the highest accuracy (77.54%). We focused on accuracy as our primary performance metric.

The models we explored in descending order of accuracy are: XGBClassifier - 77.53%, RandomForestClassifier - 74.84%, KNeighborsClassifier - 72.83%, LogisticRegression - 70.35%, LinearSVC - 70.26%.





C. Briefly discuss how Ultimate might leverage the insights gained from the model to improve its long-term rider retention.

Ultimate can leverage insights of this work by performing cost-benefit analysis on the 'important' variables which Ultimate can control. For example, the most 'important' feature in the analysis is the user being registered to the city 'King's Landing', so the natural intuition would be to emphasize the companies' strengths and increase geo-specific targeted marketing to that area. Marketing could consider running a geo-specific promotion for "Ride Like A King'' with an immediate discount on the first ride for a new sign-up in King's Landing.

The second most important feature in our analysis is 'avg_rating_by_driver' which is something that may not be directly actionable, as driver rating of a passenger is a complex function of many other qualitative variables and the company may value the subjectivity of this metric. However, that may be worth surveying some driver-partners to analyze how they think about these ratings.

The third most important feature to predict user retention is Android Phone usage. I'd recommend that marketing could consider targeted ads towards attracting more Android Phone users to Ultimate. Perhaps offer an Android only incentive with an A/B test.




Feature Importance

