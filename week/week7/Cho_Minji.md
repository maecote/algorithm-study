# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.30 ~ 2025.07.06

## 사용 언어: JavaScript

---

### Day 1 (06.30)

- 🔗 문제: [카펫](https://school.programmers.co.kr/learn/courses/30/lessons/42842)
- 📁 코드: [카펫.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42842.%E2%80%85%EC%B9%B4%ED%8E%AB/%EC%B9%B4%ED%8E%AB.js)
- 💡 메모: 공식 찾으면 간단한 문제. 갈색 격자의 수는 노란색 영역의 가로 _ 세로 _ 2 + 4(모서리)이다. 가로 _ 세로의 값으로 정리하면 `b` / 2 - 2이고 이를 `rowCol` 변수에 담았다. `row` = 1, `col` = `rowCol` - 1부터 시작해서 `row` _ `col` 값이 `y`가 되는 경우를 찾는다.

---

### Day 2 (07.01)

- 🔗 문제: [오픈채팅방](https://school.programmers.co.kr/learn/courses/30/lessons/42888)
- 📁 코드: [오픈채팅방.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42888.%E2%80%85%EC%98%A4%ED%94%88%EC%B1%84%ED%8C%85%EB%B0%A9/%EC%98%A4%ED%94%88%EC%B1%84%ED%8C%85%EB%B0%A9.js)
- 💡 메모: 출력을 어떻게 할지 고민하다가 result 배열에 [id, 메시지] 형태로 담고 마지막에 result.map(v => nickname[v[0]] + v[1])으로 최종 아이디를 적용시켰다.

---

### Day 3 (07.02)

- 🔗 문제: [여행경로](https://school.programmers.co.kr/learn/courses/30/lessons/43164?language=javascript)
- 📁 코드: [여행경로.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/43164.%E2%80%85%EC%97%AC%ED%96%89%EA%B2%BD%EB%A1%9C/%EC%97%AC%ED%96%89%EA%B2%BD%EB%A1%9C.js)
- 💡 메모: 출발지 기준으로 도착지를 사전순으로 정렬하고 방문 여부를 배열로 관리. DFS로 경로를 탐색하는데 이때 현재 출발지와 여행 경로를 함께 전달한다. `path.length === total + 1`이면 path를 정답으로 저장하고 탬색을 중단한다.

---

### Day 4 (07.03)

- 🔗 문제: [피보나치 수 6](https://www.acmicpc.net/problem/11444)
- 📁 코드: [피보나치 수 6.js](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/11444.%E2%80%85%ED%94%BC%EB%B3%B4%EB%82%98%EC%B9%98%E2%80%85%EC%88%98%E2%80%856/%ED%94%BC%EB%B3%B4%EB%82%98%EC%B9%98%E2%80%85%EC%88%98%E2%80%856.js)
- 💡 메모: 입력값이 엄청 커서 BigInt 써야함. 이미 계산한 값은 map에 저장해서 재시용

---

### Day 5 (07.04)

- 🔗 문제: [네트워크](https://school.programmers.co.kr/learn/courses/30/lessons/43162)
- 📁 코드: [네트워크.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/43162.%E2%80%85%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC.js)
- 💡 메모: i=0~n-1까지 아직 방문하지 않은 컴퓨터에서 DFS를 실행시키고 count를 증가시킨다.

---

## 📌 이번 주 회고

- 이번주는 문제 푸는게 재밌었다. 여전히 어렵지만 두 달 전보다 성장하고 있다는 느낌이 들었다.
