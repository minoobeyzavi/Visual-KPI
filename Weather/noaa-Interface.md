 ## NOAA
 
 Using [Postman](https://www.getpostman.com/docs/introduction), add a key to header as "token" with the value "dmvfhINKHBVgAWGFxEsicLiaMAhNKSgy" obtained from [Token Request Page](https://www.ncdc.noaa.gov/cdo-web/token).

<div align="center"><img src="https://github.com/minoobeyzavi/Visual-KPI/blob/master/Images/postman-noaa.png"/></div></br>


 ```
 Base Address  https://www.ncdc.noaa.gov/cdo-web/api/v2/
 ```
 
 ### Current Data
 Availability per location is varied and most up-to-date data usually dates back to yesterday.
 ```
 Request URI: data?datasetid=GHCND&locationid=ZIP:{ZIPCODE}&units=standard&startdate={DATE}&enddate={DATE}&datatypeid={DATATYPEID}
 Result Base Path: results
 Value Field: .value
 Timestamp Field: .date
  ```
 Enter ZIPCODE, the same DATE for startdate and enddate and then DATATYPEID manually.

 ### Forecast (Trend Data)
 ```
 Request URI: data?datasetid=GHCND&locationid=ZIP:{ZIPCODE}&units=standard&startdate={STARTDATE}&enddate={ENDDATE}&datatypeid={DATATYPEID}
 Result Base Path: results
 Value Field: .value
 Timestamp Field: .date
 ```
 Enter ZIPCODE, STARTDATE, ENDDATE and DATATYPEID manually.
 
 ### Historical Data
 ```
 Request URI: data?datasetid=GHCND&locationid=ZIP:{ZIPCODE}&units=standard&startdate={DATE}&enddate={DATE}&datatypeid={DATATYPEID}
 Result Base Path: results
 Value Field: .value
 Timestamp Field: .date
 ```
 Enter ZIPCODE, the same DATE for startdate and enddate and then DATATYPEID manually.

## Notes
https://www.ncdc.noaa.gov/cdo-web/webservices/v2#data
</br>token:	dmvfhINKHBVgAWGFxEsicLiaMAhNKSgy</br>
[Token Request](https://www.ncdc.noaa.gov/cdo-web/token)

 Useful Addresses:
 ```
 Locations in GHCND Dataset  https://www.ncdc.noaa.gov/cdo-web/api/v2/locations?datasetid=GHCND
 Location Categories  https://www.ncdc.noaa.gov/cdo-web/api/v2/locationcategories
 ```

<b>datasetid</b> Required</br> 
A single valid dataset id e.g. datasetid=GHCND.

<b>startdate & enddate</b> Required</br>
(YYYY-MM-DD) format e.g. startdate=2017-01-01. Annual and Monthly data will be limited to a ten year range while all other data will be limited to a one year range.

<b>locationid</b> Optional</br>
A valid location id or a chain of location ids seperated by ampersands e.g. ZIP:94103.

<b>units</b> Optional</br>
Accepts 'standard' or 'metric'.

<b>datatypeid</b> Optional</br>
For the GHCND dataset, available datatypes are PRCP, TMAX & TMIN.

<b>limit</b> Optional</br>
Default is 25. Limits the number of results in the response. Maximum is 1000.


<div align=center><img src="https://github.com/minoobeyzavi/Visual-KPI/blob/master/Images/postman-noaa-trendData.png"/></div>
