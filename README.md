# gcp-etl-pipeline-tutorial-followalong
This ETL pipeline was created by following a YouTube tutorial by TechTrapture. Original video: https://youtu.be/kxV4_xDchCc?si=n9K4TxM9ld4g0EoC and https://youtu.be/lMaZnZldxcE?si=viJPbFsLfpUDX_6a  
This project is a personal learning exercise. All code was written independently while referencing the tutorial.

## The tech stack/pipeline used is shown below.
![etl drawio](https://github.com/user-attachments/assets/b932f4e1-454f-4ab9-a9a1-dc0ae249d85f)

### data extraction
1. Using a ChatGPT prompt, a Python script was created to create fake data using the library faker. The data is then saved into a CSV file and uploaded to a bucket in cloud storage.
### data transformation (masking)
2. The file in the bucket is then fed into a data fusion instance, where some transformation (combining first and last names, masking PII) is performed using the UI provided.
### data loading
3. Using the UI, BigQuery is then added to the pipeline. The pipeline is then run to load the data into BigQuery.

### Jobs Orchestration
After doing it manually, the whole process above is then automated/orchestrated using Cloud Composer with Apache Airflow by uploading a DAG file to the Composer instance.
The DAG file includes a bash operator and a suitable gcp airflow operator and was created using GPT prompt also.
