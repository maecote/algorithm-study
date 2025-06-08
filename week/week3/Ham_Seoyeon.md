# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.02 ~ 2025.06.08

## 사용 언어: JavaScript

---

### Day 1 (06.02)

- 🔗 문제: [Lv 1) 피보나치 수 - 12945](https://school.programmers.co.kr/learn/courses/30/lessons/131128)
- 📁 코드: [재현 퀘스트 - 빈도수 세기 패턴 활용](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131128.%E2%80%85%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D)
- 💡 메모: 문제가 있다. 성능이 너무 좋지 않다. (메모리: 206 MB, 시간: 781.22 ms) 아직 시간 복잡도를 측정하는 방법을 모르는데, **_다음 주 스터디 시간에 내 코드의 문제점, 시간 복잡도 줄일 개선 방법 등을 스터디원 분들께 여쭈어야 할 것 같다._** [코드](https://github.com/makee-ham/algo-gogo/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131128.%E2%80%85%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D/%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D.js)

### Day 2 (06.03)

- (선거일이라서 인천 놀러갔다 왔어요ㅎㅎ 다녀와서 심화반 플젝만 했네요ㅠㅠ)

### Day 3 (06.04)

- 🔗 문제: [11. Container With Most Water(Med. level)](https://leetcode.com/problems/container-with-most-water/description/?envType=problem-list-v2&envId=two-pointers)
- 📁 코드: [재현퀘스트 - 다중 포인터 활용 Two Pointers 알고리즘 적용](https://github.com/makee-ham/algo-gogo/tree/main/0011-container-with-most-water)
- 💡 메모: 이번엔 방법 설계를 비교적 금방 했다! left랑 right index-pointer를 잡고, max 값을 업데이트 해가며 greedy하게? left index < right index일 동안의 경우를 전부 탐색했다! 공부한 걸 바로 적용하니 너무 재밌다. LeetCode 여기 문제 되게 좋네! 자주 가봐야겠다.

### Day 4 (06.05)

- 🔗 문제: [LV 1) 크기가 작은 부분문자열 - 147355](https://school.programmers.co.kr/learn/courses/30/lessons/147355)
- 📁 코드: [재현퀘스트 - sliding window pattern 과제 (리팩토링했더니 '브루트 포스 스타일 슬라이딩 윈도우'라는 혼종의 탄생 - 암튼 브루트 포스인데 이 경우에선 시간/메모리 성능 더 나음)](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/147355.%E2%80%85%ED%81%AC%EA%B8%B0%EA%B0%80%E2%80%85%EC%9E%91%EC%9D%80%E2%80%85%EB%B6%80%EB%B6%84%EB%AC%B8%EC%9E%90%EC%97%B4)
- 💡 메모: "음... 굳이 배열로 바꿨어야 했나? 메모리야 미안해..." 라는 생각에 나름대로 리팩토링 진행. 애초에 p의 길이만큼 문자열을 substring하고 이를 전체 문자열 길이에 p의 길이를 뺀 만큼 반복하여(어차피 뒤까지 빼오니까) 구했는데... 써보고 나니 이거, brute force인 것 같다...? <u>sliding window의 핵심은 "계산한 값을 **_누적_**해서 관리하는 것"에 있다.</u> window를 쭉쭉 밀면서 빠져나간 값은 빼고 새로 들어온 값은 더하고, 그런 식으로. 그런데 내가 한 두 번째 리팩토링(?) 버전은 "모든 i에 대해 t.substring(i, i + p.length)를 매번 잘라서 숫자로 바꿔서 비교"하기 때문에 **_윈도우마다 완전히 처음부터 새로 계산하는 구조_** 여서 brute force이면서도 생긴 건 또 p.length씩 슬라이드하는 구조이다. (그렇다. 이건 그냥 brute force이다.) 그런데 테스트 케이스가 이상한 건지 여기서는 brute force의 성능이 미묘하게 더 좋았다. 5ms랑 1MB 차이!...
- 참고: 그냥 아무것도 믿을 수 없다... 제출할 때마다 다르게 나온다(이미지 참고)... _난 이제 프로그래머스 불신증에 걸리고 말았다..._
  ![뭐시여](image.png)

### Day 5 (06.06) + Day 6 (06.07)

- 6일에 신나게 놀고(+진격거 덕톡회) 7일 일정 수행 후 기절(또 16시간을...)해버림...^^b

### Day 7 (06.08)

- 🔗 문제: [merge sort 순수함수로 구현해보기 by. 재현 님](https://stackblitz.com/edit/stackblitz-starters-2axlbocx?file=index.js)
- 📁 코드: [재현퀘스트- 분할정복기초: merge sort 순수함수로 구현](https://github.com/makee-ham/algo-gogo/tree/main/other-algorithms/merge-sort-with-divide-and-conquer)
- 💡 메모: 음... 뭔가 영상에서 나왔던 대로, merge 함수에서는 arr 두 개를 크기 비교해가며 쇽쇽 다른 arr에 넣고 그 arr을 반환했고... merge sort 함수에서는 최대한 쪼개도록 middle index를 잡고 재귀를 돌렸다. 아직 확실히 이해된 게 아닌 느낌이라, 다음에 다시 해봐야겠다!

---

## 📌 이번 주 회고

- 이번 주는 재현 퀘스트만 공부했던 거 같은데, 엄청 알찼다! 이렇게 저렇게 재귀라든가 포인터라든가가 분할 정복에서 똬! 합쳐져서 엄청 짜릿했다!
- 리트 코드 문제는 처음 풀어봤는데 깔끔하고 좋았다. 알고리즘 유형별로도 있어서, 추후 알고리즘을 연습하고 적용할 때엔 리트 코드를 적극 활용해봐야겠다!
