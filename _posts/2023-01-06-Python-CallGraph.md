---
layout: post
title: "[Python] 프로젝트의 호출 그래프(Call Graph) 그리기"
subtitle: "draw.io와 project graph 활용하기"
categories: Programming
tags: [Python, Programming, Call Graph, draw.io, graphviz, project graph]
---

## 호출 그래프 그리기 
  
이번에 개인 프로젝트에서는 이진 분류 인공신경망 함수를 Numpy 등만을 활용해 직접 구현하고,    
호출 그래프(call graph)를 직접 작성할 일이 생겼습니다.    
  
호출 그래프를 그리는 방법은 크게 2가지를 생각해 볼 수 있습니다.    
   
1. 한 땀 한 땀 정성껏 그린다.  
  1-1. 고전적으로 Microsoft Powerpoint를 이용한다.   
  1-2. 순서도(flowchart)에 특화된 프로그램(draw.io 등)을 이용한다.    

2. 파이썬 라이브러리를 이용해 자동화한다.   
  2-1. pycallgraph 라이브러리를 이용한다.   
  2-2. project graph 라이브러리를 이용한다.  
  
  
이번에 저는 1-2와 2-2를 이용해서 호출 그래프를 작성하였습니다. 

## draw.io를 이용해 그리기 

1-2의 대표적인 프로그램은 [draw.io](https://app.diagrams.net/){:target="_blank"}가 있습니다. 
  
온라인에서 바로 그릴 수도 있고,  
프로그램을 다운받아서 로컬에서 설치해 사용할 수도 있습니다.  
  
구글 드라이버(Google Drive)와도 연동할 수 있어 인터넷 연결만 가능하면 어디에서든지 수정이 가능하다는 장점이 있습니다.   
그 외에도 로컬이나 OneDrive, Dropbox, Github, GitLab 등에도 저장할 수 있으니 참고해 주세요.    
  
![draw.io 첫 화면](/assets/images/draw.io_screenshot.png "draw.io front page")  
  
draw.io는 프로그램이 직관적으로 구성되어 있어서 이용하기도 쉽고,   
png, jpg, pdf 등 다양한 형식으로 내보내기도 됩니다.   
(한 땀 한 땀 그리려고 집중하니까 시간도 정말 잘 가더라구요!)
   
 
## project graph 라이브러리를 이용해 그리기    

그리고 2. 파이썬 라이브러리를 이용해 자동화하는 방안도 함께 진행하였습니다.   
구글에 python call graph 검색하면 제일 처음 나오는 라이브러리는 [pycallgraph](https://pycallgraph.readthedocs.io/en/master/){:target="_blank"}더라구요. 
  
공식 문서에 따라서 설치를 시도하였는데, 설치할 수 없다는 **ERROR** 메세지를 만나고야 말았습니다.   
  
추가로 검색을 이어가다가 project graph라는 라이브러리를 소개하는   
[이 글](https://www.statworx.com/en/content-hub/blog/how-to-automatically-create-project-graphs-with-call-graph/){:target="_blank"}을 확인하게 되었습니다.  
  
왠지 될 것만 같은 느낌이 들어서 이 글을 따라서 호출 그래프 작성을 시도했고,  
제대로 작성되는 것을 확인하였습니다.    
  
  
### project graph 설치 방법

(Mac OS 기준) 설치 방법은 다음과 같습니다.   
  
먼저 터미널에서 brew를 이용해 **graphviz** 라이브러리를 설치해야 합니다.    
(brew가 설치되어 있지 않은 분들은 brew부터 설치해야 겠죠?)     
시간이 다소 소요된다는 점 주의해 주세요.    

```sh
brew install graphviz
```

그 다음 project graph라는 라이브러리를 설치합니다.  
   

```sh
pip install git+https://github.com/fior-di-latte/project_graph.git
```
  
뜻 있는 분(!)께서 작성해 배포한 라이브러리로 추측되는데,    
깃허브에 README 파일을 작성하지 않으셔서 구체적인 내용을 파악하기 어렵다는 단점이 있습니다.   
  
  
### project graph 사용 방법

이제 호출 그래프를 실제로 그릴 일만 남았습니다. 
  
먼저, 호출 그래프를 작성할 파이썬 스크립트 파일을 준비해 주세요.    
(간단한 함수를 몇 가지 작성한 파일로 실험을 해보셔도 좋을 것 같습니다.)    
그리고 파이썬 스크립트 파일 실행을 위해 해당 프로젝트 내 루트 디렉토리로 이동합니다.   
  
이제 모든 준비는 끝났습니다. 
  
터미널에서 명령어 project_graph 한 칸 띄우고 {파이썬 스크립트 파일명}.py를 치고 엔터를 누르면,   
해당 스크립트 파일이 실행되면서 호출 그래프를 자동적으로 생성할 수 있습니다.    
   
```
project_graph myproject.py
```
  
만약 사용하는 외부 라이브러리까지 모두 포함해 그리고 싶다면 `-a` 명령어를 추가하면 됩니다.  
  
```
project_graph -a myproject.py
```
  
(그 외의 추가 용법에 대해서는 좀 더 연구한 다음에 업데이트를 해보도록 할께요.)  
  
### project graph 적용 예제 
  
다음은 제가 이번에 진행하고 있는 이진 분류 프로젝트의 호출 그래프를   
project graph로 작성한 예입니다. 
  
  
![이번 프로젝트 적용 호출 그래프](/assets/images/cp1_callgraph.png "Call_Graph")  
  
같은 파일을 여러 번 그려 보았는데, 
그릴 때마다 호출 그래프의 그림이 조금씩 달랍니다.    
(마음에 드는 그래프가 나올 때까지 여러 번 해보시길 추천드립니다!)
  
  