# Looker training
###### The purpose of this issue is to provide practice exercises in Looker, covering key functionalities such as adding data sources, creating blended data, and adding data from multiple sources. The trainee will practice blending data using the Austin Bikeshare Dataset (tables bikeshare_stations and bikeshare_trips) and perform other exercises using the Kaggle Housing Prices Dataset (imported as CSV). The trainee will also practice creating calculated fields, metrics, filters, visualizations, customizing dashboards, and managing permissions.
---
***1. Add Data Sources (Kaggle CSV,  BigQuery)***

* Add data from multiple sources to Looker.

**Task:**

* Download the **Kaggle Housing Prices Dataset** from ***Kaggle***.

* Upload the dataset in **CSV format** into Looker.

* Add the following data sources:

    * **CSV:** Kaggle Housing Prices dataset.

    * **BigQuery:** Use the Austin Bikeshare Dataset (bigquery-public-data: austin_bikeshare.bikeshare_stations and bikeshare_trips).

* Document the steps for connecting each data source to Looker.

    - First to all We downlad the csv file and put it in to our project folder:

    ![1](src/img/1.png)

    - To create a Datasource, select + Create and then Data source:

    ![1](src/img/2.png)

    - After that We select from wich source came the data, this time We will choose File Upload:

    ![1](src/img/3.png)

    - To finish the proces We just find our file and select Open for the upload.

     ![1](src/img/4.png)

    - Now, if We want to load a dataset from a tables in BigQuery We try the next steps:

        - We can choose our own projects just by selecting it and his dataset and his tables, but for this case We gonna choose a two tables of a public dataset in BigQuery and We get their data with a simple query:
        `Custom query->Billing Project`(here if We dont see our project, We can add it manually in the "Enter project id manually")`->Enter Custom Query`.
        And then select Connect. Example:
    
    ![1](src/img/5.png)


| **TASK**    | :white_check_mark: |
| :---        |               ---: |

---

***2. Create Blended Data (Austin Bikeshare)***

* Learn how to create blended data by combining data from the **Austin Bikeshare Dataset.**

**Task:**

* Blend the **bikeshare_stations** and **bikeshare_trips** tables from the Austin Bikeshare dataset.

* **Join type:** Use an **inner join** on the `station_id` field to blend the data between the trips and stations.

* Example: Calculate the number of trips per station, and blend this with station data such as the location (latitude, longitude).

* Use this blended data to create visualizations, such as:

    * A bar chart showing the number of trips per station.

    * A map displaying the locations of stations and the number of trips originating from each station.

* Document the process of blending the data and creating the visualizations.

    - For the blend of the tables We going to create de blend from BigQuery bringing us both tables with the requested **inner join**.

    ![1](src/img/6.png)

    - Now, to show the data, first we need to create a Report, like we create a data source but choosing the new report button.

    ![1](src/img/7.png)

    - After click in the new report button, looker will ask us the origin of our data, for this example we gonna choose BigQuery option and repeat the previous task for adding new datasource from BigQuery, all of this using the blend query we create in BigQuery:

    ![1](src/img/8.png)

    - If the project was created correctly, we can saw the button for our data at the right and clicking it will show our field for the query.

    ![1](src/img/9.png)

    - To create a chart We the trips per station, we need to add the chart to the page, in this case We will use a basic table.

    ![1](src/img/10.png)

    - Now, to show data in this table We need to drag some variables to de Dimension section (green background) and this will be the data that we want to show as it is. To form a group with another data we just drag the variable to the metric section (first blue background) and specify the function we want on that metric (sum, max, min, avg, etc.).

    ![1](src/img/11.png)

    -  For this example we just only need the name of the station and the numbre of trips starter on that station, using a metric of SUM, to apply this just click at left of the blue section where the CT is visible and then choose the right metric we want and We can change the name of the column at the first option:

    ![1](src/img/12.png)

    - To make a bar chart We just to add the chart and use the same variables for this case:

    ![1](src/img/13.png)

    - Finally for the map chart, the bikeshare dataset was not including a latitude and longitude datas, then for this case we use another public dataset: `faa.us_airports` wich We use a BigQuery to bring us all the public airpots, name and lattitude and longitude in the New York state, to show where they are and his name. (Important, to show data in a map is strongly recomended that We have to have a field with this format in the value: `POINT(-65.3038783 18.31295177)` to Looker can show it in a easier way on "geospatial field" parameter). Remeber, when we create this project We have to call our data from BigQuery and put it the query previously reviewed in BQ. 

    ![1](src/img/14.png)

| **TASK**    | :white_check_mark: |
| :---        |               ---: |

---

***3. Create Calculated Fields (Kaggle Housing Prices)***

* Create calculated fields based on the Kaggle Housing Prices Dataset.

**Task:**

* Example calculated fields:

    * **Price per square foot:** Create a calculated field that divides the `SalePrice` by the `GrLivArea` (Above ground living area).

    * **Estimated monthly mortgage:** Use a fixed interest rate and loan term to estimate the monthly mortgage payments based on `SalePrice`.

* Document the process for creating these fields and use them in visualizations.

    * For this exercise We need to use a fields that are not include in csv file, so We need to create values using others values, for that We have to choose the "+ Add field" at the bottom of the data column then choose a "add calculated field", Next we put the name of our new data field and in the formula input We put our operation as complex as necessary, either dragging them clicling them or writing them:

    ![1](src/img/15.png)

    ![1](src/img/16.png)

    * For the Estimated monthly mortgage we solve by the same way, just creating anothers field that we can manipulated to have the values we want.

| **TASK**    | :white_check_mark: |
| :---        |               ---: |

---

***4. Create Metrics***

* Define key **metrics** using the Kaggle Housing Prices Dataset.

**Task:**

* Create metrics such as:

    * **Average home price:** Calculate the average value of SalePrice.

    * **Total number of homes sold:** Count the total entries in the dataset.

    * **Average living area:** Calculate the average of GrLivArea.

* Add these metrics to a dashboard and document their creation.

    * For this task We need to create a charts per metrics they ask of us. We gonna use the Scorecard chart. In the properties column we just add the field that we want to calculate and pick the function We need, AVG for sales and another chart with AVG too for the area, for the total of sales Looker creat by default a data with the total of rows of each dataset that We add at project named Record count.

    ![1](src/img/17.png)

| **TASK**    | :white_check_mark: |
| :---        |               ---: |

---