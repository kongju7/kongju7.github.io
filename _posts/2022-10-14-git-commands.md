---
layout: post
title: 내가 필요해서 정리하는 Git 기본 명령어
subtitle: Git 초보자를 위한 commands
categories: Programming
tags: [git, command, 명령어, clone, commit]
---

내가 필요해서 간략하게 정리하는 **Git에서 사용할 수 있는 기본 명령어**입니다.


## 새로운 저장소 생성

- `git init` : .git 하위 디렉토리 생성    
  - (* 폴더를 새롭게 만든 후, 그 안에서 명령 실행 → 새로운 git저장소 생성)
- `git config --global user.name "<사용자명>"` : 깃 환경에서 사용자 이름을 <사용자명>으로 지정 
- `git config --global user.email "<사용자이메일명>"` : 깃 환경에서 사용자 이메일을 <사용자이메일명>으로 지정 


## 저장소 복제/다운로드(clone)

- `git clone <https:.. URL>` : 기존 소스 코드 다운로드/복제
  - 예: git clone git@github.com:kongju7/study.git  
- `git clone /로컬/저장소/경로` : 로컬 저장소 복제
- `git clone 사용자명@호스트:/원격/저장소/경로` : 원격 서버 저장소 복제


## 추가(add) 및 확정(commit)

- `git status` : 깃 상태 확인    
  - **[강조] staging이나 commit 전에 깃 상태 확인을 생활화합시다**
- `git diff` : 변경사항 확인 
- `git add <파일이름.확장자이름>` : <파일이름.확장자이름>을 스테이지에 추가 
- `git add *` :	커밋에 단일 파일의 변경 사항을 포함(인덱스에 추가된 상태)
- `git add -A` : 해당 폴더 내 변경 사항을 한번에 추가 
- `git add ./` : 해당 폴더 내 변경 사항을 한번에 추가 
- `git commit -m "<커밋메시지>"` : <커밋메세지>를 붙여 스테이지에 추가된 변경사항 확정 
- `git commit -a -m "<커밋메시지>"` : <커밋메세지>를 붙여 스테이징과 커밋 동시 진행 
- `git commit --amend` : 마지막 커밋 수정하기  
  - **[주의] 단, 이미 push한 커밋에는 사용하지 마세요!** 


## 가지치기(branch)

- `git branch` : 브랜치 목록
- `git branch <브랜치이름>` : 새 브랜치 생성 (local로 만듦)
- `git checkout -b <브랜치이름>` : 브랜치 생성 및 해당 브랜치로 이동
- `git checkout main` :	메인 브랜치로 이동 
- `git checkout --track <(remote)브랜치이름>` : 원격 브랜치를 추적하는 새로운 브랜치 만들기
- `git branch -d <브랜치이름>` : 브랜치 삭제
- `git push origin <브랜치이름>` : 만든 브랜치를 원격 서버에 전송
- `git push -u <remote> <브랜치이름>` :	새 브랜치를 원격 저장소로 push
- `git pull <remote> <브랜치이름>` :	원격에 저장된 git 프로젝트의 현재 상태를 다운받고 + 현재 위치한 브랜치로 병합


## 변경 사항 발행(push)

- `git push origin main` :	변경사항 원격 서버에 업로드
- `git push <remote> <브랜치이름>` :	커밋을 원격 서버에 업로드
- `git push -u <remote> <브랜치이름>` :	커밋을 원격 서버에 업로드
- `git remote add origin <등록된 원격 서버 주소>` :	클라우드 주소 등록 및 발행(git에게 새로운 원격 서버 주소 알림)
- `git remote remove <등록된 클라우드 주소>` :	클라우드 주소 삭제


## 갱신 및 병합(merge)

- `git pull` :	원격 저장소의 변경 내용이 현재 디렉토리에 가져오고(fetch) 병합(merge)하기 
- `git merge <다른 브랜치이름>` :	현재 브랜치에 다른 브랜치의 수정사항 병합
- `git diff <브랜치이름><다른 브랜치이름>` : 변경 내용 merge 전에 바뀐 내용 비교


## 히스토리 관리 

- `git tag <태그이름>` : 현재 커밋에 태그 달기 
- `git log` : 현재 위치한 브랜치 커밋 내용 및 식별자 확인  
  - `git log --graph`: 현재 위치한 브랜치 커밋 내용 및 식별자 + 트리 구조로된 브랜치 연결 확인  
- `git blame <파일이름>` : 파일 변경 내용, 변경자, 시간 확인 


## 취소하기 

- `git checkout -- <파일이름>` : 로컬의 변경 사항을 변경 전으로 되돌림
- `git fetch origin` : 원격 저장소의 변경사항 가져오기
- `git reset --hard HEAD` : 모든 변경사항 버리기 
- `git revert <커밋>` : 커밋 되돌리기 


## 임시 변경사항 저장 및 복원 

- `git stash` : 임시 변경사항 저장
- `git stash pop` : 임시 변경사항 복원 
- `git stash list` : 임시 변경사항 보기 
  
  
  
  
### 덧붙이는 말: 혹시 오류가 있다면 제보 주세요!
  
  
Special thanks to,  
이 글은 Git을 사랑하는 개발자 **레드님**께서 검수해 주셨습니다.  

  
```
레드님의 추가 의견  
  
- git fetch origin : 원격 저장소의 변경사항 가져오기  
  → (분류 부적절) 'pull, push 직전에 반드시 fetch로 가져오고, git log로 트리 구조를 보고, merge 할건지, rebase 할건지, 내코드에 영향 없는지 파악하는 용도'이기 때문에 '취소하기' 항목보다는 `git clone` 다음에 별도의 항목으로 다루는 것이 바람직함.    
```
    
     