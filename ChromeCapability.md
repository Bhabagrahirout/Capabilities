# Chrome Capabilities

** Official Link **
[Capability](https://developer.chrome.com/docs/chromedriver/capabilities)

*   ChromeOptions class  implements the Capabilities interface, allowing you to specify other 	    WebDriver capabilities not only ChromeDriver. *


	ChromeOptions op=new ChromeOptions();

 *		We can add proxy   
  		Proxy proxy = new Proxy();
		proxy.setHttpProxy("myhttpproxy:3337");
		op.setCapability("proxy", proxy);
		
		
	      
*	   Size   
	   op.addArguments("start-maximized");
	   op.addArguments("window-size=1366,768");//default
	   op.addArguments("window-size=1280,720");
	   op.addArguments("window-size=1024,768");
	   op.addArguments("window-size=800,600");
	   if you give all the sizes it take the 1st one 
		
		
*		window position
		op.addArguments("--window-position=100,100"); //left and top
		op.addArguments("--window-position=-100,-200");// right and buttom
				
*		incognito
		op.addArguments("incognito");
		
		
*		headless
		op.addArguments("headless");
	    headless platform phantomjs,zombie.js but  after chrome added this featurs they are not used.
		
		 
*	    add extension
		First add  crx extractor extension to chrome , which enables to download extensions in .crx format.
		op.addExtensions(new File("/home/apmosys/Videos/Dark-Reader.crx"));
 		We can block ads from a website  by using extensions like UBlockOrigin, AdBlocks etc
	
		
		
*		diseable
		op.addArguments("--disable-extensions");
		op.addArguments("--disable-popup-blocking");
		op.addArguments("--disable-notifications");
		op.addArguments("--ignore-certificate-errors");
		op.addArguments("--disable-translate");
		op.addArguments("--disable-infobars"); Disable "Chrome is being controlled by automated test software"  
		op.addArguments("--disable-dev-shm-usage"); Overcome limited resource problems in Docker containers
		
	
*		enable
		op.addArguments("--enable-javascript");
		op.addArguments("--enable-tab-audio-muting");
		op.addArguments("--enable-notifications");
		op.addArguments("--allow-http-screen-capture");// that allow capture screenshot in site
		op.addArguments("--remote-allow-origins=*");
	
*		version
		op.addArguments("--version");
	
		
*		remove chrome is automated
        op.setExperimentalOption("excludeSwitches", new String[]{"enable-automation"}); 
        it remove the text that shows chrome is being  controlled by automated test s/w
        
		
  ***    Using preference add all  preferences at a time  ***
    
  *      String downloadFilepath = "/home/Videos";
         HashMap<String, Object> prefs = new HashMap<>();
        
  *     prefs.put("profile.default_content_settings.popups", 0);  for enable 1
        prefs.put("download.default_directory", downloadFilepath);
        prefs.put("geolocation", true);
        prefs.put("media_stream", true);
        websites that require access to the webcam and microphone for features like   
		video conferencing, live streaming, audio recording 
      
  *     prefs.put("profile.default_content_setting_values.notifications", 2); for  1 Allow
        prefs.put("profile.block_third_party_cookies", true);
        prefs.put("profile.default_content_setting_values.automatic_downloads", 2); for  1 Allow
        prefs.put("profile.managed_default_content_settings.images", 2);  for 1 enable images
        

  *     op.setExperimentalOption("prefs", prefs);
		//More are available
        
		
   ** Preferences: use in chromeoptions **    

*    -Preferences are settings that customize the browser's behavior and are specific to the Chrome browser and can be set using ChromeOptions.  
	 -Preferences are typically used to configure options such as default download Filepath directory, disabling   pop-up blocking, setting browser language, etc.   
  	  
	 -Examples   
		download.default_directory, profile.default_content_settings.popups, intl.accept_languages,  
	     etc.   
      Preferences are set using the setExperimentalOption() or addArguments() method in ChromeOptions.
         
	
    		
  
