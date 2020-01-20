# [Git]  rebase 를 이용하여 commit 합치기



여러개의 commit들을 합쳐보자.

`git rebase -i HEAD~N` 명령어를 사용한다.

여기서  N은 현재 commit 에서 몇번째까지 선택할지 정하는 숫자이다.



>  `git log --oneline` 명령어로 commit 이력을 간략하게 볼수 있다.



다음과 같이 test1~3 까지 커밋이 존재한다.

```shell
PS C:\Users\MSYNC-ICJ\workspace\vsc\git_test> git log --oneline
91155bc (HEAD -> master, origin/master) test4
954a86d test3
dff257a test2
dfc1d9a test1
361a5cb init comiit
```



현재 헤드부터 지난 3개의 커밋을 합쳐보겠다.

`git rebase -i HEAD~3` 을 입력하자.

다음과 같은 화면이 나올것이다.

```shell
pick dff257a test2
pick 954a86d test3
pick 91155bc test4

# Rebase dfc1d9a..91155bc onto dfc1d9a (3 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```



test4, test3의 커밋내역은 유지한체 메시지를 제거하기 위해 각각 squash로 수정한다.

(vi 명령어 참조)

```shell
pick dff257a test2
squash 954a86d test3
squash 91155bc test4

...
```



수정(`i`)하고 저장(`:wq`)하면 다음과 같이뜬다.

```shell
# This is a combination of 3 commits.
# This is the 1st commit message:

test2

# This is the commit message #2:

test3

# This is the commit message #3:

test4

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Mon Dec 30 11:28:49 2019 +0900
#
# interactive rebase in progress; onto dfc1d9a
# Last commands done (3 commands done):
#    squash 954a86d test3
```



그대로 두면 다음과 같이 이력이 남을 것이므로

```shell
test2

test3

test4
```



하나로 통햅해주었다.

```shell
# This is a combination of 3 commits.
# This is the 1st commit message:

test2~4

# Please enter the commit message for your changes. Lines starting
...
```



똑같이 수정 이후 저장해본뒤 로그를 확인해보자.

412a908 라는 새로운 커밋에 기존 세 이력이 적용된것을 확인할 수 있다.

```shell
PS C:\Users\MSYNC-ICJ\workspace\vsc\git_test> git log --oneline
412a908 (HEAD -> master) test2~4
dfc1d9a test1
361a5cb init comiit
```



푸쉬가된 이력을 rebase해서 다시 올릴경우 에러가 발생한다.

```shell
PS C:\Users\MSYNC-ICJ\workspace\vsc\git_test> git push origin master
To https://github.com/Inchijeong/git_test.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/Inchijeong/git_test.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```



과감하게 force 옵션을 사용하면 올릴수 있다.

`git push origin master -f`

다만,  주의하도록하자.



* squash를 사용할 경우

현제 커밋 메시지와 내역을 가지고 이전 이력으로 합친다.

* fixup을 사용할 경우

현재 커밋을 제거하고 이전 이력으로 합친다.



---



reword

drop

테스팅후 추가











