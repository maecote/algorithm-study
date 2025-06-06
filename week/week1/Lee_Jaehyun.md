# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.19 ~ 2025.05.25

## 사용 언어: JavaScript

---

### Day 1 (05.20)

- 🔗 문제: [388353.지게차와 크레인](https://school.programmers.co.kr/learn/courses/30/lessons/388353)
- 📁 코드: [lv2.지게차와 크레인](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/388353.%E2%80%85%EC%A7%80%EA%B2%8C%EC%B0%A8%EC%99%80%E2%80%85%ED%81%AC%EB%A0%88%EC%9D%B8)
- 💡 메모: 해쉬맵을 통해 중복 탐색을 줄이는 기법과 접근 가능성에 대해 BFS로 탐색하는 문제. 처음에 DFS로 풀었는데 효율성 문제에 걸렸다. BFS로 푸니 효율성 테스트를 통과 했다. 어차피 모든 가능성을 탐색하는 것이 아니라 가장 짧은 경로로 접근가능만 하면 되기 때문. 근데 생각해보면 어차피 워스트 케이스 시간복잡도는 똑같다.

### Day 2 (05.22)

- 🔗 문제: [68646.풍선 터트리기](https://school.programmers.co.kr/learn/courses/30/lessons/68646)
- 📁 코드: [lv3.풍선 터트리기](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/68646.%E2%80%85%ED%92%8D%EC%84%A0%E2%80%85%ED%84%B0%ED%8A%B8%EB%A6%AC%EA%B8%B0)
- 💡 메모: 처음엔 dfs로 풀려고 했다가 조건에서 배열 최대 길이가 백만인 것을 보고 안될 것이라고 생각했다. 그래서 특정 숫자를 남길 수 있는 조건이 있을 것이라고 생각을 했다. 결론적으로 k번째 숫자를 남기고 싶으면 첫번째부터 k-1번째까지의 숫자에서의 최솟값과 k+1번째에서 마지막까지의 숫자에서의 최솟값 중 둘 중 하나만 k번째 숫자보다 크면 된다.

처음엔 이중반복문을 사용했는데 시간복잡도가 너무 컸다. 이후에는 특정 구간에서의 최소값을 저장해두는 2차원 배열을 사용한 DP를 사용했는데 이건 공간복잡도가 너무 커서 통과하지 못했다.

다시 생각해보니 DP를 사용할 때 모든 특정 구간에서의 최소값을 저장해둘 필요가 없고 특정 인덱스부터 마지막까지 사이에서의 최소값만 저장해두면 된다는 것을 깨달았다. 그래서 1차원 배열을 사용한 DP를 이용해 문제를 푸니 문제가 해결되었다.

---

## 📌 이번 주 회고

- 이번주는 정처기도 준비하고, 과제도 많고, 심화반 프로젝트도 시작하느라 개인문제를 2개 밖에 못 풀었다. 그래도 "난 매주 공용문제 준비하니까 괜찮지 않을까?"라고 자기합리화 하지만 그래도 문제는 더 풀긴 풀어야한다.
