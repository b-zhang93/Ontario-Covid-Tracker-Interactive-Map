Ontario COVID-19 Tracker Project
========================================================
author: Bowen Zhang
date: June 24,2020
autosize: false
transition: rotate
font-family: 'Helvetica'

<style>
.small-code pre code {
  font-size: 1em;
}
</style>

Introduction
========================================================
This presentation is to introduce the Shiny application: Ontario Covid Tracker
<br>

## Overview:

- The application was built in Rstudio with the Shiny App and Leaflet packages. Here is an Overview:
- The tracker allows users to view geographical data on each of the cases of COVID-19 in Ontario, Canada.
- Users can filter the data and view the reactive map's results

<br>
*Data API is from Ontario Data Catalogue:  [Link](https://data.ontario.ca/dataset/confirmed-positive-cases-of-covid-19-in-ontario/resource/455fd63b-603d-4608-8216-7d8647f43350)*



The Data
========================================================
class: small-code
<small>
We obtained the data via API and sourced 5 out of the 17 original variables for relevance. 

- Outcome1: The outcome of each case reported as of the current date
- Case_Reported_Date: Date which the case was reported
- Reporting_PHU_Latitude: Latitude of the reporting Public Health Unit
- Reporting_PHU_Longitude: Longitude of the reporting Public Health Unit
- Reporting_PHU: Name of the Public Health Unit reporting the case
</small>


```
'data.frame':	34016 obs. of  5 variables:
 $ Outcome1               : chr  "Resolved" "Resolved" "Resolved" "Resolved" ...
 $ Case_Reported_Date     : chr  "2020-05-09T00:00:00" "2020-05-21T00:00:00" "2020-05-29T00:00:00" "2020-05-30T00:00:00" ...
 $ Reporting_PHU_Latitude : num  43.7 43.7 43.7 43.7 43.7 ...
 $ Reporting_PHU_Longitude: num  -79.4 -79.4 -79.4 -79.4 -79.4 ...
 $ Reporting_PHU          : chr  "Toronto Public Health" "Toronto Public Health" "Toronto Public Health" "Toronto Public Health" ...
```


Functionality
========================================================
- Interactive map showing clusters of COVID-19 cases in Ontario
- Filter by status: Resolved, Fatal, Not Resolved
- Filter by date the cases were reported
- Filter by individual Public Health Unit
- Dive into each cluster to view Markers for individual cases (zoom in and click on cluster)
- Dive into each individual case to see status and date for the patient (click on the marker)


Conclusion
========================================================
Here is a quick output of the total number of cases (June 24/20):

```r
length(covdata[,1])
```

```
[1] 34016
```

<br><br><br>
Try the Ontario Covid Tracker Shiny App yourself: [Link Here](http://bzhang93.shinyapps.io/covid-tracker)

Github: [Link Here](http://github.com/b-zhang93/Ontario-Covid-Tracker-Interactive-Map) 

