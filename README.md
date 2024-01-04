# Azure database migration Project
- This is my third project in the AiCore course
- In this project, we established a production environment database, then migrated the database to Azure SQL Database, focusing on crucial aspects like data backup, restoration, and automated scheduling.
- A pivotal phase of the project involved simulating a disaster recovery scenario with potential data loss. Furthermore, we explored the complexities of geo-replication and failover configuration to ensure data availability even under challenging conditions.
- To enhance security, Microsoft Entra ID integration was employed to define access roles, adding an extra layer of control and protection.

# Installation instructions
- Azure portal, Microsoft Remote Desktop, SQL Server and SQL Server Management Studio (SSMS).

# Usage instructions
- Using AiCore provided subcription, create a Virtual Machine (VM) on Azure portal.
- Use the RDP protocol and Microsoft Remote Desktop to establish a secure connection to the VM.
- Install SQL Server and SQL Server Management Studio (SSMS) on the VM.
- Create the production database by restoring it from provided backup file. The backup file corresponds to the renowned Microsoft SQL Server database known as AdventureWorks.

# File structure of the project
- Data extraction. In "data_extraction.py" we store methods responsible for the upload of data into pandas data frame from different sources.
- Data cleaning. In "data_cleaning.py" we develop the class DataCleaning that clean different tables, which we uploaded in "data_extraction.py".
- Uploading data into the database. We write DatabaseConnector class "database_utils.py", which initiates the database engine based on credentials provided in ".yml" file.
- "main.py" contains methods, which allow uploading data directly into the local database. 

# License information
- Non required. Public repository.
