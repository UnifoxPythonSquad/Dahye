 # BeautifulSoup이란?
 <정의>BeautifulSoup 모듈은 HTML과 XML을 파싱(기계어로 번역)하는 데에 사용되는 파이썬 라이브러리이다.<br><br>
 
 ## BeautifulSoup 사용법
 ##### 다운로드방법
 1. window+R키를 이용하여, PowerShell을 연다.
 2. 'pip3 install beautifulsoup4'를 입력한다. 이 명령어는 beautifulsoup4를 다운하는 명령어이다.
 3. 가능하다면 다운로드 후, 파이썬을 킨 뒤,<br> 'from bs4 import BeautifulSoup'를 입력하여 에러가 발생하지 않는지 확인한다.
 4. 에러가 발생하지 않는다면 다운에 성공한 것이다.
 <br><br><br>
 
 ##### 사용방법
 ~~위에서 사용한 명령어 'from bs4 import BeautifulSoup'은  beautifulsoup모듈 사용시 반드시 써줘야한다.<br>
 c언어에서의 헤더파일과 비슷한 역할을 한다.~~ <br>
 <br>
 
 ###### - 파싱할문서를 BeautifulSoup클래스의 생성자에게 넘겨 개체를 생성함(=soup)
     1  from bs4 import BeautifulSoup
     2  
     3  soup = BeautifulSoup(open("index.html"))
 <br>
 
 ###### - 본격적인 사용
 ~~lxml은 'pip3 install lxml'로 다운할 수 있다.~~<br>
 lxml을 다운 후, 본격적으로 사용한다.
 
     1  from bs4 import BeautifulSoup
     2  
     3  soup1 = BeautifulSoup(open("index.html"),"lxml")
     4  soup2 = BeautifulSoup("<html>data</html>")
   
   <br><br>
   또는, urllib 또는 Requests 모듈을 함께 사용하여 특정한 url을 주어준 후 그 url의 HTML을 파싱할 수도 있다.
   <br>
    
    
    
     1  import requests
     2  from bs4 import BeautifullSoup
     3  
     4  r = requests.get("http://www.naver.com")
     5  r.encoding = "utf-8"
     6  soup = BeautifulSoup(r.text)
     7  postTitles = soup.find_all(class_="entry-title")
     8
     9  for postTitle in postTitles:
     10   print(postTitle.text)
     
   <br><br>
   또는, find와 find_all 메쏘드를 사용하여 HTML에서 원하는 내용을 탐색하면 된다.
   <br>
   
     1  import requests
     2  from bs4 import BeautifulSoup
     3 
     4  r = requests.get("http://www.naver.com")
     5  r.encoding = "utf-8"
     6  soup = BeautifulSoup(r.text)
     7  postTitles = soup.find_all(class_="ah_k")
     8
     9  for postTitle in postTitles:
    10     print(postTitle.text)
   <br>
  위의 예제를 실행하게되면 다음과같은 결과가 나온다.
  https://www.naver.com HTML에서 "ah_k"라는 클래스에 해당되는 텍스트요소가 출력된 것이다.
 
  
      윤서인
      위수령
      라이프
      장현수
      ...
