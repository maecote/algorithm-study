# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.30 ~ 2025.07.4

## 사용 언어: JavaScript

---

### Day 1(06.30)

- 🔗 문제: [Jump Game](https://leetcode.com/problems/jump-game)
- 📁 코드: [Jump Game](https://github.com/JaeHyunLee123/coding-test/tree/main/0055-jump-game)

- 💡 메모: 접근 방식이 완전히 틀린 문제. 나는 재귀를 사용해 앞에서부터 모든 가능성을 탐색했는데, 정답코드는 뒤에서부터 가능한 하나의 수만 체크한다. (문제풀이에 도움주신 민지님 감사드립니다.)

- 이번주에 올려야하는 것은 지난주에 잘못 올렸어서 중복으로 다시 올립니다.

```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var canJump = function (nums) {
  let pos = nums.length - 1;
  for (let i = nums.length - 2; i >= 0; i--) {
    if (nums[i] + i >= pos) {
      pos = i;
    }
  }

  return pos === 0;
};
```

### Day 2 (07.01)

- 🔗 문제: [12904.가장 긴 팰린드롬](https://school.programmers.co.kr/learn/courses/30/lessons/12904)
- 📁 코드: [lv3.가장 긴 팰린드롬](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/12904.%E2%80%85%EA%B0%80%EC%9E%A5%E2%80%85%EA%B8%B4%E2%80%85%ED%8C%B0%EB%A6%B0%EB%93%9C%EB%A1%AC)
- 💡 메모: sliding window 패턴 + 투포인터 응용, 난이도는 쉽다. 1단계 정도?

### Day 3 (07.02)

- 🔗 문제: [67259.경주로 건설](https://school.programmers.co.kr/learn/courses/30/lessons/67259)
- 📁 코드: [lv3.경주로 건설](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/67259.%E2%80%85%EF%BC%BB%EC%B9%B4%EC%B9%B4%EC%98%A4%E2%80%85%EC%9D%B8%ED%84%B4%EF%BC%BD%E2%80%85%EA%B2%BD%EC%A3%BC%EB%A1%9C%E2%80%85%EA%B1%B4%EC%84%A4)
- 💡 메모: 넓이 우선 탐색. 방문한 좌표에 어떤 방향으로 도착했는지도 저장해두는 것이 핵심. 이런 발상이 처음에 안 나와서 어려웠다. 처음엔 깊이우선으로 탐색해서 잘 안됐었다.

### Day 4 (07.03)

- 🔗 문제: [42883. 큰 수 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/42883)
- 📁 코드: [lv2.큰 수 만들기](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42883.%E2%80%85%ED%81%B0%E2%80%85%EC%88%98%E2%80%85%EB%A7%8C%EB%93%A4%EA%B8%B0)
- 💡 메모: 스택 활용 문제. 생각보다 어려웠다. 스택을 활용한다는 접근을 처음에 하지 못했다.

### Day 5 (07.04)

- 🔗 문제: [132266. 부대복귀](https://school.programmers.co.kr/learn/courses/30/lessons/132266)
- 📁 코드: [lv3.부대복귀](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/132266.%E2%80%85%EB%B6%80%EB%8C%80%EB%B3%B5%EA%B7%80)
- 💡 메모: 그래프 문제. 처음엔 2차원 배열을 사용한 그래프를 만들었는데, 오히려 어려웠다. 인접 리스트 방식으로 문제를 푸니 잘 풀렸다.

---

## 📌 이번 주 회고

- 예전에는 그냥 문제를 풀었는데, 문제를 많이 풀다 보니 이젠 머리 속에 있는 유형이 아니면 접근법이 잘 떠오르지 않는다. 도구를 많이 익혀둬서 새로운 도구를 익히기보다는 원래 있는 도구로만 문제를 해결하려고 하는 듯한 느낌. 아무래도 새로운 접근법을 사용하려면 에너지를 많이 써야해서 그런 것 같다. 결국은 게으름 문제.
