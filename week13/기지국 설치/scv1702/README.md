# 문제 풀이

## 문제 해설

각 기지국 사이의 전파가 안통하는 아파트 개수를 구한 뒤, 이를 $2w + 1$로 나누었다. $2w + 1$은 기지국 하나를 설치할 때 전파가 통하는 아파트 개수이다. 이때 주의할 점은, 나누어 떨어지지 않는 경우 전파가 안통하는 아파트 개수가 나머지 만큼 남기 때문에 기지국을 하나 더 설치해야 한다.

## 시간 복잡도

주어진 기지국 개수를 $S$라고 할 때 $O(S)$이다.