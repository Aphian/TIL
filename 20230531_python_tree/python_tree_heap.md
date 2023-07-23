### Tree(트리)
- 비선형 구조 1:N 관계 자료구조
- 루트 : 노드 중 최상위 노드
### Binary Tree
- 모든 노드들이 2개의 서브트리를 갖는 형태의 트리
- 탐색 루트 기준으로 `key(왼쪽) < key(루트) < key(오른쪽)`
  1. 포화 이진트리 : 노드가 포화상태의 이진 트리
  2. 완전 이진트리 : Full 이진트리의 노드 끝번호 까지 빈 자리가 없는 이진트리 왼쪽 부터 채움
  3. 편향 이진트리 : 한쪽 방향으로만 자식 노드를 가지는 트리
- 순회
  1. 전위 순회
  2. 중위 순회
  3. 후위 순회
- 시간복잡도
  1. 리스트 순차 : O(N)
  2. 정렬된 리스트 순차 : O(N)
  3. 정렬된 리스트 이진 : O(logN)
  4. 이진 탐색 트리 평균 : O(logN)
---
### Heap que(힙)
- 완전 이진 트리에 있는 노드 중 키값이 가장 큰 노드나 가장 작은 노드를 찾기 위해 만든 자료구조
---
### Deque(데큐)
- 리스트는 너무 포괄적으로 사용하기 위해 구현되어 있는 자료구조임
- -> 양 끝만을 다루기 위해 사용하는 자료구조 리스트보다 가벼움/ 사이값은 신경안씀.
---
### Greedy(그리드)
- 최적화 문제를 해결하는 알고리즘
- 최적해를 구하는 데 사용되는 근시안적 방법
- 최적해의 근사값을 구하는데 사용하는 경우가 많음.