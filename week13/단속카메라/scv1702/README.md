# 문제 풀이

## 문제 해설

각 자동차는 최소 한 번은 단속카메라를 만나야 한다. 즉, 차량의 진출 지점을 기준으로 해당 차량이 단속되어야 한다는 뜻이다. 그렇다면 모든 차량의 진출 지점에 카메라를 설치하면 조건을 만족할 것이다.

그런데 단속카메라의 개수를 최소로 해야 한다. 그러면 차량의 모든 진출 지점 중 단속카메라를 설치하지 않아도 되는 지점은 제외하면, 단속카메라의 개수는 최소가 될 것이다. 단속카메라를 설치하지 않아도 되는 지점은 해당 지점에 존재하는 차량들이 모두 이미 단속된 차량인 지점이다.

그래서 각 지점의 진출 지점에 대해 오름차순으로 정렬을 한 뒤, 해당 진출 지점이 단속카메라를 설치하지 않아도 되는 지점인지 판단했다.

## 시간 복잡도

주어진 차량의 대수가 $N$이라고 하면, $O(N^2)$이다.

## 개선

2차원 배열이라도 다음과 같이 정렬이 가능하다.

```java
Arrays.sort(routes, (r1, r2) -> r1[1] - r2[1]);
```

차량의 진출 지점을 기준으로 정렬을 한 뒤, 첫 단속카메라 설치 지점을 첫 차량의 진출 지점으로 둔다. 그리고 각 경로마다 진입 지점이 단속카메라 설치 지점보다 앞에 있는 경우 단속이 될 수 없기 때문에 해당 경로의 진출 지점을 다음 단속카메라 설치 지점으로 둔다. 경로의 진입 지점이 단속카메라 설치 지점보다 뒤에 있는 경우 이미 단속이 됐기 때문에 따로 설치할 필요가 없다.

```java
int c = Integer.MIN_VALUE;
for (int[] r: routes) {
    if (c < r[0]) {
        answer += 1;
        c = r[1];
    }
}
```

이를 통해 $O(N^2)$에서 $O(N)$으로 개선했다.