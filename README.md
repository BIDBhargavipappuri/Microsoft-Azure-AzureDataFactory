Microsoft Azure Practice Documentation -
1. 🔹 Resource Group
What it is
• A Resource Group is a logical container in Azure that holds related resources (like storage accounts, databases, Data Factory, Synapse, etc.).
• It helps with:
• Organization → Grouping all resources for a project.
• Access Control → Assigning RBAC roles at the group level.
• Lifecycle Management → Deleting the group removes all resources inside.
• Cost Tracking → Monitor billing per group.

   How To create it
1. Logged into the Azure Portal.
2. Navigated to Resource Groups → Create.
3. Selected a Subscription.
4. Entered a Resource Group name (e.g., PracticeRG).
5. Chose a Region (important for latency and compliance).
6. Clicked Review + Create → Create.


2.🔹 Storage Account

What it is
• A Storage Account provides access to Azure Storage services:
o Blob Storage → For unstructured data like files, logs, images.
o Data Lake Storage Gen2 → For big data analytics with hierarchical namespace.
o File Shares, Queues, Tables → Other storage types.
• It’s the foundation for storing raw and curated data in BI/ETL workflows.

How To create it-
1. In the Azure Portal, searched for Storage Accounts → Create.
2. Selected the Resource Group (PracticeRG).
3. Entered a Storage Account name (globally unique, e.g., practiceadlsgen2).
4. Chose a Region (same as resource group for consistency).
5. Selected Performance (Standard vs Premium).
6. Selected Redundancy (e.g., LRS, GRS).
7. Enabled Hierarchical Namespace if using Data Lake Gen2.
8. Clicked Review + Create → Create.

 
 3.🔹 Azure Data Factory (ADF)
What it is
• Azure Data Factory is a cloud-based ETL/ELT service for data integration and orchestration.
• It lets you:
• Build pipelines to move and transform data.
• Connect to multiple sources (SQL, Blob, ADLS, APIs).
• Schedule workflows with triggers.
• Monitor and manage data flows.

How To create it

1. In the Azure Portal, searched for Data Factory → Create.
2. Selected the Resource Group (PracticeRG).
3. Entered a Data Factory name (e.g., PracticeADF).
4. Chose a Region (same as storage account).
5. Selected Version (V2 is default).
6. Clicked Review + Create → Create.
7. Once deployed, opened ADF Studio to design pipelines.

<img width="1395" height="450" alt="image" src="https://github.com/user-attachments/assets/f80f2295-e0d6-442f-93c1-123e6537d6ac" />







Azure Data Factory Launching and Practice with Pipeline Building and scheduling Trigger- 


Azure Data Factory Pipeline Documentation
1. 🔹 Launching Azure Data Factory
- Opened Azure Portal and navigated to Azure Data Factory.
- Created a new pipeline inside the Data Factory workspace.
- Defined the pipeline name and linked it to the existing Resource Group and Storage Account.


2. 🔹 Connecting to API (HTTP Linked Service)
- Created an HTTP Linked Service in ADF to connect to the external API.
- Configured the base URL and authentication (if required).
- Added a Copy Activity to pull data from the API endpoint.


3. 🔹 Extracting Files from API Response
- Used the Get Metadata Activity to inspect the files returned by the API.
- Configured the activity to list file names.
- Applied a filter to select only the file(s) starting with the prefix “FACT”.


4. 🔹 Iterating with ForEach Loop
- Added a ForEach Activity to loop through the filtered file list.
- Inside the loop, configured activities to process each file individually.
- Ensured only the FACT-prefixed file was passed downstream.


5. 🔹 Data Flow for ETL
- Designed a Mapping Data Flow to perform transformations:
- Cleansing and formatting data.
- Applying business rules.
- Restructuring columns for analytics.
- Defined the sink dataset as the destination for transformed data.


6. 🔹 Saving to Sink and Storage Account
- Configured the sink to write transformed data into the Azure Storage Account.
- Selected Blob Storage / Data Lake Gen2 as the destination.
- Verified that the output files were successfully stored in the designated container.


7. 🔹 Outcome
- Successfully built an end-to-end pipeline in Azure Data Factory.
- Automated pulling data from an API, filtering specific files, applying ETL transformations, and storing results in Azure Storage.
- Documented and saved the pipeline for future reuse and reference.


<img width="1918" height="522" alt="image" src="https://github.com/user-attachments/assets/ee6360d3-5050-4bc6-8727-f68e07537886" />

