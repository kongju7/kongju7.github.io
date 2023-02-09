---
layout: post
title: "[Python] .env 설정 방법"
subtitle: "API token 숨김 처리"
categories: Programming
tags: [Python, Programming, Python-dotenv, .env, API token]
---

## Python에서 .env 설정 방법 
  
코드를 깃허브 등에 공개할 때 API token을 숨김 처리해야할 때가 있다.  
이 때 .env 파일을 활용하면 된다. 
  
### Required Python module : [Python-dotenv](https://github.com/theskumar/python-dotenv){:target="_blank"}
  
.env 파일을 활용하기 위해서는 먼저 `Python-dotenv` 모듈을 설치해야 된다.   
  
```Shell
pip install python-dotenv
```
  
### .env 
  
 `Python-dotenv` 모듈의 설치가 끝나면, 작업 폴더에서 `.env` 파일을 생성한다.    
  
```Shell
touch .env 
```
  
그리고 `.env` 파일을 연다.  
  
```Shell
open .env 
```
  
`.env` 파일 안에 숨김 처리하고 싶은 API token을 아래와 같은 형식으로 적어 넣는다.    
여기서 export 다음에 오는 변수 명(이 예제에서는 'api_key')을 Python 파일에서 호출하여 사용하면 된다.    

```
export api_key = "my_secret_api_token"
```
  
  
### .gitignore 
  
`.env` 파일이 깃허브 등에 업로드되어 API token이 공개되는 불상사(?)를 막기 위해서      
`.gitignore` 파일을 생성하여, 그 파일 안에 `.env`를 추가할 필요가 있다.    
  
```
.env
```
  
### Python Code 
  
파이썬 파일에서는 다음과 같이 작성하면 API token을 숨김처리 할 수 있게 된다.      
  
```Python
from dotenv import load_dotenv  
import os    
  
# load .env  
load_dotenv()  
  
api_key = os.environ.get('api_key')
```