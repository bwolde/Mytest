1. Start Visual Studio as Administrator, then open 10_Demos_Deployment.sln solution.  Note: if you get an error saying that Visual Studio cannot open that type of project, make sure [Microsoft Azure SDK](https://azure.microsoft.com/en-us/downloads/) is installed.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image1.png)

2. Right click on MyHealth project. Click on Deploy>New Deployment. 
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image2.png) 

3. You will be prompted to connect to your Azure Subscription.  
4. Create a new Resource Group to contain all the backend services. The name must be unique in the selected subscription.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image4.png)

5. Click on “Deploy” (make sure Visual Studio runs as administrator, otherwise the deploy script will fail).
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image5.png) 

6. After completing the task, all the resources will be created inside the selected Resource Group. Sign in into the [Azure Portal](https://ms.portal.azure.com/), click on "Resource Groups", click on the Resource Group that was just created. Under "Summary", you will see all the resources created.    
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image6.png)

7. Open the 01_Demos_ASPNET5.sln solution to deploy the backend services.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image7.png)

8. In the appsettings.json files it´s possible to change the default credentials that are needed to connect to the private web site.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image8.png)

9. Make sure packages for the solution are restored, and that MyHealth.Web project builds successfully. Select MyHealth.Web project and click on “publish”. Select "Microsoft Azure App Service" as publish target. 
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image9.png)

10. Select the right Azure Subscription and navigate to the Azure WebApp created in the first steps. Select the website.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image10.png)

11. Click on “Ok”.  
12. In the Settings page, set the right DNX version: rc1-update1. 
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image12.png)
 
13. Click on “Publish”.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image13.png)

14. After completing the deployment a new browser will be opened with the HealthClinic WebSite.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image14.png)

15. Click on “private area” and use the credentials stored in the settings file to access to this area.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image15.png)

16. Open the 06_Demos_MobileApp.sln solution to deploy the MobileApp backend.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image16.png)

17. Click on “Publish” and choose the mobileapp service.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image17.png)  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image17b.png)

18. Click on “Publish”. A new browser will be opened after completing the deployment.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Deployment/image18.png)

19. Now that the entire backend was deployed, the URL's of the services created must be used in the client apps. In file [src\MyHealth.Client.Core\AppSettings.cs] (https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Core/AppSettings.cs), set "ServerlUrl" to the website URL, and "MobileAPIUrl" to the mobile app URL.
