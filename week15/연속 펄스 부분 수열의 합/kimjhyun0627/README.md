  # 문제 풀이

## 문제 해설

***dp***

1. 1로 시작하는 펄스 함수, -1로 시작하는 펄스 함수를 곱한 list를 생성해준다.
2. dp도 똑같이 2개 만들어준다.
3. 가중치를 곱한 두 list에 대해 dp 순회한다. 부분수열의 최대 합을 구한다.
4. 두 dp list의 가장 큰 값을 비교해 더 큰 값을 반환한다.


## 시간 복잡도

$$O(sequence)$$

