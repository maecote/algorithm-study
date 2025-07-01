# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.09 ~ 2025.06.15

## 사용 언어: JavaScript

---

### Day 3 (06.11)

- 🔗 문제: [2016년](https://school.programmers.co.kr/learn/courses/30/lessons/12901)
- 📁 코드: [2016년.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12901.%E2%80%852016%EB%85%84/2016%EB%85%84.js)
- 💡 메모: 월별 누적 날짜 수를 배열에 저장해두고 1워 1일부터 a월 b일까지의 날짜 수 - 1을 구한다. 그 값을 7로 나눈 인덱스에 해당하는 요일을 출력한다.
  ```js
  const YOIL = ["FRI", "SAT", "SUN", "MON", "TUE", "WED", "THU"];
  const DAYS = [0, 31, 60, 91, 121, 152, 182, 213, 244, 274, 305, 335, 366];

  const today = DAYS[a - 1] + b - 1;
  return YOIL[today % 7];
  ```

---

### Day 4 (06.12)

- 🔗 문제: [택배 상자 꺼내기](https://school.programmers.co.kr/learn/courses/30/lessons/389478#)
- 📁 코드: [택배 상자 꺼내기.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/389478.%E2%80%85%ED%83%9D%EB%B0%B0%E2%80%85%EC%83%81%EC%9E%90%E2%80%85%EA%BA%BC%EB%82%B4%EA%B8%B0/%ED%83%9D%EB%B0%B0%E2%80%85%EC%83%81%EC%9E%90%E2%80%85%EA%BA%BC%EB%82%B4%EA%B8%B0.js)
- 💡 메모: 택배 상자는 홀수 줄일 때 역순으로 배치된다. 꺼내야 하는 택배 상자의 위치 row와 col을 구하고, 규칙에 따라 값을 더해가면서 그 값이 n(창고에 있는 택배 수) 이상이 되면 반복문을 종료한다.
  ```js
  const A = 2 * col + 1;
  const B = 2 * (w - col - 1) + 1;
  ```
  짝수줄에서 홀수줄로 갈 때는 A를, 홀수줄에서 짝수줄로 갈 때는 B를 더한다. 매번 이동할 때마다 toggle을 바꿔 A, B 중 어느 것을 더할지 판단한다.
  ```js
  while (nowBox <= n) {
    const plus = toggle ? A : B;
    nowBox += plus;
    count++;
    toggle = !toggle;
  }
  ```
  규칙은 금방 찾을 수 있었지만 오답이 계속 떠서 계산식을 여러번 수정해야 했다.

---

### Day 7 (06.15)

- 🔗 문제: [직사각형 별찍기](https://school.programmers.co.kr/learn/courses/30/lessons/12969)
- 📁 코드: [직사각형 별찍기.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12969.%E2%80%85%EC%A7%81%EC%82%AC%EA%B0%81%ED%98%95%E2%80%85%EB%B3%84%EC%B0%8D%EA%B8%B0/%EC%A7%81%EC%82%AC%EA%B0%81%ED%98%95%E2%80%85%EB%B3%84%EC%B0%8D%EA%B8%B0.js)

- 🔗 문제: [3진법 뒤집기](https://school.programmers.co.kr/learn/courses/30/lessons/68935)
- 📁 코드: [3진법 뒤집기.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/68935.%E2%80%853%EC%A7%84%EB%B2%95%E2%80%85%EB%92%A4%EC%A7%91%EA%B8%B0/3%EC%A7%84%EB%B2%95%E2%80%85%EB%92%A4%EC%A7%91%EA%B8%B0.js)
- 💡 메모: 머리 식히려고 푼 간단한 문제들

---

## 📌 이번 주 회고

- 이번주는 문제 풀기 귀찮아서 단순 구현 문제만 찾아다녔다. 알고리즘 공부 해야하는데..
