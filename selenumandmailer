import smtplib
from email.mime.text import MIMEText
from selenium import webdriver
import time
import sys


def sendMail(me, you, msg):
    smtp = smtplib.SMTP_SSL('smtp.gmail.com', 465)
    smtp.login(me, 'app-password-of-google-plz')
    msg = MIMEText(msg)
    msg['Subject'] = '제목 https://medium.com/@oneroot'
    smtp.sendmail(me, you, msg.as_string())
    smtp.quit()
    
while(1):

    options = webdriver.ChromeOptions()
    
    options.add_argument('headless')
    options.add_argument('window-size=1920x1080')
    options.add_argument("--disable-gpu")


    driver = webdriver.Chrome('chromedriver', options=options)
    
    driver.get("https://medium.com/@oneroot")

    p_element = driver.find_elements_by_tag_name("a")

    print(p_element[16].text[:2])

    file=open('RNT.txt','r')
    savedtxt=file.read()
    file.close()

    if p_element[15].text[:2] != savedtxt :
        print("다르다")
        sendMail('picaseo0316@gmail.com', 'bjkanggr@gmail.com', 'https://medium.com/@oneroot 내용')
        file=open('RNT.txt','w')
        file.write(p_element[15].text[:2])
        file.close()   
    else:
        print("같다")
    time.sleep(5) # 2초 대기
    driver.quit() # 브라우저 종료


#    smtp.login(me, 'app-password-of-google-plz')  여기만 수정하면된다.
