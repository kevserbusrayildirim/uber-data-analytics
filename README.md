# Uber Data Analytics
  The project aims to analyze Uber data. However, the dataset consisting of real-world data is in its raw form, making it difficult to work with. Therefore, the data should be modeled. Tables with the necessary relationships are created, and some preprocessing steps have been applied to make the data usable, such as formatting the data set appropriately and cleaning up repeated values. Data transformation operations were simply applied in an ipynb file.  
  
## Project Architecture 
  
![architecture](https://github.com/kevserbusrayildirim/uber-data-analytics/assets/61944895/222ee9d7-8afe-4ffe-a66c-b69e9681530f)
  
  
Operations carried out in the Uber Data Analytics project are as follows:  
  
1 - The dataset containing Uber data is stored by creating a bucket on the Google Cloud platform.  
2 - Requests are made to the created Uber Data Analytics API to access the dataset.  
3 - An instance is created on the Google Cloud platform for the Virtual Machine where pipeline operations will be executed. The Virtual Machine is started via SSH connection.   
The following commands are executed:    
  
* sudo apt-get update -y    
* sudo apt-get install python3-distutils  
* sudo apt-get install python3-apt  
* sudo apt-get install wget  
* wget https://bootstrap.pypa.io/get-pip.py  
* sudo python3 get-pip.py  
To install Mage AI: sudo pip3 install mage-ai  
  
4 - Access is obtained to the IP and Port addresses for the Virtual Machine and Mage connection. After establishing the Mage connection in the virtual machine terminal, the port on which it operates is specified.  
5 - In order for the Port to be used, a Firewall rule is created on the virtual machine to allow access. In this section, the port on which Mage will operate should be defined in the TCP section.  
6 - After establishing the Mage connection, pipeline operations begin.  
  
#### **Performing Pipeline Operations Using Mage:**    
1 - A Data Loader is created to make requests to the API on Google Cloud. The request should successfully return the dataset.  
2 - A pipeline is created with the Transformer to perform transformations on the data. Transformations that will enable us to analyze the data properly, as in the ipynb file, are done at this stage.
3 - Credentials are created for using the Data Exporter API.
4 - The 'Key' section in the configuration file named io_config.yaml is filled with the created credential.
Thus, the pipeline stages are completed.  
    
#### **For Data Analysis with BigQuery:**    
1 - A dataset is created in BigQuery Studio on GCP to store the data exported from the pipeline.  
2 - BigQuery configurations are also made on the data exporter and run.  
3 - Another SSH connection is established to the Virtual Machine to install BigQuery on the Virtual Machine.  
4 - Data is sent to BigQuery using the Data Loader.  
5 - SQL queries can be made for Data Analysis with BigQuery. As a result, an Analysis Report is obtained. You can access these queries from the analytics_query.sql file.  
    
#### **Data Analysis Visualization with Looker:**    
In this part of the project, visualization is performed as in the [link]([link](https://lookerstudio.google.com/u/0/reporting/427cf309-8aa9-4dc3-90d5-34113f476e82/page/iF6nD?s=ljeB8mXKW5I)) using the analysis report obtained from BigQuery, making the analysis more meaningful for users.  
<img width="523" alt="image" src="https://github.com/kevserbusrayildirim/uber-data-analytics/assets/61944895/34bc82d0-0692-471e-8386-962d5d93568d">  
  
  
I would like to thank Darshil Parmar for the tutorial I benefited from and for his work.
