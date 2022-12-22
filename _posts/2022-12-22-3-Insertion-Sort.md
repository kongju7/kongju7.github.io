---
layout: post
title: "[Python] 삽입 정렬 특징 및 파이썬 구현"
subtitle: "정렬 알고리즘 시리즈 3. 삽입 정렬"
categories: Programming
tags: [Python, 파이썬, Insertion Sort, 삽입 정렬]
---

## 대표적인 정렬 알고리즘  

1. [버블 정렬(Bubble Sort)](https://kongju7.github.io/programming/2022/12/22/1-Bubble-Sort.html){:target="_blank"} 
2. [선택 정렬(Selection Sort)](https://kongju7.github.io/programming/2022/12/22/2-Selection-Sort.html){:target="_blank"} 
3. **`삽입 정렬(Insertion Sort)`**
4. 퀵 정렬(Quick Sort)
5. 병합 정렬(Merge Sort))



## 3. 삽입 정렬(Insertion Sort)
  
### 1) 삽입 정렬 정의 
- 삽입하고자 하는 노드와 이미 정렬된 배열과 비교하는 방법
  - 노드보다 작은 값을 가진 노드가 나올 때까지 비교를 진행하며, 노드보다 작은 값을 발견하면 작은 값 오른쪽 인덱스에 노드를 삽입
  

### 2) 삽입 정렬의 특징  
  
- 장점 
  - 최선의 경우 시간 복잡도가 O(N)으로, 빠른 효율성을 나타냄
  - 성능이 좋아서 다른 정렬 알고리즘의 일부로 사용되기도 함 
  - 소량의 데이터 정렬에 효율적임 
  - **안정 정렬(Stable Sort)**. 즉, 배열에 중복값이 들어 있는 경우 순서를 유지함 

- 단점 
  - 데이터의 상태 및 크기에 따라 성능의 편차가 크게 벌어짐 
  - 최악의 경우 시간 복잡도가 O(N²)이 되기도 함 
  

### 3) 삽입 정렬의 시간 복잡도 
- 리스트가 이미 정렬된 경우, 리스트의 각 항목을 비교하며 리스트에 정렬된 요소가 있는지 확인함 : O(N)
- 리스트를 역순으로 재정렬하려면 인덱스 변경을 위해 반복문을 정렬될 때까지 수행 : O(N²)
  
  
### 4) 삽입 정렬 파이썬 구현 

먼저 기본형이라고 할 수 있는 삽입 정렬 **오름차순(Ascending, ASC)**을 파이썬 코드로 구현해 보겠습니다. 

```Python 
# 삽입 정렬 파이썬 구현 (기본형: 오름차순) 
def insertion_sort(li):
    for i in range(1, len(li)):
        for j in range(i, 0, -1):
            if li[j - 1] > li[j]:
                li[j - 1], li[j] = li[j], li[j - 1]  # swap
    return li
```

삽입 정렬 **내림차순(Descending, DESC)**을 파이썬 코드로 구현해 보면 다음과 같습니다. 

```Python 
# 삽입 정렬 파이썬 구현 (내림차순) 
def insertion_sort_desc(li):
    for i in range(1, len(li)):
        for j in range(i, 0, -1):
            if li[j - 1] < li[j]:
                li[j - 1], li[j] = li[j], li[j - 1]  # swap
    return li
```  
  
다음 포스트에서는 대표적인 정렬 알고리즘 중 4. 퀵 정렬(Quick Sort)에 대해 이어서 다루겠습니다. 
     