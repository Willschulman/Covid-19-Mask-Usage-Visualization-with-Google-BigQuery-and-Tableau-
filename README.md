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

Using SQL, I wrote this query to retrieve a dataset combining these three data sources.
 
 ![Screen Shot 2021-05-01 at 12 10 47 PM](https://user-images.githubusercontent.com/75948597/116788259-a2da2400-aa76-11eb-8fca-cfb36e32e2fa.png)
 ![Screen Shot 2021-05-01 at 12 13 14 PM](https://user-images.githubusercontent.com/75948597/116788277-aec5e600-aa76-11eb-829a-69afc732c208.png)


As you can see, I converted the mask usage survey results into a single statistic which I call "mask score".
 
 
I also wrote a second query to retrieve summary statistics 
![Screen Shot 2021-05-01 at 12 19 42 PM](https://user-images.githubusercontent.com/75948597/116788751-6b20ab80-aa79-11eb-8734-91b7652ef297.png)
![Screen Shot 2021-05-01 at 12 52 45 PM](https://user-images.githubusercontent.com/75948597/116789305-37935080-aa7c-11eb-9120-ddb3d4874596.png)

Then I used the qnorm function in r to determine the 33.3 and 66.6 percentile markers.

 ![Screen Shot 2021-05-01 at 12 23 15 PM](https://user-images.githubusercontent.com/75948597/116788601-8ccd6300-aa78-11eb-8b2f-2ea9cda22fbe.png)
![Screen Shot 2021-05-01 at 12 22 25 PM](https://user-images.githubusercontent.com/75948597/116788602-8ccd6300-aa78-11eb-8dfd-67633ec4da83.png)

I then took the percentintile markers and used a Case statement within my query to classify each county as "high", "med", or "low".
![Screen Shot 2021-05-01 at 12 54 31 PM](https://user-images.githubusercontent.com/75948597/116790864-b2f90000-aa84-11eb-933e-b579faf90f5f.png)

I ran my query and returned the following table:
![Screen Shot 2021-05-01 at 2 06 59 PM](https://user-images.githubusercontent.com/75948597/116820384-ccf91800-ab42-11eb-9016-a36f061edd75.png)

Then I downloaded the data as a csv file and imported it into Tableau for vizualization and analysis.





 
