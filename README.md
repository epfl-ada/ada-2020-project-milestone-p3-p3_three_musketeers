### 1. Title: Does the police retaliate against  in reaction to racial injustice protests?


### 2. Abstract:
Civil rights movements have protested for decades against police brutality and racial bias of law enforcement towards black people. 
Racial injustice protests have regularly sparked reactions from government officials and have been greatly referred to in the media. 
However, it is unclear how police officers reacted to racial justice protests. Given that those protests are often directed against 
the police as such, it is reasonable to think that they might feel attacked. If police officers feel criticised and attacked by such 
protest they might want to retaliate and in the case of traffic stops, they might increase stops and searches of minorities. On the 
other hand, they might also try to correct their racial bias given the clearly voiced criticism. We found a dataset which documents 
racial injustice protest in the USA since the year 2017. In our project we would like to connect the data on police traffic stops 
(Pierson et al., 2020) with information about racial injustice protests.  With this integrated dataset we would like to estimate if 
and which effects protests have on the stop and search decisions of police officers, in so doing, we would like to extend the 
racial bias analysis to the specific case of protests.


### 3. Research questions
 1) Is there a relationship between the occurence of a racial injustice protest and the number of attendees of the latter with the racial bias in police traffic stops following the given protest?




### 4. Proposed dataset
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
   
3) We use as a second source, a collection of 780 protests organized by the “Black Lives Movement” (Trump et al., 2018) between 2014 and 2015.
   In addition to protest-specific features, this collection also includes census information. 

### 5. Methods

In order to assess the effects of racial injustice protests on traffic stop rates, we will, first, create the same visualization of the 
replication that was presented for marijuana legalization. Subsequently, we will proceed onto a more tailored method. Before both steps,
some data wrangling will be needed.

**Data wrangling**: As mentioned above, we will adopt the non-aggregated datasets of Stanford’s open policing and the count love dataset with
protest data. Currently, the idea would be to aggregate the Stanford data by day and merge it with the protest dataset by coupling a 
certain day of police stop information with the protest that is closest in time and with matching place. We would also include a column
with information about elapsed time from/to the protest. We will filter out the Hispanic race as it is not heavily concerned with our analysis.
Reasonably, much more data wrangling will become necessary.

**Pre-Post Plot**: For a few very big protests we want to depict the pre- post- difference in stop rates given the race of the driver as in 
the replication. Since we believe that there might be more black people in the streets the day of the protest, we will exclude the day 
of the protest (or even one day before and one day after) from our visualization and only plot the week (or two weeks) before and after
the protest. 

**Linear-Regression**: To estimate a (non-causal) effect of protests on traffic stop decisions we plan to use a linear regression model,
where we regress the number of attendees of a protest and the elapsed time from/to the protest and other covariates onto the search 
rates in the following week (or other time frame). An analysis will be carried out on the resulting model.

### 6. Proposed timeline

Week 1 Data wrangling: Download data sets, filter columns, join data sets based on date and location, aggregate data by day and week, select three most prominent/largest protests.  

Week 2 Data visualization, analysis and modeling: Replicate the visualization of figure 4 for top three protests, analyse results, change protests and repeat some of week 1 tasks if the result is not sufficient. If everything is working well then we start the regression in order to estimate the magnitude of the bias according to the coefficients.

Week 3 Final details and submission: Finish data analysis and modeling, clear code cells, add textual descriptions (i.e. data story), make a short video, submit GitHub repository.

### 7. Organization within the team

Individual responsibilities: Each one is responsible to clean code cells and add textual descriptions of personal tasks. 

Collective responsibilities: We solve critical problems together, if any arise, and we redefine our strategy based on the research questions we wish to answer, we create the short video together.

Aurel Mader: match three data sources, build and analyse regression, write abstract, introduction, literature review, methods and conclusion of report.

Ludovica Schaerf: aggregate dataframes for plotting, make and analyse visualization, regression experiments and results in report.

Theodoros Bitsakis: data wrangling and descriptive statistics for Count Love data set, dataset merging based on date/location, select top three protests, dataset description in reoprt.

### 8. Questions for TAs (optional)

1. Our data set is from a webpage, we tried to assess the trustworthiness of our dataset given prior use in other projects and concluded that it seems trustworthy. Do you agree?

2. We very much worry about causality. Till now we couldn’t think about a feasible method to assert causality and all our methods could only show simple correlations. Do you have any proposals regarding causality or is our method sufficient? 
