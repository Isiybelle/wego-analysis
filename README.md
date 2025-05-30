# WeGo Public Transit Analysis
[WeGo Public Transit](https://www.wegotransit.com/) is a public transit system serving the Greater Nashville and Davidson County area. WeGo provides local and regional bus routes, the WeGo Star train service connecting Lebanon to downtown Nashville, along with several other transit services.

The data for this project can be downloaded from [here](https://drive.google.com/file/d/1iM4WjC9k3EXHPNc6q4AwDh_MEIpXvfMD/view?usp=sharing).

In this project, you'll be analyzing the on-time performance of buses to look for patterns and try to identify correlations to controllable or external factors. 

The main variable you will be studying in this project is **adherence**, which compares the actual departure time to the scheduled time and is included in the ADHERENCE column. A negative adherence value means that a bus left a time point late and a positive adherence indicates that the bus left the time point early. Buses with adherence values beyond negative 6 are generally considered late and beyond positive 1 are considered early. However, there is some additional logic where the staff applies waivers to allow early departures, such as an express bus that has already picked up everyone at a park-and-ride lot and is only dropping people off at the remaining stops, and also allows for early timepoint records for all records where TRIP_EDGE = 2 (end of trip), since it is not a problem if a bus ends its trip early as long as it didn't pass other timepoints early along the way. **Note:** When determining whether a bus is early or late, it is advised that you use the 'ADJUSTED_EARLY_COUNT', 'ADJUSTED_LATE_COUNT', and 'ADJUSTED_ONTIME_COUNT' columns in order to account for the adjustments.

Goals of these questions:
1. What is the overall on-time performance, and what do the overall distribution of adherence look like? 
2. How does direction of travel, route, or location affect the on-time performance?
3. How does time of day or day of week affect on-time performance?
4. How much of a factor does the driver have on on-time performance? The driver is indicated by the OPERATOR variable.
5. Is there any relationship between lateness (ADHERENCE) and headway deviation? The headway deviation variable is contained in the HDWY_DEV column. See the notes under number 9 for a description of headway and headway deviation.

**Stretch Questions:**  

6. How much impact does being late or too spaced out at the first stop have downstream?  
7. What is the impact of the layover at the start of the trip (the difference between the first stop arrival and departure time)? Does more dwell time at the beginning of a trip lead to more stable headways (lower values for % headway deviation)? Do trips with longer **scheduled** layover time have more stable headway values?  
8. What is the relationship between distance or time traveled since the start of a given trip and the adherence value? Does on-time performance become less stable the further along the route the bus has traveled?

9. **Headway** is the amount of time between a bus and the prior bus at the same stop. In the dataset, the amount of headway scheduled is contained in the SCHEDULED_HDWY column and indicates the difference between the scheduled time for a particular stop and the scheduled time for the previous bus on that same stop.
This dataset contains a column HDWY_DEV, which shows the amount of deviation from the scheduled headway. **Bunching** occurs when there is shorter headway than scheduled, which would appear as a negative HDWY_DEV value. **Gapping** is when there is more headway than scheduled and appears as a positive value in the HDWY_DEV column. Note that you can calculate headway deviation percentage as HDWY_DEV/SCHEDULED_HDWY. The generally accepted range of headway deviation is 50% to 150% of the scheduled headway, so if scheduled headway is 10 minutes, a headway deviation of up to 5 minutes would be acceptable (but not ideal).
How do the variables studied related to headway deviation? 




# Mulligang WeGo Presentation

Team analysis of WeGo Public Transit data diving into operator and route efficiency. Our team worked together to determine how off shcedule buses seemed to be running and factors that could influence such. We compared the dataset's most experienced operators to determine on-time percentages, and observed separate stops per trip per route to find the least troublesome stops and the most consistnetly behind stops. This data was observed in a folium map to better showcase route adherence times and stats. 

**The Experiment**

At the end, we decided to run a 'randomizer race' to see if we could manipulate probability to determine what operaters would 'win' on certain routes. We looked at routes 56 and 55 to be our 'race tracks' and used teh data's five most experienced operators as our 'racers'. After running the races several time, we came to interesting insights about on-time percentage, probability, and where high performing operators and lower performing operators would be best suited.
