# glob
</br>

* glob 사용방법

       import glob
       for filename in glob.glob('*.파일형식'):
          print(filename)
        
  위의 예제는 __현재 디렉토리에서 확장자가 '.파일형식'인 파일만 모아서 출력한다.__ 
   </br></br></br></br>
   
*  iglob 사용방법

       import glob
       for filename in glob.iglob('파일이름**/*.파일형식', recursive=True):
          print(filename)
          
   위의 예제는 __재귀적으로 현재 폴더의 모든 하위폴더까지 탐색하여 확장자가 '.파일형식'인 파일을 출력한다.__ 
   </br></br></br></br>
   
 * 예제)
       
       import glob
       for filename in glob.iglob('Unifox/**/*.jpg',recursive=True):
          print(filename)
          
    위의 예제는 Unifox폴더를 재귀적으로 돌며 jpg파일을 출력하는 코드이다.
