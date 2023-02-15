---
layout: post
title: "[Python] requirements.txt로 라이브러리 한 번에 설치하기"
subtitle: "pip install -r requirements.txt"
categories: Programming
tags: [Python, Programming, pip, requirements.txt]
---



파이썬을 이용하다보면 다른 훌륭한 개발자들이 미리 만들어놓은 라이브러리를 자주(항상) 사용하게 된다.  
수행하는 프로젝트에 따라서 사용하는 라이브러리가 여러 개인 경우가 많은데,   
이 때 pip과 라이브러리 목록을 담은 txt 파일 하나면 필요한 라이브러리를 한 번에 설치할 수 있다.  


## pip list 

우선 내 컴퓨터에 어떤 라이브러리가 설치되어 있는지 확인해보자.  

터미널에서 `pip list`를 입력하면 다음과 같이 pip으로 설치된 모든 라이브러리가 나온다.

```
$ pip list
Package                                           Version
------------------------------------------------- --------------------
absl-py                                           1.0.0
afinn                                             0.1
aiohttp                                           3.8.1
aiosignal                                         1.2.0
alabaster                                         0.7.12
alembic                                           1.8.0
anaconda-client                                   1.10.0
anaconda-navigator                                2.2.0
anaconda-project                                  0.10.2
analytics-python                                  1.4.0
anyio                                             3.5.0
appdirs                                           1.4.4
applaunchservices                                 0.2.1
appnope                                           0.1.2
appscript                                         1.1.2
argon2-cffi                                       21.3.0
argon2-cffi-bindings                              21.2.0
arrow                                             1.2.2
astroid                                           2.6.6
astropy                                           5.0.4
asttokens                                         2.0.5
astunparse                                        1.6.3
async-generator                                   1.10
async-timeout                                     4.0.1
atomicwrites                                      1.4.0
attrs                                             21.4.0
audioread                                         2.1.9
...
```


이 명령어를 통해 2022년 7월 27일 현재 내 컴퓨터에 깔려있는 파이썬 라이브러리를 확인할 수 있다.   
너무 많아서 (...)이하는 생략했다.  


다음 명령어를 활용하면 내 컴퓨터(혹은 특정 가상환경)에 설치되어 있는 Python 라이브러리의 목록을 requirements.txt로 생성할 수 있다.

```Shell
pip freeze > requirements.txt
```



## Python 라이브러리 한 번에 설치하기: requirements.txt 활용 

이 라이브러리들을 그대로 다른 컴퓨터나 가상환경에 설치하고 싶거나,
혹은 다른 프로젝트에서 필요로하는 라이브러리를 한 번에 설치하고 싶을 때는 어떻게 하면 좋을까?  


먼저, 장인 정신으로 모든 라이브러리를 **하나하나 설치**하는 방법이 있다.  
이 경우 수많은 오타와 시간, ERROR 메세지를 각오해야 한다. 


두번째로는 **requirements.txt**를 이용해서 필요한 라이브러리를 한 번에 설치하는 방법이 있다.  

requirements.txt는 한 프로젝트를 수행하기 위해 필요한 라이브러리 목록을 작성한 텍스트 파일이다.  
파일명을 꼭 requirements.txt로 할 필요는 없지만, 
파이썬 개발자 대부분이 requirements.txt라는 이름으로 주로 사용한다.  

`pip freeze > requirements.txt` 명령어로 내 컴퓨터에서 직접 작성하였거나    
다른 프로젝트에서 제공된 **requirements.txt**를  
해당 라이브러리를 설치하고 싶은 다른 컴퓨터나 가상환경에 넣고  
pip install에 -r 옵션과 함께 파이썬 라이브러리 목록이 들어있는 파일명을 명령어로 치기만 하면
한 번에 필요로 하는 모든 라이브러리를 설치할 수 있다. 


```Shell
pip install -r requirements.txt
```



## 주의사항 

터미널에서 설치할 때는 해당 파일(requirements.txt)이 들어가 있는 폴더(나 가상환경)로 이동한 후 작업을 해주어야 한다.  
안그러면 다음과 같은 ERROR 메세지를 확인하게 된다.  

```
ERROR: Could not install packages due to an OSError: [Errno 2] No such file or directory: '/opt/concourse/worker/volumes/live/ba252660-e2b9-4a6d-6906-9be4ed7deda4/volume/aiohttp_1646806382603/work'
```



참고로, 프로젝트에 따라서는 라이브러리의 특정 버젼 설치가 필요하기도 하는데,  
이 때에는 라이브러리 이름 옆에 **==2.0** 이런 식으로 버젼이 명시되어 있기도 한다.  

```
abc==2.0 
```


만약 특정 버젼 이상의 버젼을 의미할 때는 **>=**로 표시된다. 

```
abc>=2.0 
```


