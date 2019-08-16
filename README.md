# Python2

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
  from sys import stdin
  a = int(stdin.readline())
  for i range(a):
    b, c = map(int, stdin.readline().split())
  
    
  # 방법 2
  # stdin.readline() 대신 input() 활용
  # 방법 1이 더 빠름
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
  
  sum_value = reduce((lambda x,y : x+y), [x for x in range(1,101)]) print(sum_value)
  ```

  