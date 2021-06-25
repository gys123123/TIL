# 원격저장소(remoterepository)

## 기본 설정

1. 로컬 git 저장소 준비
2. github repository 생성
3. Repository default branch 변경
   1. Settings -> Repositories -> - > Repository default branch ->  master로 변경
4.  Your profile ->  Repositories new 생성 



# 명령어

### 원격 저장소 주소 추가

```bash
# git아, 원격 저장소 주소 origin이라는 이름으로 추가 할건데, 주소는 이거야.
$ git remote add origin https://github.com/gys123123/TIL.git
$ git remote add {주소이름} {주소}
# 첫 원격 저장소는 관례적으로 origin으로 이름 생성
```





### 원격 저장소 목록 보기

```bash
$ git remote -v
```



### 원격 저장소 삭제



```bash
$ git remote rm origin
$ git remote rm {주소이름}

```



### 원격 저장소에 업로드(Push)



```bash
# git아 업로드 할건데 origin이라는 이름으로 저장해둔 원격 저장소에 master 브랜치의 commit 내역들을 업로드 할거야.
$ git push -u origin master

```



- commit 내역이 없으면 업로드 불가능

git branch -m main

작업관리자에서 git credential-manager 끝내기 깃허브 아이디 비밀번호 입력하기

# pull

- 원격 저장소의 변경사항을 받아옴(업데이트)

```bash
$ git pull origin master

```



# clone

- 원격 저장소 내용 전체 복제



```bash
$ git clone {원격저장소 URL}
#새로운 환경에서 잘 쓰임
```

- 주의사항
- 이미 git init이 되어있음

