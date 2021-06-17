# [Git] Git 기초 다지기



## Git Repository

---

* 로컬 저장소에서 사용



### Git Repository 명령어 종류

* commit
* branch
* checkout
* cherry-pick
* reset
* revert
* rebase
* merge



### 커밋(Commit)

* 프로젝트의 스냅샷을 기록
* 커밋은 저장소의 이전 버전과 다음 버전의 변경 내역(delta)을 저장
* 대부분 커밋이 그 커밋 위의 부모 커밋을 가리킴
* 모든 변경분(delta) 확인 명령어
  * `resolving deltas`
* 커밋은 매우 가볍고 커밋 사이의 전환도 매우 빠름
* 커밋 명령어
  * `git commit`
* 마지막 커밋 메시지 변경
  * `git commit --amend -m "변경할 메시지 내용"`



### 브랜치(Branch)

* 특정 커밋에 대한 참조(reference)
* 메모리나 디스크 공간에 부담 없음
* 작은 단위로 나누는 것이 좋음
* 커밋들음 포함하는 작업 내역
* 새 브랜치 만들기 명령어
  * `git branch [브랜치명]`
* 브랜치 이동 명령어
  * `git checkout [브랜치명]`



### 머지(Merge)

* 별도의 두 브랜치를 합침
* 머지하면 인자로 적은 브랜치와 합쳐진 커밋이 현재 브랜치 아래 붙음
  * ex) main 브랜치에 bugFix를 합치기
  * `git checkout bugFix; git merge main`
* 머지 명령어
  * `git merge [브랜치명]`



### 리베이스(Rebase)

* 브랜치끼리 작업을 접목
* 현재 브랜치를 인자로 적은 브랜치 아래 복사 후 기존 커밋들 제거됨
* 커밋 로그와 이력이 깨끗해짐
* 합쳐질 대상으로 체크아웃, 주체로 리베이스
  * ex) main 브랜치에 bugFix를 합친 커밋을 뒤에 붙이기
  * `git checkout bugFix; git rebase main`
* 리베이스 명령어
  * `git rebase [브랜치명]`



### 커밋간 이동

* HEAD: 현재 작업중인 커밋
* HEAD는 항상 작업트리의 가장 최근 커밋을 가리킴
* 일반적으로 HEAD는 브랜치 이름을 가리킴
* 커밋을 하게 되면, 브랜치의 상태가 바뀌고 변경은 HEAD를 통해 확인 가능
* HEAD 분리 명령어 (해시값은 앞 6자리만 사용해도됨)
  * `git checkout <Commit ref>`



### 상대 참조(Relative Ref)

* 한 지점에서 다른 지점으로 도달해 작업 가능
* `^` 와 `~` 동시 사용 가능

#### ^ 연산자

* `^` : 한번에 한 커밋 위로 움직임
  * ex) main의 부모로 체크아웃
    * `git checkout main^`
* `^<num>`: 여러 부모중 숫자에 맞는 부모로 올라감
  * ex) main의 두번째 부모로 체크아웃
    * `git checkout main^2`

#### ~ 연산자

* `~<num>`: 한번에 여러 커밋 위로 올라감
* num에 올라가고 싶은 부모의 갯수를 적음
* ex) HEAD에서 위로 4번째 커밋으로 체크아웃
  * `git checkout HEAD~4`



### 브랜치 강제로 옮기기

* `-f`: 강제로 실행할 때 옵션
* ex) main 브랜치를 HEAD에서 세번 뒤로 강제로 옮기기
  * `git branch -f main HEAD~3`



### 작업 되돌리기

* 개별파일이나 묶음을 스테이징
* 실제 변경을 복구

#### 리셋(Reset)

* 애초에 커밋하지 않은 것처럼 예전 커밋으로 브랜치를 옮김
* 로컬 저장소에는 리셋 이전 커밋이 아예 없어짐
* 리모트 브랜치에 사용 불가
* 리셋 명령어
  * `git reset <Commit ref>`

#### 리버트(Revert)

* 작업한 커밋 내용의 반대 내용으로 새로운 커밋을함
* 다른 사람들에게 리버트 내역 공유 가능
* 리버트 명령어
  * `git revert [브랜치명]`



### 체리픽(Cherry-Pick)

* HEAD 아래에 있는 일련의 커밋들에 대한 복사본을 만듬
* ex) side 브랜치에 있는 C2, C4 커밋만 main에 합침
  * `git cherry-pick C2 C4`
