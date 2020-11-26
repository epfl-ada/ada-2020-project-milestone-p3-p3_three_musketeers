1. Title: Police retaliation against racial injustice protests


2. Abstract:
Civil rights movements have protested for decades against police brutality and racial bias of law enforcement towards black people. 
Racial injustice protests have regularly sparked reactions from government officials and have been greatly referred to in the media. 
However, it is unclear how police officers reacted to racial justice protests. Given that those protests are often directed against 
the police as such, it is reasonable to think that they might feel attacked. If police officers feel criticised and attacked by such 
protest they might want to retaliate and in the case of traffic stops, they might increase stops and searches of minorities. On the 
other hand they might also try to correct their racial bias given the clearly voiced criticism. We found a data set which documents 
racial injustice protest in the USA since the year 2017. In our project we would like to connect the data on police traffic stops 
(Pierson et al., 2020) with information about racial injustice protests.  With this integrated dataset we would like to estimate if 
and which effects protests have on the stop and search decisions of police officers. 


3. Research questions
  1) Do racial injustice protests have an effect on the racial bias of police in traffic stops?
  2) If so, can the magnitude of this correlation be estimated? 


4. Proposed dataset
  1) Protest data set “Count Love”: https://countlove.org/faq.html
     This data set is a collection of different types of protests that took place in the USA from 2017 to 2020 and it has been used as
     a point of reference in several projects (to name a few: New York Times, Bloomberg, ACLED data project, Boston University Research).
     It consists of 37090 protest events and each protest has information about 8 features (Date, Location, Attendees, Event, Tags, Curated,
     Source, Total Articles). A first look into the data reveals that in 1.7% of protests participated more than 1000 attendees in “Racial 
     Injustice” related protests. Moreover, 2.94% of records include protests with more than 1000 attendees in 2017 and 2018. Finally, the 
     maximum number of attendees in a racial injustice protest is 300000 in 2017 and also, we have observed that the data includes protests
     with an unknown number of attendees. The aforementioned statistics provide evidence that we can merge the protest data set on columns 
     “Date {2017, 2018}” and “Location” with the dataset of traffic stops provided by the original paper and focus on a small set of large 
     racial injustice protests.
     
2) Police stops data set: https://openpolicing.stanford.edu/data/
   This dataset is provided by the original paper “A large-scale analysis of racial disparities in police stops across the United States”
   by E. Pierson et al. (2020). We will use the processed, but not aggregated, version that we know is well documented and cleaned. 
   Furthermore, we will draw our attention in traffic stop records that occurred from 2017 to 2018 in order to merge them with the “Count
   Love” data set.

5. Methods

In order to assess the effects of racial injustice protests on traffic stop rates, we will, first, create the same visualization of the 
replication that was presented out for marijuana legalization. Subsequently, we will proceed onto a more tailored method. Before both steps,
some data wrangling will be needed.

Data wrangling: As mentioned above, we will adopt the non-aggregated datasets of Stanford’s open policing and the count love dataset with
protest data. Currently, the idea would be to aggregate the stanford data by day and merge it with the protest dataset by coupling a 
certain day of police stop information with the protest that is closest in time and with matching place. We would also include a column
with information about elapsed time from/to the protest. We will filter out the Hispanic race as it is not heavily concerned with our analysis.
Reasonably, much more data wrangling will become necessary.

Pre-Post Plot: For a few very big protests we want to depict the pre- post- difference in stop rates given the race of the driver as in 
the replication. Since we believe that there might be more black people in the streets the day of the protest, we will exclude the day 
of the protest (or even one day before and one day after) from our visualization and only plot the week (or two weeks) before and after
the protest. 

Linear-Regression: To estimate a (non-causal) effect of protests on traffic stop decisions we plan to use a linear regression model,
where we regress the number of attendees of a protest and the elapsed time from/to the protest and other covariates onto the search 
rates in the following week (or other time frame)

6. Proposed timeline

Week 1 Data wrangling: Select three most prominent protests. Download dataframes and do necessary merges. Aggregate data by day and 
week and match the two data sources.
Week 2 Data visualization and analysis: Recreate replication visualization with new data. Analyse results. Begin the regression.
Week 3 Data modeling: Finish regression and analysis. Make a short video, clean code and add textual descriptions (i.e. data story).
