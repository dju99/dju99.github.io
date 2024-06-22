---
layout: single
title: "[Algorithm] DFS, 깊이 우선 탐색"
excerpt_separator: <!--break-->
categories:
  - "Algorithm"
date: 2024-06-22
toc: true
toc_sticky: true
---

DFS, 깊이 우선 탐색에 대해 알아보겠습니다.

<!--break-->

<br>

## DFS, 깊이 우선 탐색이란

- Depth-First Search
- 그래프에서 깊은 부분을 우선으로 탐색하는 알고리즘

<br>

## DFS 동작 과정

- DFS는 스택 자료구조를 사용한다.

1. 탐색 시작 노드를 스택에 넣고 _<u>방문 처리\*</u>_

2. 스택 최상단에 노드에 방문 안한 인접 노드가 <br>
   \- 있으면 그 인접 노드를 스택에 넣고 방문 처리 <br>
   \- 없으면 최상단 노드를 스택에서 뺌

3. 위 과정을 반복

> 스택에 삽입되어 처리된 노드가 다시 삽입되지 않도록 함.

<br>

## 예제 코드

### 코드

```python
graph = [
  [],
  [2, 3, 8],
  [1, 7],
  [1, 4, 5],
  [3, 5],
  [3, 4],
  [7],
  [2, 6, 8],
  [1, 7]
]

visited = [False] * 9

def dfs(graph, v , visited):
  visited[v] = True
  print(v, end =" ")
  for i in graph[v]:
    if not visited[i]:
      dfs(graph, i, visited)

dfs(graph, 1, visited)


결과값
1 2 7 6 8 3 4 5
```

### 설명

- 매개변수

  - graph: 인접 리스트로 표현된 그래프
  - v: 현재 방문 중인 노드
  - visited: 노드의 방문 여부를 저장하는 리스트

- 과정

  ```python
  def dfs(graph, v , visited):
    visited[v] = True           //현재 노드 방문 처리

    print(v, end =" ")          // 현재 노드 출력

    for i in graph[v]:          // 현재 노드와 연결된 노드에 대해 반복
      if not visited[i]:        // i 노드에 방문하지 않았으면
      dfs(graph, i, visited)    // i에 대해 dfs 호출
  ```
