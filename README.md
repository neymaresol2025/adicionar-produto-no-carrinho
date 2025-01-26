//# adicionar-produto-no-carrinho
//JavaScript

const { Builder, By, Key, until } = require('selenium-webdriver')
const { Builder, By, Key, until } = require('selenium-webdriver')
const assert = require('assert')

describe('Adicionar_produto_carrinho', function() {
  this.timeout(30000)
  let driver
  let vars
  beforeEach(async function() {
    driver = await new Builder().forBrowser('chrome').build()
    vars = {}
  })
  afterEach(async function() {
    await driver.quit();
  })
  it('Adicionar_produto_carrinho', async function() {
    await driver.get("https://advantageonlineshopping.com/#/")
    await driver.manage().window().setRect({ width: 1004, height: 708 })
    await driver.findElement(By.name("username")).sendKeys("Claudinei")
    await driver.findElement(By.name("password")).sendKeys("mANE@1980")
    await driver.findElement(By.id("speakersImg")).click()
    await driver.findElement(By.id("20")).click()
    await driver.findElement(By.css(".plus")).click()
    await driver.findElement(By.linkText("HOME")).click()
    {
      const element = await driver.findElement(By.linkText("HOME"))
      await driver.actions({ bridge: true }).moveToElement(element).perform()
    }
    await driver.findElement(By.id("miceImg")).click()
    await driver.findElement(By.id("29")).click()
    await driver.findElement(By.css(".plus")).click()
    await driver.findElement(By.css(".minus")).click()
    await driver.findElement(By.name("save_to_cart")).click()
    await driver.findElement(By.id("checkOutPopUp")).click()
    await driver.executeScript("window.scrollTo(0,0)")
    await driver.findElement(By.linkText("HOME")).click()
    await driver.findElement(By.id("speakersImg")).click()
    await driver.findElement(By.id("20")).click()
    await driver.findElement(By.name("save_to_cart")).click()
    await driver.findElement(By.id("checkOutPopUp")).click()
    await driver.findElement(By.linkText("HOME")).click()
  })
})
