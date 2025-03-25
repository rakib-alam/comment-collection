# comment-collection
from selenium import webdriver
from selenium.webdriver.common.by import By
import time
driver= webdriver.Chrome()
driver.get('https://www.daraz.com.bd/products/2023-i465829987-s2238309140.html')

#print(comment)
# Get the scroll height
scroll_height = driver.execute_script('return document.body.scrollHeight')
print(scroll_height)
driver.refresh()
for i in range(0,scroll_height+800,50):
    driver.execute_script(f'window.scrollTo(0,{i});')
    time.sleep(0.4)
##comment collection
comment=driver.find_elements(By.CLASS_NAME,'content')
for i in comment:
    print(i.text)


print(comment)
time.sleep(40)
driver.quit()


