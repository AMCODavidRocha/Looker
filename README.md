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