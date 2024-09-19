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
	
	
	If you want to work with Chrome, it's better to use ChromeOptions. However, if you're working with mobile browsers or devices, DesiredCapabilities is more appropriate."


##### why

 *   ChromeOptions: It's specifically designed to configure Chrome browser settings, and it is now the preferred approach when working with Chrome in modern Selenium versions.
 *   DesiredCapabilities: This is more commonly used when working with mobile browsers or when you need to set capabilities for different types of devices (e.g., Android or iOS) in mobile testing frameworks like Appium. It is still used for setting device-specific capabilities.

	