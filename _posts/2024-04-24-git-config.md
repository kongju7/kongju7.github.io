---
layout: post
title: "[Git] 깃 계정 정보 등록/삭제하기"
subtitle: "git user.name user.email 등록/삭제하기"
categories: Programming
tags: [git, command, 명령어, git config, user.name, user.email]
---

## git config user.name user.email 등록/삭제하기 

오늘은 깃 계정 정보를 등록하거나 삭제하는 방법에 대해서 정리해 보도록 하겠습니다. 


### 1. 깃 설정 확인 
  
먼저 아래의 명령어를 통해서 깃 설정 상태를 확인합니다.   
  
```
git config --global --list 
```

이 때 위 예제에서 사용한 `--global` 대신 `--local`, `--system` 옵션을 사용할 수도 있습니다. 
- `--local`: 작업 폴더,  
- `--global`: 전역,  
- `--system`: 시스템 전체 를 각각 의미합니다.     
  
  
  
### 2. 사용자 이름과 이메일 등록 
  
이메일은 [깃허브(GitHub)](https://github.com/){:target="_blank"} 계정에 등록한 이메일로 작성해 주세요.
참고로 [GitHub > Settings > Emails](https://github.com/settings/emails){:target="_blank"}에서 복수의 이메일을 등록할 수 있으니,  
사용 개발 환경이나 용도에 따라서 이메일을 구분해 사용하는 것도 좋습니다.  
  
```
git config --global user.name "{이름}"
git config --global user.email "{이메일}"
```
   
  
### 3. 저장된 사용자 이름과 이메일 삭제 
  
`--unset` 명령어를 사용하면 저장된 사용자 이름과 이메일을 삭제할 수 있습니다. 

```
git config --global --unset user.name
git config --global --unset user.email
```
  
  
### 4. 저장된 자격 증명 헬퍼 삭제 
  
저장된 자격 증명 헬퍼까지 삭제하게 되면, 깃 푸쉬를 통해 원격 저장소에 접근할 때마다 수동으로 사용자 이름과 비밀번호를 입력해야 합니다.
  
```
git config --global --unset credential.helper
```
  
  
