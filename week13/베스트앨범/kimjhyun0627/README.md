  # 문제 풀이

## 문제 해설

***람다식 정렬***

1. defaultdict 자료형을 이용해 genres와 plays를 index와 함께 딕셔너리형으로 묶어준다.
2. defaultdict에 아무 것도 없을 때까지 — 모든 장르에서 뽑아냈을 때까지 — 순회한다. sum을 통해 가장 많이 재생된 장르부터 조져준다. 노래가 하나밖에 없을 때 예외처리를 해주고, 두개 이상이라면 max를 통해 가장 많이 들은 노래의 index를 뽑아준 뒤 해당 노래를 삭제하고 다음 노래를 뽑아준다. 이후 해당 장르를 defaultdict에서 삭제한다.


## 시간 복잡도

$$O(len(genres))$$

