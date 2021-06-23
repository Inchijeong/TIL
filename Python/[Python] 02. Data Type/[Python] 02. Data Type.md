# [Python] 02. Data Type



## 주석(Remark)

* 한줄 주석:  `#` 이용

* 여러줄 주석: `"""` 또는 `'''` 이용

```python
# Remark (주석)

# 한줄 주석

"""
여러줄 주석
"""

'''
여러줄 주석
'''
```



## 내장 데이터형(Built-in Types)

Python Data Type 의 종류

* Numeric
* Sequence
* Text Sequence
* Mapping
* Set
* Bool



### Numeric

* int: 정수
* float: 실수
* complex: 복소수

```python
# Numeric Type (숫자형)

# int (정수)
# float (실수)
# complex (복소수)

a = 123           # 정수
b = 3.141592      # 실수
c = 3.14E10       # 실수 (지수 형태)
d = 1 + 2j        # 복소수
e = 0o34          # 8진수
f = 0xAB          # 16진수

print(type(a))    # <class 'int'>
print(type(b))    # <class 'float'>
print(type(c))    # <class 'float'>
print(type(d))    # <class 'complex'>
print(type(e))    # <class 'int'>
print(type(f))    # <class 'int'>

div = 3 / 4       # 나눗셈
print(div)        # 0.75

result = 3 ** 3   # 지수 표현
print(result)     # 27

result = 10 % 3   # 나머지 연산
print(result)     # 1

result = 10 // 3  # 나눗셈 몫
print(result)     # 3
```



### Sequence













