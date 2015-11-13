# Roscommon Calendar of Events 2015 API
## Data Representation and Querying Project 2015
### John Malcolm Anderson

## Introduction
This project provides the design and documentation for the dataset Roscommon Calendar of Events 2015 which is available at [data.gov.ie](http://roscommon.roscoco.opendata.arcgis.com/datasets/fbae9c86e6e1441bbea951893744f3bc_0). The main purpose of the API is to share events that are happening in Roscommon to various media outlets and any interested parties via a simple RESTfull API. The secondary usage is an ability for trusted event organisers and media outlets to post, update & delete events via the API. Authentication for trusted users is handled with OAuth 1.0.  

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from Roscommon County Council Open Data Portal (http://roscommon.roscoco.opendata.arcgis.com/datasets/fbae9c86e6e1441bbea951893744f3bc_0).
The CSV file contains 73 rows, the first being a header row with the names of each field. 

There are 21 values on each line, which are as follows:
- **x**: the year that the car was purchased.
- **y**: the price of the car.
- **Event_ID**: The Unique Identifier for the event.
- **Month**: The month that the event takes place.
- **Event_Date**: The date of the event.
- **Event_Name**: The name of the event.
- **Day**: The day(s) the event takes place.
- **Type**: The type of Event.
- **Time**: The time(s) the event takes place.
- **Image_url**: The URL for the event.
- **Address**: The address for the event.
- **Lat**: The Latitude of the event location.
- **Long**: The Longtitude of the event location.


