## CYCLISTIC-BIKE-SHARE-GOOGLE-DATA-ANALYTICS-PROJECT
<img src="https://github.com/aubin560/Cyclistic-bike-share-Google-Data-Analytics-Project/blob/main/Divvy_Pricing_SingleRide_1200x960.jpg" alt="Cyclistic" style="width:80%;height:20%" >

## SCENARIO

You are a junior data analyst working in the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## BUSINESS TASK

The finance analysts have concluded that annual members are much more profitable than casual riders. The marketing department believes that the company future success depends on maximizing the number of annual members rather than creating campaign that targets all new customers. Cyclistic marketing analytics team has the responsibility of understanding how do annual members and casual riders use Cyclistic bikes differently. From these insights, Cyclistic marketing analytics team will design a new marketing strategy to convert casual riders into annual members. 

## DESCRIPTION OF DATA SOURCE

I downloaded data from this <a href="https://drive.google.com/drive/folders/1upc0vzD-xtbLi8l91PjZOR0Ui9FQktiJ?usp=sharing">link</a> and stored it in my computer hard drive. I will use this data to explore how different customers types are using the Cyclistic bikes from July 2021 to June 2022. The data has been made available by Motivate internal Inc. under this <a href="https://ride.divvybikes.com/data-license-agreement">license</a>. The data include the following column headers: ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name. end_station_id, start_lat, start_lng, end_lat, end_lng, and member_casual. Below is a description of each column header and sample values.

<table>
  <tr>
    <th>Column name</th>
    <th>Column description</th>
    <th>Sample data</th>
  </tr>
  <tr>
    <td>Ride_id	Unique</td>
    <td>identifier of customers</td>
    <td>B8BA05857944F445</td>
  </tr>
  <tr>
    <td>Rideable_type</td>
    <td>The type of bikes ridden by customers</td>
    <td>electric_bike</td>
  </tr>
    <tr>
    <td>Started_at</td>
    <td>Date and time each customer start a ride</td>
    <td>7/1/21 0:00</td>
  </tr>
  <tr>
    <td>Ended_at</td>
    <td>Date and time each customer end a ride</td>
    <td>7/1/21 0:04</td>
  </tr>
  <tr>
    <td>Start_station_name</td>
    <td>The location at which the ride started</td>
    <td>Bissell St & Armitage Ave</td>
  </tr>
  <tr>
    <td>Start_station_id</td>
    <td>The identifier of the location at which the ride started</td>
    <td>TA1309000035</td>
  </tr>
  <tr>
    <td>End_station_name</td>
    <td>The location at which the ride ended</td>
    <td>Broadway & Thorndale Ave</td>
  </tr>
  <tr>
    <td>End_station_id</td>
    <td>The identifier of the location at which the ride ended</td>
    <td>TA1307000064</td>
  </tr>  
  <tr>
    <td>End_station_id</td>
    <td>The identifier of the location at which the ride ended</td>
    <td>TA1307000064</td>
  </tr>
  <tr>
    <td>Geographic</td>
    <td>position</td>
    <td>41.918440000</td>
  </tr>
  <tr>
    <td>Start_lng</td>
    <td>Geographic position</td>
    <td>-87.652220000</td>
  </tr>
  <tr>
    <td>End_lng</td>
    <td>Geographic position</td>
    <td>-87.658617000</td>
  </tr>
  <tr>
    <td>Member_casual</td>
    <td>This column has two values: Member for annual membership and casual for casual riders.</td>
    <td>casual</td>
  </tr>
  </table>				

## DATA CLEANING DOCUMENTATION AND MANIPULATIONS

I used spreadsheet to clean data

Data cleaning verification checklist

