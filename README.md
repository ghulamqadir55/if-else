       import io.appium.java_client.android.AndroidDriver;
       import io.appium.java_client.remote.MobileCapabilityType;
       import org.openqa.selenium.By;
       import org.openqa.selenium.remote.DesiredCapabilities;

       import java.net.MalformedURLException;
       import java.net.URL;

       class AppiumDemo {

       public static void main(String[] args) throws MalformedURLException, InterruptedException {

        DesiredCapabilities dc = new DesiredCapabilities();
        dc.setCapability(MobileCapabilityType.DEVICE_NAME, "f401a4a5");          // Add Your Device
        dc.setCapability("appPackage", "com.google.android.calculator");
        dc.setCapability("appActivity", "com.android.calculator2.Calculator");
        URL url = new URL("http://127.0.0.1:4723/wd/hub");
        AndroidDriver driver = new AndroidDriver(url, dc);

        driver.findElement(By.id("com.google.android.calculator:id/digit_5")).click();
        driver.findElement(By.id("com.google.android.calculator:id/op_add")).click();
        driver.findElement(By.id("com.google.android.calculator:id/digit_5")).click();
        driver.findElement(By.id("com.google.android.calculator:id/eq")).click();
        String Result = driver.findElement(By.id("com.google.android.calculator:id/result_final")).getText();

        System.out.println(Result);
        if (Result.equals("10")) {
            System.out.println("Pass");
        } else {
            System.out.println("Failed");
        }


        Thread.sleep(10000);
        driver.quit();
       }
      }