* 체리픽 명령어
  * `git cherry-pick <Commit1> <Commit2> <...>`



### 인터렉티브 리베이스(Interactive Reabse)

* 리베이스 목적지가 되는 곳에 아래에 복사될 커밋들을 보여주는 UI 제공
* `-i` 옵션을 사용
* UI 내부
  * 커밋 순서를 변경 가능
  * `pick`: 커밋을 수정하지 않고 그냥 사용
  * `reword`: 커밋 메시지를 수정
  * `edit`: 메시지, 작업 내용을 수정
  * `squash`: 해당 커밋을 이전 커밋과 합침 (메시지가 합쳐짐)
  * `fixup`: 해당 커밋을 이전 커밋과 합침 (이전 메시지만 남음)
  * `exec`: 리베이스 도중 쉘 커맨드를 입력할 수 있게함
  * `break`: 해당 라인에서 리베이스를 일시 중지
  * `drop`: 해당 커밋을 명시적으로 삭제
  * `merge`: 머지 커밋을 만들면서 합침
* ex) HEAD 포함 위로 4개를 합치기
  * `git rebase -i HEAD~4`



### 태그(Tag)

* 중요한 지점들에 영구적으로 표시
* 릴리즈나 큰 브랜치 병합 등에 사용
* 태그 만들기 명령어
  * `git tag [태그 이름] <Commit ref>`
  * `<Commit ref>` 생략시 HEAD에 태그 삽입됨



### 디스크라이브(Describe)

* 커밋 체크아웃 이후 방향 감각을 다시 찾는데 도움
* 묘사 명령어
  * `git describe <Commit ref>`
  * `<ref>` 는 commit을 의미하는 모두 가능
  * `<ref>`가 없다면 HEAD 사용
* 출력 형태
  * `<tag>_<numCommits>_g<hash>`
  * `<tag>`: 가장 가까운 부모 태그
  * `<numCommits>`: 부모 태그에서 현재가 몇 커밋 멀리있는지
  * `<hash>` 묘사하고 있는 커밋의 해시

* 문제가 되는 커밋을 찾는 명령어
  * `git bisect`



## Git Remote

---

* 클라우드 컴퓨터에 저장소를 복사한것과 같음
* 원격 저장소와 커밋을 주고 받음
* 원격 저장소를 통해 협업 가능



### 클론(Clone)

* 원격 저장소의 프로젝트를 로컬에 저장
* 복제 명령어
  * `git clone <url>`



### 원격 브랜치

* `clone` 으로 원격 저장소를 받게되면 `origin/main`과 같은 원격 브랜치가 생성됨
* 원격 브랜치는 원격 저장소의 상태를 반영
* 원격 브랜치는 체크 아웃을 하게 되면 분리된 HEAD 모드로 가게됨
* 원격 브랜치 작명 규약
  * `<remote name>/<branch name>`



### 페치(Fetch)

* 원격 저장소에서 데이터 가져오기(동기화)
  * 원격 저장소에는 있지만 로컬에 없는 커밋을 다운로드
* 원격 브랜치가 변경됨
  * 원격 브랜치가 가리키는 곳을 업데이트
* `http://` 또는 `git://` 과 같은 프로토콜로 접근
* 원격 저장소 변경 데이터 가져오기 명령어
  * `git fetch`



### 풀(Pull)

* `fetch` 와 `merge` 를 동시해 진행해줌
* 풀 명령어
  * `git pull`



### 페이크팀워크(FakeTeamwork)





* 원격 저장소가 동료에 의해 특정 브랜치나 여러개의 커밋이 갱신되는 경우를 표현
* 원격 저장소에 새로운 커밋이 생성
* 가짜 커밋 생성 명령어
  * `git fakeTeamwork <커밋할 이름> <숫자>`
  * 커밋할 이름으로 숫자만큼 생성됨



### 푸쉬(Push)

* 로컬 저장소의 커밋들을 업로드하고 원격 저장소에서 커밋들을 합치고 갱신
* `Pull` 의 반대
* 업로드 명령어
  * `git push`
  * `push.default`: 매개변수 없이 사용. git 설정에 따라 결정



### 충돌시 처리

* 원격 저장소에서 커밋이 됐는데 로컬에서 업데이트 없이 작업을 했을때 처리
  * `rebase` 이용
    * 로컬에 변경된 내용을 원격 브랜치에 추가하여 커밋
    * `git rebase origin/main`
  * `merge` 이용
    * 원격 저장소의 변경 정보를 로컬 브랜치에 병합
    * `git merge origin/main`
  * `pull` 이용
    * `rebase` 이용과 같음
    * `git pull --rebase`



