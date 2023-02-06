# jenkins1
TANIM
package project1;

import io.github.bonigarcia.wdm.WebDriverManager;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.time.Duration;

public class facebookgiris {

    public static void main(String[] args) {

        WebDriverManager.chromedriver().setup();
        WebDriver driver = new ChromeDriver();
        driver.manage().window().maximize();
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(15));

        driver.get("https://www.facebook.com");

        WebElement email = driver.findElement(By.xpath("//input[@id='email']"));
        email.sendKeys("hasan efe avc");

        WebElement password = driver.findElement(By.xpath("//input[@id='pass']"));
        password.sendKeys("123456789");

        driver.findElement(By.xpath("//button[@value='1']")).click();

        WebElement uyari = driver.findElement(By.xpath("//div[@class='_9ay7']"));

        String expectedsonuc="The email     address or mobile number you entered isn't connected to an account. Create a new Facebook account.";

        String actualsonuc= uyari.getText();

        if (expectedsonuc.equals(actualsonuc)){
            System.out.println("Giriş yaptık");
        }
        else {
            System.out.println("Giriş yapamadık");
        }


    }

}
