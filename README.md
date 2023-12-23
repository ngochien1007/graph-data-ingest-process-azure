# Ingest and Process Facebook graph data with Azure

This is a part of the project named **Facebook Friend Recommendation System** that my team and me did when studying the subject of **Social Networking** at UIT. This project is all about how we ingested, processed and enriched graph data and next, built a web application using React and NodeJs. I was responsible for the task of batch data ingestion and processing. 

## Architecture

![FlowBatchProcessing](https://github.com/ngochien1007/graph-data-ingest-process-azure/assets/154615929/9fc002f5-9374-486b-81e8-27fc2e230931)

## Idea

- `Batch Ingestion`: To start, split the original data file into 4 partitions. Next, add the partitions to the pipeline and use the Wait activity to set the delay to 1 minute. This means that after each partition is added to the Data Storage (Output container), it will wait for 1 minute in the Wait activity before adding the next partition to the Storage.
- `Batch Processing`: Firstly, connect Data Lake Storage to Databricks. Then, load the data into Databricks for preprocessing. This includes the following steps:
  -   Merge the partitions into a single dataframe.
  -   Simulate the data (user name and age).
  -   Map the data between the edges (from FromUser to ToUser).
    
    Finally, load the processed data back into Storage (Data Lake Storage).
## File Stucture

- `visualization_EDA`: Process the original data file into suitable format and visualize for exploratory data analyst.
- `batch_processing`: Process the batch data after ingesting into data storage.

## Related Resources

- Dataset: [SNAP | Social Circles: Faceboook](https://snap.stanford.edu/data/ego-Facebook.html)
- Video: [Batch Ingestion with Data Factory](https://youtu.be/fzqeo3ojYaQ)

## References
