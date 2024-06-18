# I-have-written-scripts-but-it-is-not-connecting-to-virtual-and-real-devices-

package Daakia.test;

import java.net.MalformedURLException;
import java.net.URL;
import java.time.Duration;

import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;

import org.openqa.selenium.remote.DesiredCapabilities;

import io.appium.java_client.android.AndroidDriver;
import io.appium.java_client.android.options.UiAutomator2Options;

public class Basetest {
	protected AndroidDriver driver;
	
	@BeforeClass
	public void basetest() throws MalformedURLException
	{

		
		DesiredCapabilities capabilities = new DesiredCapabilities();
		capabilities.setCapability("platformName", "Android");
		capabilities.setCapability("deviceName", "darshan");
	
		capabilities.setCapability("automationName", "UiAutomator2");
		capabilities.setCapability("app", "C:\\Users\\Dashan K N\\eclipse-workspace\\test\\src\\test\\java\\Resources\\base.apk");
		
		
	
		

		
		try {
            driver = new AndroidDriver(new URL("http://127.0.0.1:4723/wd/hub"), capabilities);
        } catch (MalformedURLException e) {
            e.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
            throw new RuntimeException("Failed to create session", e);
        }
    }

    @AfterClass
    public void tearDown() {
        if (driver != null) {
            driver.quit();
        }
    }
    }
	
	
	
	
	
	
	
	
	
	
	


