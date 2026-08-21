# databricksfirstproject



# 4.	Create storage account
5.	Create container- Healthcare- Created folders (appointments, lab_results, meditcation_data, medical_history, patient_data and symptoms_data
6.	create app registration
7.	storage account-access control IAM- created role assignment (storage blob Data contributor )-added member as app reg
8.	Create Azure databricks
9.	Workspace Launch
10.	Create all purpose compute
11.	Under catalog: Created bronze and silver schema. Under bronze, created Volume as metadata_files
12.	Storage Credential is necessary if you want Unity Catalog to securely access your ADLS Gen2 storage through the Access Connector.
13.	In Databricks, go to Catalog → Connect → Credentials → Storage credentials → Create credential.
14.	Choose Azure Managed Identity, give it a name such as adls_storage_credential, and paste your Access Connector Resource ID from Azure.
15.	In the Azure Portal: Open Access Connectors for Azure Databricks. Access Connector for Azure Databricks → your connector → Overview → Resource ID
example: /subscriptions/<subscription-id>/resourceGroups/<resource-group>/providers/Microsoft.Databricks/accessConnectors/<connector-name>
16. In Databricks, go to Catalog → Connect → External Data → External Locations → Create external location
17. Name: e.g. project_adls
URL: your ADLS Gen2 path, such as abfss://<container>@<storage-account>.dfs.core.windows.net/
Storage credential: select the Storage Credential you just created.
18. Storage Account → Access Control (IAM) → Check access. Search/select Access Connector for Azure Databricks, then select your connector.
19. Go to:Storage Account → Access Control (IAM) → Add → Add role assignment
Choose:
Role: Storage Blob Data Contributor
Then on Members:
Assign access to: Managed identity
Click Select members, then choose:
Managed identity: Access Connector for Azure Databricks
Select the Access Connector you created earlier, then Review + assign.
20. 
   
