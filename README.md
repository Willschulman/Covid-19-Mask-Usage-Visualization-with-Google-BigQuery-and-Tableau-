# Covid-19-Mask-Usage-Visualization-with-Google-BigQuery-and-Tableau-

After learning a considerable amount of SQL, I began looking for large, realworld databases where I could practice writing more complex queries.  

I became aquainted with Google's Data Wherehouse BigQuery and it's vast array of public datasets. Given my background in Sociology, I'm no stranger to the American Community Survey ("ACS") the thorough and expansive demographic survey conducted by The United States Census Bureau. The ACS is comprised of numerous variables including: age, race/ethnicity, gender, employment, housing, and many others. It's an excellent source of information for community level demographic charectatistics. When evaluated alongside other variables of interest it becomes a treasure trove of explanatory power.

Enter BigQuery.

The ACS collects data at many different levels (state, county, zipcode, geographic coorrdinates). Since it's county level data uses the county fips code as it's unique primary key, it's easy to combine the ACS table with other tables that have county level data identified with the county fips code.

The New York Times conducted a survey on county level mask data in July:
https://www.nytimes.com/interactive/2020/07/17/upshot/coronavirus-face-mask-map.html

The New York Times also regularly collects county level COVID-19 data: 
https://www.nytimes.com/interactive/2021/us/covid-cases.html

Both of these datasets are housed in google's data warehouse and both use the county fips code as their unique primary key. 
