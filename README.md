# Azure database migration Project
- This is my third project in the AiCore course
- In this project, we established a production environment database, then migrated the database to Azure SQL Database, focusing on crucial aspects like data backup, restoration, and automated scheduling.
- A pivotal phase of the project involved simulating a disaster recovery scenario with potential data loss. Furthermore, we explored the complexities of geo-replication and failover configuration to ensure data availability even under challenging conditions.
- To enhance security, Microsoft Entra ID integration was employed to define access roles, adding an extra layer of control and protection.

# Installation instructions
- Azure portal, Microsoft Remote Desktop, SQL Server, SQL Server Management Studio (SSMS), Azure Data Studio, integration runtime

# Tasks completed
- Used AiCore provided subcription, created a Virtual Machine (VM) on Azure portal.
- Used the RDP protocol and Microsoft Remote Desktop to establish a secure connection to the VM.
- Installed SQL Server and SQL Server Management Studio (SSMS) on the VM.
- Created the production database by restoring it from provided backup file. The backup file corresponds to the renowned Microsoft SQL Server database known as AdventureWorks.
- Created an Azure SQL Database, which served as the target for migrating our on-premise database. We ensured that the associated SQL Server uses SQL login as the chosen authentication method. Additionally, we confirmed that the SQL Server has the appropriate firewall rules, specifically with our IP address added to the firewall settings.
- We installed and configured Azure Data Studio on the production Windows VM. We then established a connection to the existing on-premise database.
- Using Azure Data Studio, we established a connection to the newly created Azure SQL Database. This connection served as the conduit for schema and data migration between the two databases.
- After establishing connections to both databases, we installed the SQL Server Schema Compare extension within Azure Data Studio. Then used this extension to compare and subsequently migrate the schema from the on-premise database to the Azure SQL Database.
- For data migration phase, we installed the Azure SQL Migration extension within Azure Data Studio. We also had to install integration runtime. This facilitated the smooth transfer of data from our on-premise database to the Azure SQL Database.
- To confirm the success of the database migration process, we carried out a comprehensive validation by inspecting the data, schema, and any configurations of the migrated database, ensuring that the migration has been executed successfully and adheres to principles of data integrity.
- Generated a full backup of the On-Premise production database hosted on the Windows VM. This backup duplicates the database, providing a safety net in the event of unforeseen issues. The resultant backup file was stored in a designated location on the on premise computer.
- Azure Blob Storage account was created to serve as a secure online repository for your database backups. The backup file was uploaded to the Blob Storage container. This provided an extra layer of backup protection by making a redundant copy stored remotely.
- A development environment was created by provisioning a new Windows VM that mirrors the production environment including installing the releveant Install SQL Server and software on this VM to mimic the necessary database infrastructure. The databse backup was restored into this environment. The development environemnt can be used as a controlled and isolated environment where applications and software can be tested, developed, and experimented with, all without impacting the production systems.
- On your development Windows VM, SSMS was used to establish a management task that automates regular backups of the development database. The maintenance plan was configured for automated weekly backup schedule to ensure consistent protection for the evolving work and to simplify recovery for the development environment.
- In the production database we mimicked data loss. We deliberately removed critical data from your production database to replicate a scenario where data integrity is compromised. We confirmed its success by examining the Azure SQL Database using the connection already established in Azure Data Studio. Before the data loss, the SQL query was carried out: SELECT * FROM Person.EmailAddress. The results were 19972 entries. For data loss, the intention deletion SQL query was carried out: DELETE TOP (100) FROM Person.EmailAddress. To confirm the success of the deletion, the SQL query was repeated: SELECT * FROM Person.EmailAddress. The results were 19872 entries, which is 100 less than the original production database.
- We used Azure SQL Database Backup to restore the production database to a point just before the simulated data loss occurred, approximately 2 hours before. The success of the restored data was validated by examining the restored data through the connection in Azure Data Studio using the SQL query previously used to check that the entries were 19972.



# File structure of the project
- README.md file contains all the updates

# License information
- Non required. Public repository.
