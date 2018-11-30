import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.Test;

import static com.codeborne.selenide.Selenide.switchTo;

public class test {
    @Test // Marking this method as part of the test
    public void SiteyeGir() {
        System.setProperty("webdriver.chrome.driver", "C:\\SeleniumDrivers\\chromedriver.exe");

        WebDriver driver = new ChromeDriver();
        driver.get("http://94.55.114.18:8889/edys-web/sistemeGiris.xhtml");
        driver.manage().window().maximize();
        driver.findElement(By.id("eForm:txtEKullaniciAdi")).sendKeys("ts0104");
        driver.findElement(By.id("eForm:loginESifre")).sendKeys("123");
        driver.findElement(By.id("eForm:egirisYapButton")).click();
        driver.findElement(By.xpath("//*[@id=\"leftMenuForm:edysMenuItem_1989401481\"]/span")).click();
        driver.findElement(By.xpath("//*[@id=\"mainInboxForm:inboxDataTable:0:degistirilmemisVersiyonlariSorgulaButton\"]/span[1]")).click();
        driver.findElement(By.xpath("//*[@id=\"mainInboxForm:inboxDataTable:j_idt715\"]")).click();
        driver.findElement(By.xpath("//*[@id=\"mainInboxForm:inboxDataTable:j_idt681\"]/span[1]")).click();

        switchTo().window(1);
        String pageSource = driver.getPageSource();
        System.out.println(pageSource);

    }
}
