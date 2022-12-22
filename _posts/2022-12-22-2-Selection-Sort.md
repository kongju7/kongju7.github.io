---
layout: post
title: "[Python] 선택 정렬 특징 및 파이썬 구현"
subtitle: "정렬 알고리즘 시리즈 2. 선택 정렬"
categories: Programming
tags: [Python, 파이썬, Selection Sort, 선택 정렬]
---

## 대표적인 정렬 알고리즘  

1. [버블 정렬(Bubble Sort)](https://kongju7.github.io/programming/2022/12/22/1-Bubble-Sort.html){:target="_blank"} 
2. **`선택 정렬(Selection Sort)`**
3. 삽입 정렬(Insertion Sort)
4. 퀵 정렬(Quick Sort)
5. 병합 정렬(Merge Sort))
  
  
 
## 2. 선택 정렬(Selection Sort)
  
### 1) 선택 정렬 정의 
- 배열에 있는 값들 중 최소값을 탐색하여 정렬하는 알고리즘
  - 주어진 배열에 있는 값들 중 최소값을 찾고, 해당 최솟값을 배열의 맨 앞 위치와 교환하는 방식으로 진행 
  - 정렬한 값 이후의 나머지 배열에 대해서도 위의 절차를 반복 진행 
  
### 2) 선택 정렬의 특징  
  
- 장점 
  - 구현이 간단
  - 정렬을 위한 비교 횟수는 많지만 실제로 교환하는 횟수는 적은 편. 따라서 교환이 많이 이루어져야 하는 자료 상태에서 가장 효율적으로 적용될 수 있음
  - 시간 복잡도는 버블 정렬과 동일하지만, 실제로는 조금 더 빠르게 정렬 가능
  - 역순 정렬에서 높은 효율성을 보여줌. 즉, 내림차순으로 정렬되러 있는 자료를 오름차순으로 재정렬할 때 최적의 효율을 보여 줌  
  
- 단점 
  - 시간 복잡도가 O(N²)으로 정렬 시간이 오래 걸림
    - 이미 정렬될 산태에서 소수의 자료가 추가되어 재정렬할 때 최악의 처리 속도를 보여 줌 
  - **불안정 정렬(Unstable Sort)**. 즉, 배열에 중복값이 들어 있는 경우 순서를 보장하지 않음  
  
  
### 3) 선택 정렬의 시간 복잡도 
 - 버블 정렬과 달리 서로 이웃하지 않는 노드들을 교환하기 때문에 안정적이지 않음
 - 노드값 비교 횟수(이중 반복문 사용): O(N²) 
  - 외부 루프: (N-1)
  - 내부 루프(최소값 찾기): (N-1), (N-2), (N-3), ... , 2, 1 
  - 교환 횟수: 3(N-1)  
  
  
### 4) 선택 정렬 파이썬 구현 

먼저 기본형이라고 할 수 있는 선택 정렬 **오름차순(Ascending, ASC)**을 파이썬 코드로 구현해 보겠습니다. 

```Python 
# 선택 정렬 파이썬 구현 (기본형: 오름차순) - 최소값 찾기
def selection_sort(li):
    for i in range(len(li) - 1):
        min_idx = i
        for j in range(i + 1, len(li)):
            if li[j] < li[min_idx]:
                min_idx = j
        li[i], li[min_idx] = li[min_idx], li[i]  # swap
    return li
```

다음은 선택 정렬 **내림차순(Descending, DESC)**을 파이썬 코드로 구현해 보면 다음과 같습니다. 

```Python 
# 선택 정렬 파이썬 구현 (내림차순) - 최대값 찾기 
def selection_sort(li) :
    for i in range(len(li) - 1):
        max_idx = i
        for j in range(i + 1, len(li)):
            if li[j] > li[max_idx]:
                max_idx = j
        li[i], li[max_idx] = li[max_idx], li[i]  # swap
    return li
```  
  
다음 포스트에서는 대표적인 정렬 알고리즘 중 3. 삽입 정렬(Insertion Sort)에 대해 이어서 다루겠습니다. 
     