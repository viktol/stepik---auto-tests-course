# stepik---auto-tests-course
from selenium import webdriver
import time
import math 

def calc(x):
    return str(math.log(abs(12*math.sin(int(x)))))

try: 
    link = "http://suninjuly.github.io/alert_accept.html"
    browser = webdriver.Chrome()
    browser.get(link)
    
    input1 = browser.find_element_by_tag_name("body > form > div > div > button")
    input1.click()

    alert = browser.switch_to.alert
    alert.accept()
    
    element = browser.find_element_by_xpath("//*[@id='input_value']")
    x = element.text
    y = calc(x)
    
    
    input2 = browser.find_element_by_tag_name("#answer")
    input2.send_keys(y)
    
    
    button = browser.find_element_by_tag_name("body > form > div > div > button")
    button.click()
    
    
    time.sleep(1)

finally:
    
    time.sleep(10)
   
    browser.quit()
