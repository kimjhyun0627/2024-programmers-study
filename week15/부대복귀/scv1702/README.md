# 문제 풀이

## 문제 해설

주어진 그래프 $G$가 무방향 그래프이기 때문에 `destination`에서 BFS를 수행해 각 정점까지의 거리를 계산해주면 된다. 이때 그래프를 구성할 때 조심할 점은 $n$의 최대값이 $10^5$이기 때문에 인접 행렬로 그래프를 구성하면 메모리 공간이 $4 \times 10^{10} \ bytes= 40 \ GB$나 잡아먹기 때문에 메모리 초과가 날 수 밖에 없다. 그래서 인접 리스트로 그래프를 구성해야 한다.

## 시간 복잡도

인접 리스트의 BFS는 $O(n + e)$이다. $e$는 총 간선 개수이다.