# Assignment

package files;

import java.util.concurrent.TimeUnit;
import javax.lang.model.element.Element;
import java.io.File;
import java.io.IOException;
import java.text.SimpleDateFormat;
import java.time.Duration;
import java.time.temporal.ChronoUnit;
import java.util.Date;
import java.util.Iterator;
import java.util.Random;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.testng.Assert;
import org.testng.ITestResult;
import org.testng.Reporter;
import org.testng.annotations.Test;
import java1.FixMethodOrder;
import org.openqa.selenium.By;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class calling{
	boolean role=false;
	int count=0;
	boolean country=false;

	
public static <JSONObject> void main(String[] args) throws InterruptedException { 	
		System.setProperty("webdriver.chrome.driver","D:\\chromedriver.exe");
		WebDriver driver=new ChromeDriver();  
     driver.get("https://gist.github.com/kumarpani/1e759f27ae302be92ad51ec09955e765");    
       driver.manage().window().maximize(); 
       new WebDriverWait(driver, Duration.of(30,ChronoUnit.SECONDS)).until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//a[contains(text(),'Raw')]")));
       driver.findElement(By.xpath("//a[contains(text(),'Raw')]")).click();
       new WebDriverWait(driver, Duration.of(30,ChronoUnit.SECONDS)).until(ExpectedConditions.visibilityOfElementLocated(By.tagName("pre")));
       String jsonData=driver.findElement(By.tagName("pre")).getText();
       Thread.sleep(3000);
       
}
       
       @Test
   	public void test1Players() {
    	   JSONObject jsonObject=new JSONObject(jsonData);
    	   String country = (String)jsonObject.get("country");
           Iterator iterator = country.iterator();
           while(iterator.hasNext()) { 
           try {
        	   if(!country.equalsIgnoreCase("India")){	  
                   count++;
                   }
           if(count==4) { 
    		System.out.println("team has only 4 foreign players");
           }} catch (InterruptedException e) {
        	   System.out.println("Test Failed");
           }
           assert(true);
         
           }}
   	
           @Test
          	public void test2role() {
                  String role = (String)jsonObject.get("role");
                  Iterator iterator = role.iterator();
                  while(iterator.hasNext()) { 
                	  try {
        	if(role=="Wicket-keeper") {
	    		System.out.println("there is at least one wicket keeper");
        	}} catch (InterruptedException e) {
        		 System.out.println("Test Failed");
	          }
                	  assert(true); 
                	  }
                  }
           }
