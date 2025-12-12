Storage Event Trigger with Example- 

What is Storage Event Trigger - 

Storage Event Trigger is like a “doorbell” for your Azure storage. When a new file comes in, ADF hears the bell and runs your pipeline right away.

👉 Storage Event Trigger in ADF-
- Imagine you have a folder in the cloud (Azure Blob Storage or ADLS).
- Whenever someone drops a new file into that folder, ADF immediately notices it.
- As soon as the file arrives, ADF can kick off a pipeline automatically — for example, to move the file to another place, process it, or load it into a database.
- It only works with Azure storage accounts (Blob or ADLS). If files are added somewhere else (like SharePoint or Google Drive), this trigger won’t fire.
 In short: Storage Event Trigger is like a “doorbell” for your Azure storage. When a new file comes in, ADF hears the bell and runs your pipeline right away.

👊I have created storage event trigger in ADF , below are screenhsots. I created new pipleine ,added copy data activity and configured source and sink. Configured
a trigger for this pipeline and selected storage events type,specified start date, selected start trigger box and click on OK. once we start executing this 
pipeline it will start copying data files from source to destination specifed in copy data activity.

👊we can also delete files in source once the files are copied to destination sucessfully. To do this i have added Delete from activites and configured this .

👊I tested this and worked sucessfully. WOW Amazing experience.

✌️ Snapshot of pipeline in ADF -

<img width="1918" height="488" alt="image" src="https://github.com/user-attachments/assets/6747b5e6-98b1-49c6-801d-0a43f5cf1802" />


✌️While running first copy activity file got stored in to detsination container @ 6:52 PM

<img width="1922" height="982" alt="image" src="https://github.com/user-attachments/assets/32aa94f6-376c-42a2-adda-94843dff13e0" />

✌️@ 6:53PM I added new file and the trigger started and executed the pipeline, below two screen shots shows the same and delete activity also perfromed
sucessfully.

<img width="1912" height="1022" alt="image" src="https://github.com/user-attachments/assets/ec1805f6-ae85-4986-9fef-a531c1f5aed2" />

<img width="1918" height="387" alt="image" src="https://github.com/user-attachments/assets/c70fbe4d-a6f8-4773-845e-21f06603fa05" />

<img width="1922" height="1035" alt="image" src="https://github.com/user-attachments/assets/03f671de-cfc2-429a-b637-e57357a2757d" />

<img width="1907" height="1038" alt="image" src="https://github.com/user-attachments/assets/8c37909e-5d3a-4772-bda8-90217cdd9f15" />4





