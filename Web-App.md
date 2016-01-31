**Public and private websites:**

Open solution 01_Demos_ASPNET5. Set MyHealth.Web project as startup project and run. The application will start running locally on IISExpress.
The private website requires credentials for access; the default username and password can be viewed or changed in [src\MyHealth.Web\appsettings.json](https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Web/appsettings.json).

If you have an Azure account you can publish the web app to the cloud. Right-click on MyHealth.Web project, select Publish. Choose "Microsoft Azure Web Apps" as a publish target. Enter your credentials to connect to your Azure account and select the subscription to use. Select New web app. Create a new AppService plan, ResourceGroup and Database server if needed. Click "Publish" button.

The private website is set to use the local database in appsettings.json. To change it to use the database in Azure, replace this part of the connection string: 

```
Server=(localdb)\\mssqllocaldb;Database=MyHealth;
```
with your database in Azure: 
 
```
Server=<your db server>.database.windows.net;Database=<db name>;User Id=<user id>;Password=<your password>;
```

You can use SQL Server 2014 Management Studio to examine the database you have created, see the following [instructions] (https://azure.microsoft.com/en-us/documentation/articles/sql-database-manage-azure-ssms/).