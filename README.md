# Roscommon Events 2015 API ![alt text](http://me.johnmalcolmdesign.com/RosLogo80.png "Logo Title Text 1")
## Data Representation and Querying Project 2015 
### John Malcolm Anderson 

## Introduction 
This project provides the design and documentation for the dataset Roscommon Calendar of Events 2015 which is available at [data.gov.ie](http://roscommon.roscoco.opendata.arcgis.com/datasets/fbae9c86e6e1441bbea951893744f3bc_0). 

The main purpose of this API is to share events that are happening in Roscommon to various media outlets and any interested parties via a simple RESTfull API. The secondary usage is an ability for trusted event organisers and media outlets to post, update & delete events. Authentication is handled with the highly trusted [OAuth 1.0 Protocol](http://tools.ietf.org/html/rfc5849).  

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [Roscommon County Council Open Data Portal] (http://roscommon.roscoco.opendata.arcgis.com/datasets/fbae9c86e6e1441bbea951893744f3bc_0).
The CSV file contains 73 rows, the first being a header row with the names of each field. Due to increasing popularity and ease of use this API will return data in JSON format. 

There are 19 values for each event, which are all returned as **String** for API simplicity and due to the type of data contained. Most are self explanatory, see below for a full list values:
- **event_id***: The Unique Identifier for the event.
- **month***: The month that the event takes place.
- **event_date***: The date of the event.
- **event_name***: The name of the event.
- **day***: The day(s) the event takes place.
- **type***: The type of Event.
- **time**: The time(s) the event takes place. 
- **image_url***: The URL for the event.
- **address**: The address for the event. 
- **lat***: The Latitude of the event location. 
- **long***: The Longtitude of the event location. 
- **telephone***: The telephone number for the event.
- **email**: The email address for the event.
- **website**: The website for the event.
- **creation_date***: The date the event was originally posted.
- **creator***: The poster of the original event.
- **edit_date**: The date event was last edited.
- **editor**: The last editor of the event.

Asterix = required field all other fields may be null.

Fields auto-generated on the server = *event_id*,  *creation_date*, *creator*, *edit_date*, *editor*.

## Endpoints
Below is a list of API endpoints organised via the your typical operations on the data: Create, Read, Update and Delete. The format is: "HTTP Method: Endpoint URL". All methods besides those under the "Reading" heading require [authenticaton](link to authentication section).

### Get all events
**GET:** *http://www.roscommoncoco.ie/api/events/*.

**HTTP Response Example**
```http
HTTP/1.1 200 OK
[
  {
    "event_id": "1",
    "month ": "March",
    "event_date": "March 18th",
    "event_name": "Roscommon Womens Network Charity 5km Fun Run",
    "day": "Wednesday",
    "type": "Charity",
    [...]
  },
  [...]
]
```

[Example of JSON returned.](http://me.johnmalcolmdesign.com/roscommon_events_2015.json)


### Get specific event
**GET:** *http://www.roscommoncoco.ie/api/events/[event_id]*.

**HTTP Response Example**
```http
HTTP/1.1 200 OK
{
  "event_id": "1",
  "month ": "March",
  "event_date": "March 18th",
  "event_name": "Roscommon Womens Network Charity 5km Fun Run",
  "day": "Wednesday",
  "type": "Charity",
  [...]
}
```

### Create an event
**POST:** *http://www.roscommoncoco.ie/api/events/*.

**HTTP Request Example**
```http
POST /api/events/ HTTP/1.1
Host: roscommoncoco.ie
  {
    "month ": "March",
    "event_date": "March 18th",
    "event_name": "Roscommon Womens Network Charity 5km Fun Run",
    "day": "Wednesday",
    "type": "Charity",
    "address": "Roscommon",
    "lat": "53.627591",
    "long": "-8.189096",
    "telephone": "0949621690",
    [OAuthCredentials ... ]
  }

```

**HTTP Response Example**
```http
HTTP/1.1 201 Created
Host: roscommoncoco.ie
Content-Type: application/json; charset=utf-8
Content-Length: 19
  {
    "event_id": "1",
    "month ": "March",
    "event_date": "March 18th",
    "event_name": "Roscommon Womens Network Charity 5km Fun Run",
    "day": "Wednesday",
    "type": "Charity",
    [...]
    "creation_date": "2015-04-01T09:48:54.005Z",
    "creator": "RoscomCoCoGIS",
    "edit_date": "2015-04-01T10:15:53.670Z",
    "editor": ""
  }
```

### Update an event
**PATCH:** *http://www.roscommoncoco.ie/api/events/[event_id]*.

**HTTP Request Example**
```http
PATCH /api/events/43 HTTP/1.1
Host: roscommoncoco.ie
Content-Type: application/json; charset=utf-8
Content-Length: 19
{
  "event_date": "March 22th",
  "day": "Friday",
  "address": "Roscommon",
  "telephone": "0870642570",
  [OAuthCredentials ... ]
}

```

**HTTP Response Example**
```http
PATCH /api/events/43 HTTP/1.1
Host: roscommoncoco.ie
Content-Type: application/json; charset=utf-8
Content-Length: 19
{
  "event_id": "43",
  "month ": "March",
  "event_date": "March 21th",
  "event_name": "Roscommon Womens Network Charity 5km Fun Run",
  "day": "Friday",
  [...]
  "creation_date": "2015-04-01T09:48:54.005Z",
  "creator": "RoscomCoCoGIS",
  "edit_date": "2015-04-01T10:15:53.670Z",
  "editor": "FCP Media"
}

```

### Deleting an event
**DELETE:** *http://www.roscommoncoco.ie/api/events/[event_id]*.

**HTTP Request Example**
```http
DELETE /api/events/43 HTTP/1.1
Host: roscommoncoco.ie
Content-Type: application/json; charset=utf-8
Content-Length: 1
{"OAuthCredentials": [...]}
```
**HTTP Response Example**
```http
HTTP/1.1 204 No Content
```

####Most errors return 400 Bad Request. A bad request, for example, will receive a response like this:
```http
HTTP/1.1 400 Bad Request

{"message": "Unable to decode data"}
```
