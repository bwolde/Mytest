**Cordova app**

The "Doctor" mobile app is written using Visual Studio Tools for Apache Cordova. The same code runs on Android devices, Windows Phone and iPhone.   

Open solution 05_Demos_Cordova in Visual Studio. If the "Dependencies" folder in Solution Explorer shows "Not installed", right click on Dependencies > Restore Packages.  

Run the default Gulp task: open the Task Runner Explorer window in Visual Studio, and you will see the list of tasks.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Cordova/defaulttask.png)  

Right-click the "default" task then click on "Run". Build the solution.  

The "API_URL" and "GATEWAY_URL" values in file [src\MyHealth.Client.Cordova\content\app\modules\shared\services\configService.ts](https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Cordova/content/app/modules/shared/services/configService.ts) need to be set to the URL's obtained from deploying the Azure mobile app service (see the [Deployment](https://github.com/Microsoft/HealthClinic.biz/wiki/Deployment) section).  

The Doctor app uses Bing Maps API's. In order to get this part of the application working, you must [get a Bing Maps key](https://msdn.microsoft.com/en-us/library/ff428642.aspx), which needs to be added in file [src\MyHealth.Client.Cordova\content\app\modules\shared\services\configService.ts](https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Cordova/content/app/modules/shared/services/configService.ts). 

To run the Cordova application on Android emulator: set "Solution Platform" to Android, then choose VS Emulator.  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Cordova/androidemulator.png)

To run on Windows Phone emulator, set "Solution Platform" to Windows Phone, then choose "Mobile Emulator".  
![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Cordova/windowsphoneemulator.png)  

The application will look like below:  
![![](https://github.com/alinapopa/Images/blob/master/HealthClinicWiki/Cordova/wp.png)  

To be able to build the Cordova app for iOS, the Mac needs to have Node.js, XCode and the VS Remote Agent installed. Visual Studio connects to the remote agent running on the Mac to build the application. Detailed step-by-step instructions for setting up and running the VS Remote Agent are at https://taco.visualstudio.com/en-us/docs/ios-guide/. 

