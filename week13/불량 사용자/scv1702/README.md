# 문제 풀이

## 문제 해설

불량 사용자 아이디가 $m$개라고 할때, 응모자 아이디 $n$개 중 $m$개를 뽑아 해당 응모자 아이디 목록이 제재 아이디 목록이 될 수 있는지 검사한다. 해당 응모자 아이디 목록이 제재 아이디 목록이 되려면 불량 사용자 아이디 목록과 1:1 대응이 되어야 한다.

응모자 아이디 목록을 뽑는 것은 조합을 사용했고, 응모자 아이디 목록이 불량 사용자 아이디 목록과 1:1 대응 여부는 순열을 사용했다. 왜냐하면, 응모자 아이디 목록과 불량 사용자 아이디 목록의 대응이 순차적으로 이루어지지 않을 수 있기 때문이다. 응모자 아이디 목록과 불량 사용자 아이디 목록의 순열 중 하나라도 일치하는 경우가 있다면 1:1 대응이 가능한 경우이다.

다만, 이 알고리즘은 입력값이 매우 작기 때문에 가능할 것이다. 향후에 개선해보도록 하겠다.

## 시간 복잡도

각 조합의 경우의 수마다 순열을 계산하기 때문에 $O(2^n \times m!)$이다.