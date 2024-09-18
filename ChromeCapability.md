# Capabilities

[Capability](https://github.com/)



//    ChromeOptions class  implements the Capabilities interface, allowing you to specify other 	   WebDriver capabilities not only ChromeDriver.





//		ChromeOptions op=new ChromeOptions();
	      
	    // we can add proxy 

		Proxy proxy = new Proxy();
		proxy.setHttpProxy("myhttpproxy:3337");
		op.setCapability("proxy", proxy);

		// Add a ChromeDriver-specific capability.
		op.addExtensions(new File("/path/to/extension.crx"));
	      
	     
	      
		//size
		op.addArguments("start-maximized");
/*		op.addArguments("window-size=1366,768");//default
		op.addArguments("window-size=1280,720");
		op.addArguments("window-size=1024,768");
		op.addArguments("window-size=800,600");
*/
//		if you give all the size it take the 1st one
		
		
		//window position
//		op.addArguments("--window-position=100,100"); //left and top
//		op.addArguments("--window-position=-100,-200");// right and buttom
				
		//incognito
//		op.addArguments("incognito");
		
		
		//headless
//		op.addArguments("headless");
		// headless platform phantomjs,zombie.js but  after chrome added this featurs they are not used.
		
		 
		// add extension
//		the extension are not auto add still you are using
//		op.addExtensions(new File("/home/apmosys/Videos/Dark-Reader.crx"));
//		op.addArguments("load-extension="+" extensionId);
		
		
/*		//diseable
		op.addArguments("--disable-extensions");
		op.addArguments("--disable-popup-blocking");
		op.addArguments("--disable-notifications");
		op.addArguments("--ignore-certificate-errors");
		op.addArguments("--disable-translate");
	
		//enable
		op.addArguments("--enable-javascript");
		op.addArguments("--enable-tab-audio-muting");
		op.addArguments("--enable-notifications");
		op.addArguments("--allow-http-screen-capture");// that allow capture screen shot in site
*/	
		
		//remove chrome is automated
//        op.setExperimentalOption("excludeSwitches", new String[]{"enable-automation"}); 
//        it remove the text that showing chrome is being  controled by automated test s/w
        
		
        //using preference add all  preferences at a time
        String downloadFilepath = "/home/apmosys/Videos";
        HashMap<String, Object> prefs = new HashMap<>();
        
        prefs.put("profile.default_content_settings.popups", 0); //for enable 1
        prefs.put("download.default_directory", downloadFilepath);
        prefs.put("geolocation", true);
        prefs.put("media_stream", true);
        //websites that require access to the webcam and microphone for features like video conferencing, live streaming, audio recording 
      
        prefs.put("profile.default_content_setting_values.notifications", 2); //for  1 Allow
        prefs.put("profile.block_third_party_cookies", true);
        prefs.put("profile.default_content_setting_values.automatic_downloads", 2); //for  1 Allow
        prefs.put("profile.managed_default_content_settings.images", 2); // for 1 enable images
        

        op.setExperimentalOption("prefs", prefs);
        op.setExperimentalOption("excludeSwitches", new String[]{"enable-automation"});
		// more are available
        
		WebDriver wd=new ChromeDriver();
		
		
		//***// version
		op.addArguments("--version");
	
		wd.get("https://en.wikipedia.org/wiki/Cricket");
//		wd.get("https://www.flipkart.com/");
//		wd.get("https://meet.google.com/");
//		wd.get("https://zoom.us/join");
//		wd.findElement(By.xpath("//*[@id=\"join-confno\"]")).sendKeys("83132097317");
//		wd.findElement(By.xpath("//*[@id=\"btnSubmit\"]")).click();
//		wd.get("https://www.youtube.com/");
		
		wd.manage().timeouts().implicitlyWait(Duration.ofSeconds(20));
		
		
		System.out.println("complete");
	}
}
/*
Preferences: use in chromeoptions
    -Preferences are settings that customize the behavior of the browser.
    -They are specific to the Chrome browser and can be set using ChromeOptions.
    -Preferences are typically used to configure options such as default download directory, disabling pop-up blocking, setting browser language, etc.
    -Examples 
    		download.default_directory, profile.default_content_settings.popups, intl.accept_languages, etc.
    Preferences are set using the setExperimentalOption() or addArguments() method in ChromeOptions.

Capabilities:use in desirecapability
    -Capabilities are a set of key-value pairs that define the characteristics and features of the WebDriver session.
    -They are not specific to a particular browser and can be used with any WebDriver implementation (ChromeDriver, FirefoxDriver, etc.).
    -Capabilities are used to specify options such as browser name, version, platform, proxy settings, logging preferences, etc.
    - Examples 
    		 browserName, version, platform, proxy, goog:loggingPrefs, etc.
    Capabilities are set using the setCapability() method in DesiredCapabilities or directly in ChromeOptions for Chrome-specific capabilities.
*/
