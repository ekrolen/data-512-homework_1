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

### Files Created:
The code will produce 3 raw data files: mobile_app_pageviews.json, mobile_web_pageviews.json, and desktop_pageviews.json. The files are organized by article titles (keys) and the value variables are as follows:

    "project" - this is the domain of the wikipedia project. Our domain will always be "en.wikipedia.org"
    "article" - this is the name of the article who's pageviews we are pulling
    "granularity" - this is the time period of pageviews, ours will always be "monthly"
    "timestamp" - this is the timestamp in YYYYMMDDHH e.g., "2016010100"
    "access" - this is the article access method and will vary between "mobile-app", "mobile-web", and "desktop"
    "agent" - this is the type of agent, we will only be looking at "user"
    "views" - this is the number of pageviews over the timestamp specified
    
The code will then produce 3 clean data files: academy_monthly_cumulative_201507-202309.json, academy_monthly_desktop_201507-202309.json, academy_monthly_mobile_201507-202309.json. The fields are as follows:

    "project" - this is the domain of the wikipedia project. Our domain will always be "en.wikipedia.org"
    "article" - this is the name of the article who's pageviews we are pulling
    "granularity" - this is the time period of pageviews, ours will always be "monthly"
    "timestamp" - this is the timestamp in YYYYMMDDHH e.g., "2016010100"
    "agent" - this is the type of agent, we will only be looking at "user"
    "views" - this is the number of pageviews over the timestamp specified

For academy_monthly_mobile_201507-202309.json, the "views" field will be a sum of both the mobile app and mobile web raw monthly views. For academy_monthly_cumulative_201507-202309.json, the "views" field will be a sum of the views in the clean mobile file and desktop file.

The final output of the program is 3 graphs.

    
### Known Data Issues and Considerations
1. Not all files can be pulled using the Pageviews API. Specifically, the article title "Victor/Victoria" cannot be pulled due to the inclusion of the "/" and its interpretation in the API. Because of these issues, the article will not be included in the analysis.

2. Not all pageviews may refer to views of a movie's page. As an example, "Encanto", a film released in 2021, has pageview data starting in 2015. It's possible that this may be occurring for other movies' pages that have names which would be found in other contexts.

