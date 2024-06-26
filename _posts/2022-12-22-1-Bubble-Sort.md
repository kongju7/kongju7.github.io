---
layout: post
title: "[Python] 버블 정렬 특징 및 파이썬 구현"
subtitle: "정렬 알고리즘 시리즈 1. 버블 정렬"
categories: Programming
tags: [Python, 파이썬, Bubble Sort, 버블 정렬]
---

## 대표적인 정렬 알고리즘  

1. **`버블 정렬(Bubble Sort)`**
2. [선택 정렬(Selection Sort)](https://kongju7.github.io/programming/2022/12/22/2-Selection-Sort.html){:target="_blank"} 
3. [삽입 정렬(Insertion Sort)](https://kongju7.github.io/programming/2022/12/22/3-Insertion-Sort.html){:target="_blank"} 
4. 퀵 정렬(Quick Sort)
5. 병합 정렬(Merge Sort))
  
  
  
## 1. 버블 정렬(Bubble Sort)
  
### 1) 버블 정렬 정의 
- 서로 이웃한 두 원소를 비교하여 정렬하는 알고리즘 
  - 이웃한 2개의 값을 비교하여 크기가 순서대로 되어 있지 않으면 서로 교환하는 방식으로 진행
  

### 2) 버블 정렬의 특징  
  
- 장점 
  - 구현이 간단
  - **안정 정렬(Stable Sort)**. 즉, 배열에 중복값이 들어 있는 경우 순서를 유지함 
  
- 단점 
  - 순서에 맞지 않은 요소를 이웃한 요소와 교환 
  - 하나의 요소가 가장 왼쪽에서 가장 오른쪽으로 이동하기 위해서는 배열에서 모든 다른 요소들과 교환되어야 함 
  - 특히 특정 요소가 최종 정렬 위치에 이미 도착해 있는 경우라도 교환이 일어나기도 함 
  
- 한마디로 **가장 간단한 정렬 알고리즘이지만, 매우 비효율적**인 정렬 알고리즘
  
  
### 3) 버블 정렬의 시간 복잡도 
- 배열 전체를 살펴보는 과정을 무조건 N번 진행(이중 반복문 사용): O(N²)  
- 옆에 있는 이웃 노드와 교환하므로 안정적임  
  - 비교 횟수: (N-1) + (N-2) + (N-3) + ... + 1 = N(N-1)/2  
  
  
### 4) 버블 정렬 파이썬 구현 

먼저 기본형이라고 할 수 있는 **오름차순(Ascending, ASC)**을 파이썬 코드로 구현해 보겠습니다. 

```Python 
# 버블 정렬 파이썬 구현 (기본형: 오름차순)
def bubble_sort(li):
    for i in range(len(li)-1, 0, -1):
        for j in range(i):
            if li[j] > li[j + 1]:
                li[j], li[j + 1] = li[j + 1], li[j]  # swap
    return li
```

버블 정렬 **내림차순(Descending, DESC)**을 파이썬 코드로 구현해 보면 다음과 같습니다. 

```Python 
# 버블 정렬 파이썬 구현 (내림차순)
def bubble_sort_desc(li) :
    for i in range(len(li)):
        for j in range(len(li)-1, i, -1):
            if li[j] > li[j - 1]:
                li[j], li[j - 1] = li[j - 1], li[j]  # swap
    return li
```  
  
다음 포스트에서는 대표적인 정렬 알고리즘 중 2. [선택 정렬(Selection Sort)](https://kongju7.github.io/programming/2022/12/22/2-Selection-Sort.html){:target="_blank"}에 대해 이어서 다루겠습니다. 
    
  