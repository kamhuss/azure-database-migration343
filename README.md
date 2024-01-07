# Azure database migration Project
- This is my third project in the AiCore course
- In this project, we established a production environment database, then migrated the database to Azure SQL Database, focusing on crucial aspects like data backup, restoration, and automated scheduling.
- A pivotal phase of the project involved simulating a disaster recovery scenario with potential data loss. Furthermore, we explored the complexities of geo-replication and failover configuration to ensure data availability even under challenging conditions.
- To enhance security, Microsoft Entra ID integration was employed to define access roles, adding an extra layer of control and protection.

# Installation instructions
- Azure portal, Microsoft Remote Desktop, SQL Server, SQL Server Management Studio (SSMS), Azure Data Studio

# Tasks completed
- Used AiCore provided subcription, created a Virtual Machine (VM) on Azure portal.
- Used the RDP protocol and Microsoft Remote Desktop to establish a secure connection to the VM.
- Installed SQL Server and SQL Server Management Studio (SSMS) on the VM.
- Created the production database by restoring it from provided backup file. The backup file corresponds to the renowned Microsoft SQL Server database known as AdventureWorks.
- Created an Azure SQL Database, which served as the target for migrating our on-premise database. We ensured that the associated SQL Server uses SQL login as the chosen authentication method. Additionally, we confirmed that the SQL Server has the appropriate firewall rules, specifically with our IP address added to the firewall settings.
- We installed and configure Azure Data Studio on your production Windows VM. We then established a connection to the existing on-premise database.
- Using Azure Data Studio, we established a connection to the newly created Azure SQL Database. This connection served as the conduit for schema and data migration between the two databases.
- After establishing connections to both databases, we installed the SQL Server Schema Compare extension within Azure Data Studio. Then used this extension to compare and subsequently migrate the schema from the on-premise database to the Azure SQL Database.
- For data migration phase, we installed the Azure SQL Migration extension within Azure Data Studio. This facilitated the smooth transfer of data from our on-premise database to the Azure SQL Database.
- To confirm the success of the database migration process, we carried out a comprehensive validation by inspecting the data, schema, and any configurations of the migrated database, ensuring that the migration has been executed successfully and adheres to principles of data integrity.

# File structure of the project
- README.md file contains all the updates

# License information
- Non required. Public repository.
