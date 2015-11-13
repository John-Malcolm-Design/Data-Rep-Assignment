# Roscommon Events 2015 API ![alt text](http://me.johnmalcolmdesign.com/RosLogo80.png "Logo Title Text 1")
## Data Representation and Querying Project 2015 
### John Malcolm Anderson 

## Introduction 
This project provides the design and documentation for the dataset Roscommon Calendar of Events 2015 which is available at [data.gov.ie](http://roscommon.roscoco.opendata.arcgis.com/datasets/fbae9c86e6e1441bbea951893744f3bc_0). 

The main purpose of this API is to share events that are happening in Roscommon to various media outlets and any interested parties via a simple RESTfull API. The secondary usage is an ability for trusted event organisers and media outlets to post, update & delete events. Authentication is handled with the highly trusted [OAuth 1.0 Protocol](http://tools.ietf.org/html/rfc5849).  

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [Roscommon County Council Open Data Portal] (http://roscommon.roscoco.opendata.arcgis.com/datasets/fbae9c86e6e1441bbea951893744f3bc_0).
The CSV file contains 73 rows, the first being a header row with the names of each field. 

There are 19 values on each line, which are as follows:
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

## Methods
Below is a list of API endpoints organised via the your typical operations on the data: Create, Read, Update and Delete. All methods besides those under the "Reading" heading require [authenticaton](link to authentication section).

### Creating
##### List all events

### Reading

### Updating

### Deleting


