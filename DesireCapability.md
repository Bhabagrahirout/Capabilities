# Desire Capabilities


	DesiredCapabilities cp = new DesiredCapabilities();
	cp.setCapability("browserName", "chrome");
	cp.setCapability("browserVersion", "latest");
	cp.setCapability("platformName", "Linux"); 
	cp.setCapability("acceptInsecureCerts", true);  // To handle SSL certificate errors
	cp.setCapability("goog:chromeOptions", chromeOptions);  // Chrome-specific options
	cp.setCapability("timeouts", "{\"implicit\": 10000, \"pageLoad\": 30000}");  // Timeout settings
	cp.setCapability("enableVNC", true);  // For enabling VNC if running tests on Selenium Grid
	cp.setCapability("enableVideo", true);  // To record the test session
	cp.setCapability("setWindowRect", true);  // Allow setting browser window size
	cp.setCapability("pageLoadStrategy", "eager");  // To control how the page loads
	
	
	 