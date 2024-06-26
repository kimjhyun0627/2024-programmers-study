# 문제 풀이

## 문제 해설

오름차순에 대한 우선순위 큐와 내림차순에 대한 우선순위 큐 각각을 따로 두는 방식을 사용했다. 그리고 원소 제거를 위해 이중우선순위 큐에 존재하는 각 원소의 개수를 `HashMap`을 사용했고, 이중우선순위 큐가 비어있는지 판단하기 위해 `size` 변수를 사용했다. 

### 1. 원소 삽입

원소 삽입은 오름차순 큐와 내림차순 큐에 각각 삽입하고, 원소 개수와 큐의 크기를 증가시킨다.

```java
public void offer(int num) {
    min.offer(num);
    max.offer(num);
    counts.put(num, counts.getOrDefault(num, 0) + 1);
    size += 1;
}
```

### 2. 원소 제거

최대값 제거와 최소값 제거는 각각 내림차순 큐와 오름차순 큐에 적용된다는 것을 제외하면 로직은 동일하다. 최대값 제거를 예시로 들면, 내림차순 큐에서 제거한 원소가 이미 이중우선순위 큐에서 제거된 경우 해당 원소를 무시하기 위해 `counts.get(result) <= 0`가 아닐 때까지 내림차순 큐에서 계속 원소를 제거한다. 성공적으로 원소를 제거한 경우 이중우선순위 큐의 크기와 원소의 개수를 감소시킨다.

```java
public int pollMax() {
    int result = max.poll();
    while (counts.get(result) <= 0) {
        result = max.poll();
    }
    size -= 1;
    counts.put(result, counts.get(result) - 1);
    return result;
}
```

## 시간 복잡도

이중우선순위 큐에 존재하는 원소의 개수를 $N$이라고 할 때, 원소의 삽입은 $O(logN)$이다. 그러나 원소 제거의 경우 내림차순/오름차순 큐에 이미 제거된 원소가 많이 존재하는 경우 $O(\log{N})$보다 오래 걸린다. 최악의 경우는 내림차순/오름차순 큐에 존재하는 모든 원소가 이미 제거된 원소인 경우로 $O(N + \log{N})$이다. 전체 시간 복잡도는 주어진 연산에 따라 다르기 때문에, 일반적인 시간 복잡도를 파악하긴 어려울 것 같다.