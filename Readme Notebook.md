
# Lyft Bay Wheels (fka Ford Go Bike) Data Visualization Project
## by Jerry Yip


## Dataset

> The [Lyft Bay Wheels System Data](https://www.lyft.com/bikes/bay-wheels/system-data) dataset (formerly known as 'Ford GoBike' dataset) comprises Lyft's Bay Area bike sharing data made available to the public by Lyft and previously Ford (the bike share system's prior operator).  The public data set spans 2017 to present day (Sep 2019), however I focused my analysis on data for 2018 and 2019 while excluding 2017 data for several key reasons, including:
* the 2017 data does not include date or timestamps of bike rides
* the 2017 data is not as recent and may include outdated details  

>For the 2018 and 2019 dataset, data is published by Lyft in separate files divided by calendar month, for which I combined the data into a single dataframe named 'bike_clean' for better analysis. 
> Upon consolidation, my combined dataframe covers 3,736,961 bike rentals comprising 3,736,961 rows and 29 attributes (columns).  The dataset covers bike rentals servicing the following 3 service areas in the bay area:  
* San Francisco
* East Bay
* San Jose  
### Further Dataset Details
>The original Lyft published dataset included the following 16 attributes (columns):
* duration_sec
* start_time
* end_time
* start_station_id
* start_station_name
* start_station_latitude
* start_station_longitude
* end_station_id
* end_station_name
* end_station_latitude
* end_station_longitude
* bike_id
* user_type
* member_birth_year
* member_gender
* bike_share_for_all_trip  

> The dataset was further enhanced by me to include the following additional derived attributes:  
* ride_dist (approx ride distance assuming a straight line)
* ride_dist_est (approx ride distance accounting for traffic detours)
* duration_min (duration of rental in minutes)
* ride_year (year of rental)
* ride_month (month of rental)
* start_day (day of the week for start of rental)
* end_day (day of the week for end of rental
* start_hour (hour of the day for start of rental)
* end_hour (hour of the day for end of rental)
* member_age (approximate age of renter)
* age_group (age group of customer)
* start_srv_area (start service area)
* end_srv_area (end service area)  

> In addition to consolidating the data to a single dataframe and adding the above attributes, there were a few other data wrangling steps I performed to assist with data analysis efforts.  These steps included:  
* cleaning up inconsistencies in data representation(abbreviations vs non-abbreviations)
* correcting data types (converting timestamps captured as string datatypes to datetime datatypes) etc
* setting certain columns to categorical datatypes with nominal ordering (e.g. age_group etc.)
* converting missing values to null or appropriate 'other' values
* dropping the column 'rental_access_method' which was only available for the months of June and July 2019
* re-ordering the columns to put the most useful columns towards the left side of the dataframe
* to account for the fact that the distance between rental stations is not a straight line, multiplying the straight line distance between stations by a 'detour index' of 1.417 in order to calculate an approximate ride distance as per the column 'ride_dist_est' -- see the following [national study](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3835347/) for more details


## Summary of Findings

> In terms of bike rental distribution, the most rentals occur on weekdays with a bimodal distribution of daily rental start times with 2 peak concentrations during morning and evening commute hours of 7-9am and 4-7pm.  Also as expected, ridership increases during the warmer spring-fall months.  
Looking across demographics, the highest usage is by middle aged riders  with 25-34 year olds representing the largest group (43.4%) and 35-44 year olds representing the next largest group (22%) -- this further reinforces earlier findings of heavy usage of the bike share system for work commutes by working age riders.  
Across genders, we find that males vastly outnumber female riders as far as the number of bike rentals by a factor of 3x1 with riders who identified their genders as male comprising ~68% of rentals whereas only ~22% of rentals were by women.  
In the exploration I found, as would be expected, a strong positive correlation between the rental duration and the estimated ride distance.  Overall, the average bike rental duration is 13.84 minutes long and an estimated 1.44 miles in distance.  Whereas bike rental duration and estimate ride distance does not vary greatly by age and gender, the rental duration does vary dramatically between subscribers and non-subscribing customers -- subscribers on average ride for ~11 minutes, but non-subscribing customers ride on average 28 minutes.  It appears subscribers do not bother with maximizing each rental as they get an unlimited number of rides up to 45 minutes, whereas non-subscribers attempt to use all of their allotted 30 minutes of time -- it appears price does influence riding habits.  
Over time, ridership has increased with year over year ridership increasing every month since January 2018 except for the month of June 2019 which coincides with two recalls of Lyft's electric bikes as detailed in the following [article](https://www.theverge.com/2019/7/31/20749396/lyft-electric-bikes-pulled-san-francisco-battery-fires-motivate-bay-wheels).  
Lastly, as a curious sidebar, I observed an interesting trend regarding late night rentals to what appears to be largely Friday night and weekend male party-goers. Despite comprising only a small percentage of total ridership (~1.3% of all rides), this trend does appear to be growing over time.  Hence, it may be worth exploring this trend more as a possible safety concern and conversely an opportunity to direct such riders to instead use Lyft's ride sharing programs (aka Lyft's taxi and carpool service). On the other hand, perhaps it is further evidence that Lyft's strategy to expand operations in all modes of transportation is a good move -- by providing customers more alternatives such as bike rentals during these weekend late nights that are often 'peak' or 'surge' pricing hours for car and carpool ride sharing, perhaps Lyft is capturing more revenue from those customers who previously would otherwise simply walk versus requesting an expensive Lyft car (assuming they are riding safely and sober that is).

## Key Insights for Presentation

> For the presentation, I focus on growth opportunities for Lyft's operation of the Bay Wheels bike sharing system. With the assumption that Lyft's goal is to grow bike ridership, I review the current breakdown of bike rentals before expanding on opportunities to increase ridership among certain lesser served groups including female riders and one-off or occasional users (comprising non-subscribing 'customer' user types).  
Beyond demographics and personas, I analyze these growth opportunities in the context of the latest 2019 ridership trends, Lyft's recent transition of the bike sharing system from Ford, and coinciding impacts of Lyft's recent recalls of electric bikes.  Lastly, I look at the revenue implications of the aforementioned trends from the lens of bike share pricing versus average rental durations over time.




```python

```
