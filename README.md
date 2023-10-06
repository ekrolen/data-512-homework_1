# data-512-homework_1

### Purpose:
The goal of this project is to acquire monthly article traffic data, analyze it, and publish the  results in a reproducible way.

### Sources and Licenses:
The source data uses the following license:
**EKRC INSERT LICENSE HERE

We also use the Wikimedia Foundation REST API which has the following
terms of use:
https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions

The Pageviews API documentation can be found at the following link:
https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews

We will leverage code developed by Dr. David W. McDonald for use in Data 512  which is provided under Creative Commons CC-BY license. (https://creativecommons.org/ and https://creativecommons.org/licenses/by/4.0/)

Additionally, we will be using a list of Academy Award winning article titles provided by Dr. McDonald. A link to the list can be found here: https://drive.google.com/drive/folders/1lPJF73GX5Vyu2uAvT5VpAY-xGwP2fCCx

### Steps to replicate results:
1. Download thank_the_academy.AUG.2023.csv from https://docs.google.com/spreadsheets/d/1A1h_7KAo7KXaVxdScJmIVPTvjb3IuY9oZhNV4ZHxrxw/edit#gid=1229854301. Save this data in your project repository in the "raw_data" directory.

2. **EKRC INSERT REST OF STEPS

### Data Files Created:
The code will produce 3 raw data files: mobile_app_pageviews.json, mobile_web_pageviews.json, and desktop_pageviews.json. The files are organized by article titles (keys) and the value variables are as follows:

    "project" - this is the domain of the wikipedia project. Our domain will always be "en.wikipedia.org"
    "article" - this is the name of the article who's pageviews we are pulling
    "granularity" - this is the time period of pageviews, ours will always be "monthly"
    "timestamp" - this is the timestamp in YYYYMMDDHH e.g., "2016010100"
    "access" - this is the article access method and will vary between "mobile-app", "mobile-web", and "desktop"
    "agent" - this is the type of agent, we will only be looking at "user"
    "views" - this is the number of pageviews over the timestamp specified
    

