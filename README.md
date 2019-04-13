# Rohan-Nikhil
package package1;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.By.ById;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;

public class Spicejet {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		WebDriver driver = new FirefoxDriver();
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
		driver.get("https://www.spicejet.com");

    driver.findElement(By.id("ctl00_mainContent_rbtnl_Trip_1")).click();
	driver.findElement(By.id("ctl00_mainContent_ddl_originStation1_CTXTaction")).click();
	driver.findElement(By.linkText("Gorakhpur (GOP)")).click();
	
	driver.findElement(By.id("ctl00_mainContent_ddl_destinationStation1_CTXTaction")).click();
	driver.findElement(By.linkText("Goa (GOI)")).click();
	
	Actions act = new Actions(driver);
	driver.findElement(By.id("ctl00_mainContent_view_date1")).click();
	act.moveToElement(driver.findElement(By.linkText("18"))).build().perform();
	driver.findElement(By.linkText("18")).click();
	driver.findElement(By.id("ctl00_mainContent_view_date2")).click();
	act.moveToElement(driver.findElement(By.linkText("20"))).build().perform();
	driver.findElement(By.linkText("20")).click();
	driver.findElement(By.id("divpaxinfo")).click();
	driver.findElement(By.id("hrefIncChd")).click();
	driver.findElement(By.id("hrefIncInf")).click();
	driver.findElement(By.id("btnclosepaxoption")).click();
	Select sc = new Select(driver.findElement(By.id("ctl00_mainContent_DropDownListCurrency")));
	sc.selectByValue("USD");
	driver.findElement(By.id("ctl00_mainContent_btn_FindFlights")).click();
	}

}
