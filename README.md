# Olympics in Tokyo - 2021 
**Azure Cloud**

Tokyo-olympic-data-engineering-project

## Description
***
### Datapipe line to ingesting, loading and transforming the data using various azure services to do a POC for data analysis using PowerBI

## Datapipe line - Architectural Diagram 

![image](https://github.com/bhaskarpathak609/tokyo-olympic-azure-data-engineering-project/assets/110766706/a5061333-8036-42a3-843b-0d1ca7136053)

Create storage account

Create container with name ```tokyo_olympic-data```

Inside ```tokyo_olympic-data``` create two folders

+ _raw_data_ - stored the data as it is in raw form coming from git
+ _transfored_data_ - stored the transformed data using pyspark in databricks

## The movement of data
***
External source from ```Git``` > Azure cloud storage inside ```raw_data``` folder > Transformations in ```databricks``` using PySpark > Azure cloud storage inside ```transformed_data``` folder > Azure Synapse Analytics

## Services used
***
_Data Source_ - Data kept in git ```folder name``` **data** [https://github.com/bhaskarpathak609/tokyo-olympic-azure-data-engineering-project.git](url)
+ athletes.csv
+ coaches.csv
+ entriesgender.csv
+ medals.csv
+ teams.csv

#### Data_ingestion  
_Data factory_ - Here we will create data pipelines to ingest data from ```git folder``` to the ```raw_folder``` using **azure_data_factory**

![image](https://github.com/bhaskarpathak609/tokyo-olympic-azure-data-engineering-project/assets/110766706/944ff087-652b-4bbc-834b-a0ebf9e3f64a)

### For transformation 
_Databricks_ - ```Tokyo_olympics_transformations.ipynb```

After data transfomation using PySpark store the data back to ```transformed_data``` folder inside the storage container

Now the data is in transformed state inside the **data lake gen 2**

### Getting insights 
_Azure Synapse Analytics_ - is a limitless analytics service that brings together enterprise data warehousing and Big Data analytics privilege us with services like using ADF, runing SQL queries, Python/PySpark code using either serverless or dedicated resources
+ Creating database
+ Creating tables for all the .csv files inside ```transformed_data``` folder
+ Run SQL commands to get the insights from the data even pyhton codes can be executed

![image](https://github.com/bhaskarpathak609/tokyo-olympic-azure-data-engineering-project/assets/110766706/baa64323-bed2-4530-b68a-fb13ad1be31e)


