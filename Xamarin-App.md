
**iOS Xamarin app**

A Xamarin license is needed. You will be prompted to sign-in with the Xamarin account within Visual Studio when creating or loading Xamarin projects. For building the iOS app, you need a Mac with OSX Yosemite (10.10.5) or above, with XCode and Xamarin installed. See instructions for setting up your Mac at http://developer.xamarin.com/guides/ios/getting_started/. 

Visual Studio needs to have the Cross-Platform tools installed: within the Visual Studio installer, select a Custom install and check the box _Cross-Platform Mobile Development_ > _C#/.NET (Xamarin)_. 

Open solution 04_Demos_NativeXamarinApps in Visual Studio. Log into Xamarin account if prompted. Make sure your Mac is available on the network and [paired](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac) with Visual Studio. If the pairing menu does not automatically appear, in Visual Studio go to _Tools_ > _Options_ > _Xamarin_ > _iOS Settings_ > _Find Xamarin Mac Agent_, and connect with your Mac. 

Set MyHealth.Client.iOS as startup project. Set Configuration to iPhoneSimulator, build and run. The application will start in the Simulator on the Mac. To get data, the ServerUrl string  in file [src\MyHealth.Client.Core\AppSettings.cs] (https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Core/AppSettings.cs) needs to be set to the address where the web app was deployed.

**Android Xamarin app**

Open solution 04_Demos_NativeXamarinApps in Visual Studio. Set MyHealth.Client.Droid as startup project. Set "VS Emulator" in the run configuration. To get data, the ServerUrl string  in file [src\MyHealth.Client.Core\AppSettings.cs] (https://github.com/Microsoft/HealthClinic.biz/blob/master/src/MyHealth.Client.Core/AppSettings.cs) needs to be set to the address where the web app was deployed.
