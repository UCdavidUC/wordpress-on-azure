 # WordPress on Azure
 ## Scenario
 There are a couple of WordPress Web Application available in the Azure Marketplace, one is based on Windows OS and the other one in Linux.
 When creating deploying the template with the corresponding parameters the resource deploys correctly both the MySQL Database service (Azure Database for MySQL or MySQL in App) and the Application Insights service (if configured).
 At first the WordPress deployment seems right until you view the site:
 * It does not loads the .css files correctly.
 * It does not loads the fonts and other media resources.

 ## Workaround
 As a workaround there is a mechanism for deploying a WordPress instance in Azure Web Apps that work correctly for any version of WordPress:

 ### Prerequiites
 * Web App Service.
 * Azure Database for MySQL.
 * Application Insights (optional: if you requiere advanced application montitoring)

 ### Steps
 1. Create an Azure Database for MySQL.
 2. Configure a database user and password.
 3. Store database access strings.
 4. Create a database schema using the MySQL Workbech desktop application (or other query execution engine for MySQL).
 5. Save the database name.
 6. Create an Azure Web App Service based on Linux.
 7. Configure the Web App through SSH.
 8. Configure and install WordPress

 ### Step 1. Create an Azure Database for MySQL
 
 Go to the Microsoft Azure Portal and create a new service called "Azure Database for MySQL".