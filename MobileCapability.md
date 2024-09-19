# Mobile Capabilities

*		DesiredCapabilities cap = new DesiredCapabilities();
		cap.setCapability("platformName", "Android");
		cap.setCapability("deviceName","Give a specific name to identify");
		cap.setCapability("platformVersion", "vesion");
		cap.setCapability("noReset", true);  
		cap.setCapability("fastReset", true);
		cap.setCapability("newCommandTimeout", 2000);
		cap.setCapability("udid", "42006409e0c6253b");
		cap.setCapability ("acceptInsecureCerts", true);
		cap.setCapability("automationName", "uiautomator2");
		cap.setCapability("appPackage", "com.android.chrome");
	    cap.setCapability("appActivity","com.google.android.apps.chrome.Main");
		or 
		cap.setCapability("browserName", "Chrome"); The appium will know to start which browser we don’t need app package and app activity.

	
	noRest=true --->The app will keep its data and not be reinstalled and not be relaunched 		       from scratch.	  
	noRest=false--->IN Android : The app will start as if it was freshly installed, 				     but it is not reinstalled.   
     \t            IN Ios    : The app is removed and reinstalled, which results 					in a completely clean state.  
	fastReset=true-->Appium will reset the app by clearing the app data, but without   		     uninstalling and reinstalling the app   
	fastRest=false-->Appium will uninstall and then reinstall the app.It takes 				longer because of the uninstall/reinstall process.  
	 As per requirment use one of them.
	

 	Also we can use all this in MobileCapability i.e  Appium Java client   
*		cap.setCapability(MobileCapabilityType.PLATFORM_NAME, "Android");
		cap.setCapability(MobileCapabilityType.PLATFORM_VERSION, "14");
		cap.setCapability(MobileCapabilityType.NO_RESET, "true");
		cap.setCapability(MobileCapabilityType.NEW_COMMAND_TIMEOUT, "2000");
		cap.setCapability(MobileCapabilityType.UDID, "42006409e0c6253b");  
		cap.setCapability(MobileCababilityType.APP_ACTIVITY,"com.google.android.chrome.Main")
		 
 	In some case Mobilecapabitype apppackage and activity not work so add in generaly.
*	cap.setCapability("apmosys.user", "lighthouse.apmosys.com");
	cap.setCapability("apmosys.accessToken",
	"25f41fbcf95442feb08be69c486e3da03b9c9c1bbf154ab9bca4a4e16453e445");


 	Add user capability that are validate by the url that are design in such way in server side .
*	URL url = new URL("https://lighthouseprotean.apmosys.com/wd/hub");

	AppiumDriver<WebElement> driver=new AndroidDriver<>(url,cap);