  # 문제 풀이

## 문제 해설

***누적합***

*발상 자체가 미친 것 같은 문제…*
*카카오 아무나 가는거 아니구나*

*누적합을 이용하면 네 모서리만 체크해준 후 한 번의 순회로 누적합 계산을 통해 모든 board 칸의 값들을 계산가능하다*

1. 누적 합 계산을 위해 기존 board보다 1칸씩 더 큰 2차원 list를 생성한다.
2. skill에 대해 순회한다. type에 따라 degree값의 부호 처리를 해준 후 (r1,c1) 자리와 (r2+1, c2+1) 자리에는 degree를 더해주고 (r2+1, c1) 자리와 (r1, c2+1) 자리에는 degree를 빼준다.
3. row와 col에 대해 한 번씩 누적합 list를 순회하며 값을 채워준다.
4. board를 마지막으로 한 번 순회하며 양수인 값의 개수를 반환한다.


## 시간 복잡도

$$O(skill+n*m)$$

