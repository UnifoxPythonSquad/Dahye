# 이터레이터(Iterator) 란?  
</br></br>
## 1)정의
   이터레이터(Iterator)는 **'반복자'의 뜻**을 가지고 있으며, __값을 차례대로 꺼낼 수 있는 객체(object)이다.__ </br></br> 
## 2)이터레이터를 사용하는 이유
   for반복문을 사용하면 숫자가 많을경우 메모리를 낭비하게 되어 **성능이 저하**된다.  </br></br>
## 3)이터레이터 사용방법
   이터레이터 **지연평가방식**(이터레이터만 생성한 후 필요한시점에서 데이터를 생성한다. 따라서, __데이터생성을 뒤로 미루는 것__ 이다.)</br>
> * 반복 가능한 객체</br>
: 반복할 수 있는 객체로, 문자열,리스트,딕셔너리 등을 반복 가능한 객체라고 한다.</br>
요소가 여러 개 들어있고, 한 번에 하나씩 꺼낼 수 있다.</br></br>
> * 판단 </br>
명령어 **dir(객체)** 를 사용하여 반복 가능한 객체인지 확인할 수 있다.
</br>

  #### 이터레이터 사용(1)
    
      >>> it = [1,2,3].__iter__()
      >>> it.__next__()
      1
      >>>it.__next__()
      2
      >>>it.__next__()
      3
      >>>it.__next__()
      Traceback (most recent call last):
        Fail "<pyshell#48>", line 1, in <module>
          it.__next__()
      StopIteration
      
 위의 예제는 이터레이더 it에 1,2,3을 저장해주고 있다.<br>
 it.__ next()__ 를 이용해 저장되어있는 값을 하나씩 뽑아주고,</br>
 더이상 이터레이터에 들어있는값이 없으면 StopIteration을 발생시켜 반복을 끝낸다.</br>
 이 방법은 __꺼낼 요소가 없을때까지 반복을 실행__ 
</br></br></br></br>
   #### 이터레이터 사용(2)
   
       >>> it = range(3).__iter__()
       >>> it.__next__()
       0
       >>> it.__next__()
       1
       >>> it.__next__()
       2
       >>> it.__next__()
      Traceback (most recent call last):
        Fail "<pyshell#5>", line 1, in <module>
          it.__next__()
      StopIteration
      
 위의 예제는 이터레이더 it에 3개를 지정해주고 있다.<br>
 it.__ next()__ 를 이용해 저장되어있는 자리 값을 하나씩 뽑아주고,</br>
 더이상 이터레이터가 없으면 StopIteration을 발생시켜 반복을 끝낸다.</br>
 첫번째 사용방법과 다른점은, __지정된 숫자가 되면 StopIteration을 발생시킨다.__ 
</br></br></br></br>
   #### 이터레이터 만들기
       class 이터레이터이름:
          def __iter__(self):
             코드
             
          def __next(self):
             코드
             
</br>

         class Count:
            def __init__(self,stop):
               self.num = 0                # 현재 숫자 유지, 0부터 지정된 숫자 전까지 반복
               
               self.stop = stop            # 반복을 끝낼 숫자
               
            def __iter__(self):
               return self                 # 현재 인스턴스 반환
               
            def __next__(self):
               if self.num < self.stop:    # 현재 숫자가 반복을 끝낼 숫자보다 작을 때
               
                  r = self.num             # 반환할 숫자를 r에 저장
                  self.num += 1            # 현재숫자 +1
                  return r                 # 숫자 반환
               else:                       # 아니면,
                  raise StopIteration      # 예외 발생
                  
                  
         for i in Count(3):
            print(i,end' ')
            
</br>




