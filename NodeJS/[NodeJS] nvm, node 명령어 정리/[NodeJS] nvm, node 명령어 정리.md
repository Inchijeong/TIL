# [NodeJS] nvm, node 명령어 정리



## 현재 사용하는 버전 확인

```sh
$ node -v
```



## 설치된 버전 목록

```sh
$ nvm ls
```



## 설치할 수 있는 버전 목록 보기

```sh
$ nvm ls-remote
```



## 특정 버전 설치하기

```sh
$ nvm install v10.15.0
```



## 특정 버전 사용하기

```sh
$ nvm use v11.8.0
```



## 특정 버전 기본값으로 설정

```sh
$ nvm alias default 8.9.4
```



## 설치되어 있는 가장 최신버전 기본값으로 설정

```sh
$ nvm alias default node
```



## 전역에 설치된 모듈 목록

```sh
$ npm list --depth=0 -g
```



## 현재 프로젝트에 설치된 모듈 목록

```sh
$ npm list --depth=0
```



## 현재 프로젝트에 설치된 모듈 삭제

```sh
$ rm -rf node_modules dist
```





## Mac에서 Node 완전 삭제

1. ```sh
   lsbom -f -l -s -pf /var/db/receipts/org.nodejs.pkg.bom | while read f; do sudo rm /usr/local/${f}; done
   
   sudo rm -rf /usr/local/lib/node /usr/local/lib/node_modules /var/db/receipts/org.nodejs.*
   ```

2. ```sh
   cd /usr/local/lib
   
   sudo rm -rf node*
   ```

3. ```sh
   cd /usr/local/include
   
   sudo rm -rf node*
   ```

4. ```sh
   brew uninstall node
   ```

5. ```sh
   sudo rm -rf /usr/local/bin/npm
   sudo rm -rf /usr/local/bin/node
   ls -las
   ```

6. ```sh
   sudo rm -rf /usr/local/share/man/man1/node.1
   
   sudo rm -rf /usr/local/lib/dtrace/node.d
   
   sudo rm -rf ~/.npm
   ```

7. Node가 완전히 삭제되었다면, nvm → node → npm 순으로 다시 설치



## 참조

* [https://velog.io/@minidoo/Node-mac에서-Node.js-완전히-삭제하기](https://velog.io/@minidoo/Node-mac%EC%97%90%EC%84%9C-Node.js-%EC%99%84%EC%A0%84%ED%9E%88-%EC%82%AD%EC%A0%9C%ED%95%98%EA%B8%B0)
* [Node.js 설치와 예제](https://madplay.github.io/post/nodejs-install-osx)

