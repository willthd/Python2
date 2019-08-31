# Python_2

* 입력 받기

  ```python
  """
  Input
  5
  1 2
  3 4
  2 6
  4 6
  5 7
  """
  
  # 방법 1
  # stdin.readline()의 경우 개행문자까지 읽기 때문에 len()으로 구하면 +1됨
  from sys import stdin
  a = int(stdin.readline())
  for i range(a):
    b, c = map(int, stdin.readline().split())
  
    
  # 방법 2
  # stdin.readline() 대신 input() 활용
  # 방법 1이 더 빠름
  ```

* 출력

* ```python
  # java에서 System.out.println()과 동일
  print("adslkfjl")
  
  # java에서 System.out.print()와 동일
  print("adslkfjl", end='')
  ```

* map

  list의 각 element에 함수를 적용시켜 결과를 반환

  ```python
  # 각 원소의 제곱 값 출력
  items = [1, 2, 3, 4, 5]
  squared = list(map(lambda x: x**2, items))
  
  # 결과
  # [1, 4, 9, 16, 25]
  ```

* filter

  list의 각 element에서 어떤 조건에 일치하는 값만 반환

  ```python
  # 리스트에서 홀수만 출력
  is_odd = list(filter(lambda x: x%2 == 1, items))
  
  # 결과
  # [1, 3, 5]
  ```

* reduce

  list의 각 element끼리 연산할 때 사용

  ```python
  # 리스트의 원소들 간의 합 출력
  from functools import reduce
  
  sum = reduce((lambda x,y : x+y), [x for x in range(101)])
  
  # 결과
  # 5050
  ```

* sort

* ```python
  # 숫자는 오름차순, 문자는 알파벳순으로 정렬. 원본 정렬되어 변환
  list.sort()
  
  # sort된 list를 return. 원본 변환 x
  sorted(list)
  
  # 원소들을 거꾸로 뒤집는 것 뿐. 원본 변환
  list.reverse()
  
  # 원소들은 뒤집어 return 하지만, list()로 한 번감싸야 함. 원본 변환 x
  reversed(list)
  list[::-1]
  
# 특정 기준으로 정렬 할 때 key 사용. sorted도 마찬가지
  list.sort(key = lambda x: x[0])
  
  # 두 가지 기준으로 정렬 할 때, 앞의 것이 우선 기준. sorted도 마찬가지
  list.sort(key = lambda x: (x[0], x[1]))
  ```
  
* Indexing, 인덱싱

* ```python
  # arr[A:B:C]의 의미는, index A 부터 index B 까지 C의 간격으로 배열을 만듬
  [0, 1, 2, 3, 4, 5, 10]
  
  a = "12345"
  a[::-1]
  
  # 출력 결과
  54321
  ```

* String, 문자열

* ```python
  # 아래 경우 모두 s 원본 변경 x. return 값만 변경
  # 대문자 
  s.upper()
  
  # 소문자
  s.lower()
  
  # 앞 글자만 대문자
  s.caplitalize()
  ```

* for문, 값과 index 함께 나타내기

* ```python
  arr = [2, 7, 10]
  for idx, val in enumerate(arr):
  	print(idx, val)
  	
  # 만약 enumerate에서 두 번째 인자를 줄 경우, idx는 두 번째 값(여기선 5)부터 시작
  for idx, val in enumerate(arr, 5):
  	print(idx, val)
  ```

* string에서 ==와 is의 차이

* ```python
  a = "pub"
  b = ''.join(["p", "u", "b"])
  
  # a == b일 경우 True. 값을 비교
  # s is b일 경우 False. 객체 자체를 비교
  ```

* for문, 반복문

* ```python
  for i in range(10, 7, -1):
  	print(i)
  	
  # 출력 결과
  # 10
  # 9
  # 8
  
  # for문 내에서 index 변화 불가능
  
  '''
  for i in range(10):
  	if i == 3:
  		i = 8
  	print(i)
  '''
  	
i = 0
  while i < 10:
  	if i == 3:
  		i = 8
      i += 1
  	print(i)
  	i += 1	# 꼭 추가
  ```
  
* format

* ```python
  print('Case #{}: {} + {} = {}'.format(t+1, A, B, A+B))
  ```

* list

* ```python
  # 사이즈 1000인 리스트 선언
  a = [0] * 1000
  
  # 값의 index 찾기
  a.index(값)
  ```

* 소수점

  ```python
  # 소수점 표현 1, 소수점 4째 자리
  "{0:0.4f}".format(y)
  
  # 소수점 표현 2, 3.4213
  "%0.4f" % 3.42134234
  ```

* 몫, 나머지

  ```python
  # 몫만 구하기
  5//3
  
  # 나머지만 구하기
  5%3
  ```

* stack, queue, deque

  ```python
  # 스택
  stack = []
  stack.append(1)
  stack.append(2)
  stack.append(3)
  stack.pop() # 3
  stack.pop() # 2
  stack.pop() # 1 
  
  # 큐
  queue = []
  queue.append(1)
  queue.append(2)
  queue.append(3)
  queue.pop(0) # 1
  queue.pop(0) # 2
  queue.pop(0) # 3
  
  
  # 큐, 덱을 이용함, 큐의 경우 앞으로 한칸 씩 값을 옮겨야 하기 때문에 시간 복잡도 O(n)되기 때문
  from collections import deque # (*deque는 double ended queue의 약자입니다)
  queue = deque()
  queue.append(1)
  queue.append(2)
  queue.popleft() # 1
  queue.popleft() # 2
  
  # list를 deque로 변환
  dq = Deque(list_)
  ```

  