<table>
  <tr>
    <th>COMMON PROBLEMS</th>
    <th>TOOL USED</th>
    <th>OBSERVATION</th>
  </tr>
  <tr>
    <td> Null data </td>
    <td> Conditional formatting and filter </td>
    <td> I found missing values in columns: start_station_name, start_station_id, end_station_name and end_station_id but I did not remove them because they represent a large part of the data </td>
  </tr>
  <tr>
    <td> Misspelled words </td>
    <td> Filter </td>
    <td> I filtered the rideable_type column to check if the rideable types are well spelled. We have only three types that are: electric_bike, classic_bike and docked_bike.
        I filtered the member_casual column to check if we only have two membership type that are member and casual </td>
  </tr>
  <tr>
    <td> Mistyped numbers </td>
    <td> Sort and filter </td>
    <td> In the ride_id column most of ids have 16 characters. I removed all ids without 16 characters. 
         In the ride_length new created column I removed all dates and times that are negative. </td>
  </tr>
  <tr>
    <td> Mistyped numbers </td>
    <td> Sort and filter </td>
    <td> In the ride_id column most of ids have 16 characters. I removed all ids without 16 characters. 
         In the ride_length new created column I removed all dates and times that are negative. Impacts on the number of rows in tables were as followed: 
	    Total deleted rows: 4638 
	    In accordance with the rules found at https://www.divvybikes.com/system-data we have to remove all trips or rides less than 60 seconds in length. Trips less than 60 seconds in length are potentially false starts or users trying to re-dock a bike to ensure it was secure. Impacts on the number of rows in tables were as followed: The Total number of rows deleted 99508 (1.6% of the total rows 5895758) </td>
 </tr>
  <tr>
    <td> Extra spaces and characters </td>
    <td> Trim function </td>
    <td> I removed extra spaces in all the dataset </td>
  </tr>
<tr>
    <td> Duplicates </td>
    <td> Remove duplicate function </td>
    <td> I found no duplicated data </td>
 </tr>
<tr>
    <td> Mismatched data types </td>
    <td>------</td>
    <td> I corrected data types </td>
</tr>
<tr>
    <td> Messy(inconsistent) string </td>
    <td>------</td>
    <td> No inconsistent string </td>
</tr>

<tr>
    <td> Messy (inconsistent) data formats </td>
    <td>------</td>
    <td> Inconsistent data format in the start_station_id and end_station_id </td>
  </tr>

<tr>
    <td> Misleading variable labels (columns) </td>
    <td> ------ </td>
    <td> I combined “started at” and “ended at” column into “route” with a to as separator. 
I changed “member_casual” into customer_type </td>
</tr>
<tr>
    <td> Business Logic </td>
    <td> ------ </td>
    <td> My data make sense to answer the business question. </td>
  </tr>
  </table>


#### Data manipulation

I concatenated the column start_station_name and the end_station_name to make one column called route. With “to” as separator. After concatenation, the cells with only “to” in the route column were replaced by no_given_route. In the route column cells that start with “to” indicates data points with no start_station_name and with “to” at the end indicate data points with no end_station_name. 


Manipulation of data to create new columns that are important to answer questions.
We are going to answer the question: How do annual members and casual riders use cyclistic bikes differently?
We want to discover information about the ride_length of members and casual riders and we also want to know how the members and casual riders use cyclistic bikes in the days of the week and in months of the year


Organizing data into metrics 
Ride_length = ended_at – started_at 
I put the ride_length column in the hh:mm: ss format. Then I use the INT(number*1440) to change the date format into minutes in the number format so that I will be able to make the average of the ride_length column.


Creation of the new column called day_of_week: to get this column we applied the function WEEKDAY () on the started_at column. Then with the “Find and replace” tool I replaced days of the week that were given in number into text. Example: 2 for Monday and 6 for Friday. 


Creation of another column called month_of_year: to get this column we applied the function TEXT (array,” mmmm”), the array is nothing else than the started_at column. 

## SUMMARY OF THE ANALYSIS

I used SQL bigqueries for my analysis

Reminder of the Business Task: Understand how do annual member and casual riders use the Cyclistic bike differently?
In order to understand this question just above we need to discover information about these questions:

- What is the total number of rides by customer type?
- What is the monthly average ride length by customer type?
- What is the average ride length by customers on the days of a week?

Before answering these questions, I passed through some steps:

Step 1: Data importation 

I had 12 big files (the twelve files refer to the twelve months) to upload on Bigquery some files were higher than 100MB while I can’t upload a file from the local server that is higher than 100MB so I decided to divide each file into two subfiles and then joining them together once uploaded in the Bigquery with the joins statement. 

After uploading the data, I had two datasets with 12 tables each. I named the two datasets: tripdata and tripdata_geo (geo for geographic information) 
Before using the join statement. I first union all the months into a single year for both datasets
For the Tripdata dataset: 
~~~~sql
SELECT * FROM `revision-359107.tripdata.202107-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202108-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202109-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202110-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202111-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202112-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202201-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202202-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202203-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202204-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202205-divvy-tripdata` 
UNION ALL 
SELECT * FROM `revision-359107.tripdata.202206-divvy-tripdata` 

~~~~


		
		
		










