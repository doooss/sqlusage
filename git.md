# GitHub 사용법 문서

<br>

## Git 초기 설정

```
$ git init
$ git remote add orgin https://github.com/<account>/<repository>

문서작업 + 변경 상황 stage

$ git commit -m 메세지
$ git push -u origin main

<> 이때 readme 파일 이 있으면
$ git push -u origin +main

```

## 기존 Repository 제거

```
$ git remote remove origin
```

 <br>

## 새 Repository 추가

```
$ git remote add origin https://github.com/<account>/<repository>
```

## branch 

```
$ git branch -M <branch-name>
$ git push -u origin <branch-name>
```

branch의 자료를 clone 하고 싶을경우
```
$ git clone -b {branch_name} --single-branch {저장소 URL}
```
