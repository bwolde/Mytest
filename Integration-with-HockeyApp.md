**Integration with HockeyApp**

The Xamarin.iOS application in the HealthClinic.biz sample uses the [HockeyApp SDK](http://hockeyapp.net/releases/) to report crashes and feedback. In file [src\MyHealth.Client.iOS\AppDelegate.cs](https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.iOS/AppDelegate.cs), check the method FinishedLaunching() to view the code that HockeyApp needs in the application to report crashes. Here is the place where it´s necessary to set the App ID of the application created in HockeyApp.  

To use this application with HockeyApp:  
* Create a HockeyApp account at http://hockeyapp.net, check the box "I'm a developer". 
* After creating the account, click on "New App" and you will be able to upload a build. 
* For the iOS application, you will need to create an .ipa package:
  + Open the Project Properties of the iOS project, select "iOS IPA Options" and select "Ad-Hoc" from the Configurations dropdown list. 
  + Check the box "Build Ad-Hoc IPA". 
  + Pair with the Mac and build the project. 
  + Look for the .ipa file in the Bin directory, and upload the file to the HockeyApp.  
* After uploading the file, you will see an app dashboard with all the information related to the application. In this page you can also get the App ID value. Copy the App ID and use it to set HockeyAppiOSAppID in file [src\MyHealth.Client.Core\AppSettings.cs](https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Core/AppSettings.cs). 
* Build again the iOS project and upload the new ipa file to HockeyApp.