### 원격 저장소 거부(Remote Rejected)

* 규모가 큰 개발팀에서 `main` 브랜치는 locked
* 따라서, 변경사항을 적용하려면 `pull request` 과정을 거침
* 실수로 `main` 브랜치에 직접 커밋했을때 처리
  1. `feature` 라는 다른 브랜치를 만들어 원격 저장소에 `push`
  2. `main` 브랜치를 `reset`



### 작업의 흐름

* `feature` 브랜치의 작업을 `main` 브랜치로 통합
* 원격 저장소에서 push하고 pull하는 작업

*`feature` 브랜치: 작업을 위해 임시로 만든 브랜치 (=토픽브랜치)*



### Rebase VS Merge

* Rebase
  * 장점: 커밋 트리가 깔끔해서 보기가 좋음
  * 단점: rebase시 커밋 트리의 (보이는) 히스토리를 수정
* Merge
  * 장점: 모든 이력이 남음
  * 단점: 한눈에 보기 어려움



### 원격 추적

* `main` 과 `origin/main` 의 연결
  * `pull` 작업 도중, 커밋들은 `origin/main`에 내려받아 지고 그다음 `main` 으로 `merge` 됨
  * `push` 작업 도중, `main` 브랜치에서 원격의  `origin/main` 로 `push` 됨
* 임의의 브랜치를 `origin/main`로 추적하게 만들 수 있음
* ex) `foo` 라는 브랜치를 원격 저장소 `main` 에 `push`
  1. `git checkout -b foo origin/main`
  2. `git branch -u origin/main foo`
     * `foo` 가 현재 작업중인 브랜치라면 생략가능



### Push 인자들

#### Remote, Place

* `git push <remote> <place>`
* `<remote>`: 원격 저장소의 도착지
* `<place>`: 로컬 저장소의 브랜치
* ex) `git push origin main`
  * 로컬 저장소의 `main` 의 모든 커밋들을 수집하여 원격 저장소의 `main` 브랜치에 부족한 커밋을 채운다

#### Destination

*  `git push origin <source>:<destination>`
* 브랜치명이 다른 원격 저장소에 푸쉬할 경우
* 일반적으로 colon ref spec(콜론 참조 스팩) 이라함
* ex) `git push origin foo:main`
  * 로컬 저장소 `foo` 브랜치의 커밋을 원격 저장소 `main` 에 푸쉬
* ex) `git push origin foo:newBranch`
  * 원격 저장소에 `newBranch` 가 없다면 자동으로 새로 생성됨



### Fetch 인자들

#### Remote, Place

* `git fetch <remote> <place>`
* `<remote>`: 원격 저장소의 도착지
* `<place>`: 로컬 저장소의 브랜치
* ex) `git fetch origin foo`
  * 원격 저장소의 `foo` 에서 로컬에 없는 커밋들을 수집하여 로컬 저장소의 `origint/foo` 브랜치에 부족한 커밋을 채운다

#### Destination

*  `git fetch origin <source>:<destination>`
* 브랜치명이 다른 원격 저장소에서 풀 할 경우
* ex) `git fetch origin main:foo`
  * 원격 저장소 `main` 에서 로컬 저장소 `foo` 브랜치에 커밋을 풀함
* `fetch` 도 콜론 참조 스팩으로 지정이 가능하나 거의 사용하지 않음
* ex) `git fetch origin foo:newBranch`
  * 로컬 저장소에 `newBranch` 가 없다면 자동으로 새로 생성됨



### Soure의 이상함

* `<source>` 에 "없음" 을 지정할 수 있음
* `git push origin :foo`
  * 원격 저장소의 `foo`, 로컬 저장소의 `origin/foo` 브랜치를 제거
* `git fetch origin :foo`
  * 로컬 저장소의 `foo` 브랜치를 생성



### Pull 인자들

* `fetch` + `merge` 이기 떄문에 `fetch` 인자를 사용하여 어디로 `merge` 되는지 파악만 하면됨
* ex) `git pull origin foo`
  * = `git fetch origin foo; git merge o/foo`
* ex) `git pull origin bar~1:bugFix`
  * = `git fetch origin bar~1:bugFix; git merge bugFix



## 출처

* [깃 컨트롤 익히기](https://learngitbranching.js.org/)



