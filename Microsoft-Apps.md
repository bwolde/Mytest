**WPF app**

The WPF app is the receptionist app, which allows the receptionist to see patients' data, upcoming appointments, and create new appointments. The WPF app code is in [src\MyHealth.Client.Desktop] (https://github.com/Microsoft/HealthClinic.biz/tree/master/src/MyHealth.Client.Desktop). The WPF application shares code with the UWP app; the shared code is a portable library [MyHealth.Client.Core] (https://github.com/Microsoft/HealthClinic.biz/tree/master/src). 

Both WPF and the UWP get the data from the database in Azure, using the web app; the ServerUrl in file [src\MyHealth.Client.Core\AppSettings.cs] (https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Core/AppSettings.cs) needs to be set to the value of your URL. For testing, the WPF application can get the data locally.

1. To get data from the database that is created locally: run the ASP.NET application in localhost (see the instructions above for running the web site). Set the ServerUrl value in AppSettings.cs to the local host.  
Example: 
```csharp
 public static string ServerlUrl = "http://localhost:34393/";
```
Leave the ASP.NET application running, then on the same machine run the WPF application: open solution 02_Demos_NativeMicrosoftApps. Set MyHealth.Client.Desktop as startup project the run the application.

2. To use the database from Azure: deploy the Web application to Azure (see instructions above for running the website) then set the ServerUrl value to your website URL.

**UWP app**

The UWP app is the patient app, which lets the user see their data: appointments, medication schedule, and allows creating new appointments. To run the UWP app: open solution 02_Demos_NativeMicrosoftApps in Visual Studio, set MyHealth.Client.W10.UWP as startup project and run. The ServerUrl string  in file [src\MyHealth.Client.Core\AppSettings.cs] (https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Core/AppSettings.cs) needs to be set to the right value, in the same way as described for the WPF app. For the Patient app, the server URL can also be set directly in the application: after the application starts, go to Settings > Server Address.
