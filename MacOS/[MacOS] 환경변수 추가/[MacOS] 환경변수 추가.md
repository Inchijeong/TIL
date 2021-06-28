# [MacOS] 환경변수 추가



## 환경 변수 확인

```sh
$ printenv
```



## 특정 환경 변수 확인

```sh
# echo [환경변수명]
$ echo $PATH
```



## 일시적인 환경 변수 편집

터미널 재부팅시 사라짐

```sh
$ export PATH="$PATH:~/Downloads/flutter/bin"
```



## 영구적인 환경 변수 편집

1. 현재 사용중인 쉘 확인

   ```sh
   $ echo $SHELL
   ```

2. 경우에 따라 나뉨

   1. zsh
   2. bash



### 1. zsh 이용

1. .zshrc 편집

   ```sh
   $ vi ~/.zshrc
   ```

2. 환경 변수 추가 (Java 예시, 저장 후 종료 `:wq`)

   ```sh
   # PAHT:원하는 환경변수 위치
   export PATH="$PATH:~/Library/Java/JavaVirtualMachines/adopt-openjdk-1.8.0_292/Contents/Home/bin"
   ```

3. 설정파일 새로고침

   ```sh
   $ source ~/.zshrc
   ```

4. 확인

   ```sh
   $ echo $PATH
   ```

   

### 2. bash 이용

1. 둘중 하나 선택

   ```sh
   $ vi /etc/profile
   ```

   ```sh
   $ vi ~/.bash_profile
   ```

2. 환경 변수 추가 (Java 예시, 저장 후 종료 `:wq`)

   ```sh
   export PATH="$PATH:~/Library/Java/JavaVirtualMachines/adopt-openjdk-1.8.0_292/Contents/Home/bin"
   ```

3. zsh를 이용하려 한다면 .zshrc 에 아래 내용 추가

   ```sh
   source /etc/profile
   ```

   ```sh
   source ~/.bash_profile
   ```



## 참조

* [Deep Play](https://3months.tistory.com/537)
* [taelee.log](https://velog.io/@taelee/%ED%99%98%EA%B2%BD-%EB%B3%80%EC%88%98-%EC%84%A4%EC%A0%95-Mac)