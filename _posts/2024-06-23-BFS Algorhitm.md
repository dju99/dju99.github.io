---
layout: single
title: "[Algorithm] BFS, 너비 우선 탐색"
excerpt_separator: <!--break-->
categories:
  - "Algorithm"
date: 2024-06-23
toc: true
toc_sticky: true
---

BFS, 너비 우선 탐색에 대해 알아보겠습니다.

<!--break-->

<br>

## BFS, 너비 우선 탐색이란

- Breadth-First Search
- 가까운 노드부터 탐색하는 알고리즘

<br>

## BFS 동작 과정

BFS는 큐 자료구조를 사용한다.

1. 탐색 시작 노드를 큐에 넣고 _<u>방문 처리</u>_

2. 큐에서 노드를 꺼내고 해당 노드의 인접 노드 중 방문하지 않은 노드를 모두 큐에 넣음

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

def bfs(graph, start, visited):
  queue = deque([start])
  visited[start] = True
  while queue:
    v = queue.popleft()
    print(v, end=" ")
    for i in graph[v]:
      if not visited[i]:
        queue.append(i)
        visited[i] = True

bfs(graph, 1, visited)


결과값
1 2 3 8 7 4 5 6
```

### 설명

- 매개변수

  - graph: 인접 리스트로 표현된 그래프
  - start: 탐색 시작 노드
  - visited: 노드의 방문 여부를 저장하는 리스트

- 과정

  ```python
  def bfs(graph, start, visited):
    queue = deque([start])      //시작 노드를 큐에 삽입
    visited[start] = True       //시작 노드 방문 처리

      while queue:              // 큐 반복
        v = queue.popleft()     // 큐의 요소 삭제
        print(v, end=" ")       // 현재 노드 출력

        for i in graph[v]:      // i 노드에 인접한 노드에 대해 반복
          if not visited[i]:    // i 노드에 방문하지 않았으면
          queue.append(i)       // 큐에 추가
          visited[i] = True     // 해당 노드 방문 처리
  ```
