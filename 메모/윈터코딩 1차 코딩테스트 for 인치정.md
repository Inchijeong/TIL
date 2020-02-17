###### 윈터코딩 1차 코딩테스트 for 인치정

[공지사항](https://programmers.co.kr/tryouts/10523/notices) [테스트 안내](https://programmers.co.kr/test_description?tryout_id=10523) [도움말](https://programmers.co.kr/tryouts/10523/challenges/34017#) [JavaScript 레퍼런스](https://devdocs.programmers.co.kr/javascript/) [컴파일 옵션](https://programmers.co.kr/compile_options) [테스트 종료](https://programmers.co.kr/tryouts/10523/challenges/34017#)

- <svg id="checkbox-algorithm-335" class="ic-24 outline-box"><use xlink:href="/assets/svg-defs-85565b46e64863b65d9342cab5a7a782f12e73a839c8f7586a10037a0fe9a44b.svg#ic-check-box-unchecked-outline"><svg viewBox="0 0 24 24" id="ic-check-box-unchecked-outline"><path d="M19 5v14H5V5h14zm0-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2z" fill-rule="nonzero"></path></svg></use></svg>

  프로그래밍1

- <svg id="checkbox-algorithm-648" class="ic-24 outline-box"><use xlink:href="/assets/svg-defs-85565b46e64863b65d9342cab5a7a782f12e73a839c8f7586a10037a0fe9a44b.svg#ic-check-box-checked"><svg viewBox="0 0 24 24" id="ic-check-box-checked"><path d="M19 3H5a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V5a2 2 0 0 0-2-2zm-9 14l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z" fill-rule="nonzero"></path></svg></use></svg>

  프로그래밍2

- <svg id="checkbox-algorithm-3667" class="ic-24 outline-box"><use xlink:href="/assets/svg-defs-85565b46e64863b65d9342cab5a7a782f12e73a839c8f7586a10037a0fe9a44b.svg#ic-check-box-unchecked-outline"><svg viewBox="0 0 24 24" id="ic-check-box-unchecked-outline"><path d="M19 5v14H5V5h14zm0-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2z" fill-rule="nonzero"></path></svg></use></svg>

  프로그래밍3

- <svg id="checkbox-sql-119" class="ic-24 outline-box"><use xlink:href="/assets/svg-defs-85565b46e64863b65d9342cab5a7a782f12e73a839c8f7586a10037a0fe9a44b.svg#ic-check-box-checked"><svg viewBox="0 0 24 24" id="ic-check-box-checked"><path d="M19 3H5a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V5a2 2 0 0 0-2-2zm-9 14l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z" fill-rule="nonzero"></path></svg></use></svg>

  SQL1

- darklight

  sublimevimemacs

  JavaScript 

###### 문제 설명

가로 길이가 Wcm, 세로 길이가 Hcm인 직사각형 종이가 있습니다. 종이에는 가로, 세로 방향과 평행하게 격자 형태로 선이 그어져 있으며, 모든 격자칸은 1cm x 1cm 크기입니다. 이 종이를 격자 선을 따라 1cm × 1cm의 정사각형으로 잘라 사용할 예정이었는데, 누군가가 이 종이를 대각선 꼭지점 2개를 잇는 방향으로 잘라 놓았습니다. 그러므로 현재 직사각형 종이는 크기가 같은 직각삼각형 2개로 나누어진 상태입니다. 새로운 종이를 구할 수 없는 상태이기 때문에, 이 종이에서 원래 종이의 가로, 세로 방향과 평행하게 1cm × 1cm로 잘라 사용할 수 있는 만큼만 사용하기로 하였습니다. 가로의 길이 W와 세로의 길이 H가 주어질 때, 사용할 수 있는 정사각형의 개수를 구하는 solution 함수를 완성해 주세요.

##### 제한사항

- W, H : 1억 이하의 자연수

#### 입출력 예

| W    | H    | result |
| ---- | ---- | ------ |
| 8    | 12   | 80     |

##### 입출력 예 설명

입출력 예 #1
가로가 8, 세로가 12인 직사각형을 대각선 방향으로 자르면 총 16개 정사각형을 사용할 수 없게 됩니다. 원래 직사각형에서는 96개의 정사각형을 만들 수 있었으므로, 96 - 16 = 80 을 반환합니다.

![572957326.92.png](https://grepp-programmers.s3.amazonaws.com/files/production/ee895b2cd9/567420db-20f4-4064-afc3-af54c4a46016.png)

- [solution.js](https://programmers.co.kr/tryouts/10523/challenges/34017#)





```

```







1

```
function solution(w,h){
```

2

```
    var answer = 1;
```

3

```
    if (w === h){
```

4

```
        answer = w*h-w;
```

5

```
    }else{
```

6

```
        /*
```

7

```
        // 짝수x짝수
```

8

```
        if(w%2 === 0 && h%2 === 0){
```

9

```
            var s = (w < h) ? w : h;
```

10

```
            console.log('s', s);
```

11

```
            answer = w*h-(s*2);
```

12

```
        } else if(w%2 === 1 && h%2 === 1) {
```

13

```
            // 홀수x홀수
```

14

```
            answer = w*h-(h+w-1);
```

15

```
        } else { // 짝수x홀수
```

16

```
            
```

17

```
        }
```

18

```
        */
```





19

```
        if(w%2 === 1 || h%2 === 1){
```

20

```
            answer = w*h-(h+w-1);
```

21

```
        }else{
```

22

```
            var s = (w < h) ? w : h;
```

23

```
            answer = w*h-(s*2);
```

24

```
        }
```

25

```
        
```

26

```
    }
```

27

```
    // console.log(answer);
```

28

```
    return answer;
```

29

```
}
```





실행 결과

```
테스트 1 〉실패 (3.17ms, 37.8MB)
테스트 2 〉통과 (1.67ms, 37.3MB)
테스트 3 〉실패 (3.03ms, 37.8MB)
테스트 4 〉실패 (2.91ms, 37.7MB)
테스트 5 〉실패 (3.12ms, 37.7MB)
테스트 6 〉실패 (2.83ms, 37.7MB)
테스트 7 〉통과 (1.62ms, 37.2MB)
테스트 8 〉통과 (1.68ms, 37.5MB)
테스트 9 〉통과 (1.70ms, 37.4MB)
테스트 10 〉통과 (1.66ms, 37.4MB)
테스트 11 〉통과 (1.66ms, 37.6MB)
테스트 12 〉통과 (1.62ms, 37.4MB)
테스트 13 〉실패 (3.14ms, 37.7MB)
테스트 14 〉통과 (1.70ms, 37.4MB)
테스트 15 〉통과 (1.67ms, 37.5MB)
테스트 16 〉통과 (1.73ms, 37.5MB)
테스트 17 〉실패 (3.13ms, 37.8MB)
테스트 18 〉통과 (1.69ms, 37.6MB)
```

[테스트 케이스 추가하기](https://programmers.co.kr/challenge_algorithms/335/custom_testcases?tryout_id=10523)

채점 기록

실행

코드 채점하고 제출

종료까지
00:00:09