# branch command

- 브랜치 생성

```bash
$ git branch 브랜치명
```



- 브랜치 목록

``` bash
$ git branch
```



- 브랜치 이동

```bash
# git checkout 까지만 입력한 상태에서
# tab *2 -> checkout 가능한 브랜치명 확인 가능함
$ git checkout 브랜치명
(브랜치명)$
```

```bash
# 브랜치에 대한 모든 로그 확인방법
$ git log --all --oneline 
#
$ git log --all --graph --oneline
```

```bash
#브랜치 이동시점에서 있는 파일 정보만을 가지고 있음.
# 브랜치에서 commit한 파일만 push 됨

```

- HEAD  : 현재 우리가 속한 위치

- 브랜치 생성 + 이동

```bash
$ git chekout -b 브랜치명
```



- 브랜치 병합

```bash
(master)$ git merge 브랜치명
```

> 반드시 master 브랜치에 '브랜치'를 병합 
>
> I : INSERT로 바뀜 ,병합 내용을 추가 할 수 있음 #으로 주석 밑에 부분이 
>
> ESC : 수정 후 빠져 나갈 때
>
> :wq  : 저장 후 병합 시작 
>
> 파일을 병합하는 것 브랜치는 남아있음



- 브랜치 삭제

```bash
$ git branch -d 브랜치명
```



-브랜치 강제 삭제

```bash
$ git branch -D 브랜치명
```



> merge가 되지 않는 브랜치는 강제로 삭제해야함





# 3가지 병합 상황

### 1. fast -foward

> "다른 브랜치를 생성 한 후, master 브랜치에 변경 사항이 없을 때"



### 2. 3-way merge

> "현재 브랜치(master)가 가리키는 커밋이 Merge 할 브랜치의 조상이 아니라면 현재 브랜치와 Merge할 브랜치의 커밋 2개와 두 브랜치의 공통조상 하나를 사용한다."

#### 	 1. 새로운 브랜치 signup 생성

####  	2. signup 브랜치에서 signup.py 생성

#### 		- git add, commit 잊지 말기	

#### 	 3. master 브랜치에서 new folder 생성

#### 	 4. master 브랜치와 signup 브랜치 병합



### 	3. Merge Conflict

  "두 개의 브랜치가 동일한 파일의 동일한 위치를 수정하고 Merge 하려고 할 때 발생하는 형상"

- git이 자동으로 병합하지 못하는 상황

  ### 1. 새로운 브랜치 hotfix 생성

  ```bash
  $ git branch hotfix
  $ git checkout hotfix
  # $ git checkout -b hotfix
  ```

  

  ### 2. hotfix 브랜치에서 b.txt에 새로운 내용 입력

  - add,commit 

  ``` bash
  $ git add . or b.txt
  $ git commit -m "message"
  ```

  

  ### 3.master 브랜치에서 b.txt에 새로운 내용 입력

  ```bash
  $ git add . or b.txt
  $ git commit -m "message"
  ```

  - git add, commit

  ### 4.master 브랜치와 hotfix 브랜치 병합

  ```bash
  $ git merge hotfix
  Auto-merging b.txt
  CONFLICT (content): Merge conflict in b.txt
  Automatic merge failed; fix conflicts and then commit the result.
  
  $ git status
  On branch master
  Your branch is ahead of 'origin/master' by 9 commits.
    (use "git push" to publish your local commits)
  
  You have unmerged paths.
    (fix conflicts and run "git commit")
    (use "git merge --abort" to abort the merge)
  
  Unmerged paths:
    (use "git add <file>..." to mark resolution)
          both modified:   b.txt
  
  no changes added to commit (use "git add" and/or "git commit -a")
  
  b.txt 수정 후 다시 합병 시도
  
  ```

  

