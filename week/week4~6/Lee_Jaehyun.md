📘 Week 4 ~ 6 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.09 ~ 2025.06.30

## 사용 언어: JavaScript

---

### Day 1 (06.09)

- 🔗 문제: [64062.징검다리 건너기](https://school.programmers.co.kr/learn/courses/30/lessons/64062)
- 📁 코드: [lv3.징검다리 건너기](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/64062.%E2%80%85%EC%A7%95%EA%B2%80%EB%8B%A4%EB%A6%AC%E2%80%85%EA%B1%B4%EB%84%88%EA%B8%B0)

- 💡 메모: 이분탐색 알고리즘.

---

### Day 2(06.10)

- 🔗 문제: [340212.퍼즐 게임 챌린지](https://school.programmers.co.kr/learn/courses/30/lessons/340212)
- 📁 코드: [lv2.퍼즐 게임 챌린지](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/340212.%E2%80%85%EF%BC%BBPCCP%E2%80%85%EA%B8%B0%EC%B6%9C%EB%AC%B8%EC%A0%9C%EF%BC%BD%E2%80%852%EB%B2%88%E2%80%85%EF%BC%8F%E2%80%85%ED%8D%BC%EC%A6%90%E2%80%85%EA%B2%8C%EC%9E%84%E2%80%85%EC%B1%8C%EB%A6%B0%EC%A7%80)

- 💡 메모: 이분탐색 알고리즘.

---

### Day 3(06.24)

- 🔗 문제: [340213.동영상 재생기](https://school.programmers.co.kr/learn/courses/30/lessons/340213)
- 📁 코드: [lv1.동영상 재생기](https://github.com/JaeHyunLee123/coding-test/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/340213.%E2%80%85%EF%BC%BBPCCP%E2%80%85%EA%B8%B0%EC%B6%9C%EB%AC%B8%EC%A0%9C%EF%BC%BD%E2%80%851%EB%B2%88%E2%80%85%EF%BC%8F%E2%80%85%EB%8F%99%EC%98%81%EC%83%81%E2%80%85%EC%9E%AC%EC%83%9D%EA%B8%B0)

- 💡 메모: 구현 문제. 1단계치고는 어렵긴한데 특별한 알고리즘 지식이 필요한 문제는 아니다. 거의 보름만의 문제풀이...

---

### Day 4(06.26)

- 🔗 문제: [2470. Removing Stars From a String](https://leetcode.com/problems/removing-stars-from-a-string)
- 📁 코드: [Removing Stars From a String](https://github.com/JaeHyunLee123/coding-test/tree/main/2470-removing-stars-from-a-string)

- 💡 메모: 스택문제

---

### Day 5(06.30)

- 🔗 문제: [Jump Game](https://leetcode.com/problems/jump-game)
- 📁 코드: [Jump Game](https://github.com/JaeHyunLee123/coding-test/tree/main/0055-jump-game)

- 💡 메모: 접근 방식이 완전히 틀린 문제. 나는 재귀를 사용해 앞에서부터 모든 가능성을 탐색했는데, 정답코드는 뒤에서부터 가능한 하나의 수만 체크한다. (문제풀이에 도움주신 민지님 감사드립니다.)

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

---

## 📌 이번 주 회고

- 최근 문제풀이를 소홀히 했더니 감을 많이 잃었다. 다시 열심히 풀어보자
