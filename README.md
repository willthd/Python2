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

  ```
  
  ```

* filter



* reduce