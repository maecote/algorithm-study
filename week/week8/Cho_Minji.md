# 📘 Week 8 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.07.07 ~ 2025.07.13

## 사용 언어: JavaScript

---

### Day 1 (07.07)

- 🔗 문제: [배달](https://school.programmers.co.kr/learn/courses/30/lessons/12978)
- 📁 코드: [배달.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12978.%E2%80%85%EB%B0%B0%EB%8B%AC/%EB%B0%B0%EB%8B%AC.js)
- 💡 메모: 다익스트라. 1번 마을에서 K 시간 이하로 배달 가능한 마을 개수 구하는 문제. 큐에 [현재 마을, 현재까지 소요 시간] 형태로 저장하고, 현재 마을에서 연결된 마을을 순회하면서 새 경로가 더 짧으면 `distance`에 갱신 + 큐에 추가

---

### Day 3 (07.09)

- 🔗 문제: [가장 먼 노드](https://school.programmers.co.kr/learn/courses/30/lessons/49189)
- 📁 코드: [가장 먼 노드.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/49189.%E2%80%85%EA%B0%80%EC%9E%A5%E2%80%85%EB%A8%BC%E2%80%85%EB%85%B8%EB%93%9C/%EA%B0%80%EC%9E%A5%E2%80%85%EB%A8%BC%E2%80%85%EB%85%B8%EB%93%9C.js)
- 💡 메모: BFS. 1번 노드에서 가장 멀리 떨어진 노드의 개수 구하는 문제. 큐에서 노드를 하나씩 꺼내면서 인접 노드 순회하고 거리를 기록

---

### Day 4 (07.10)

- 🔗 문제: [디스크 트리](https://www.acmicpc.net/problem/7432)
- 📁 코드: [디스크 트리.js](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/7432.%E2%80%85%EB%94%94%EC%8A%A4%ED%81%AC%E2%80%85%ED%8A%B8%EB%A6%AC/%EB%94%94%EC%8A%A4%ED%81%AC%E2%80%85%ED%8A%B8%EB%A6%AC.js)
- 💡 메모: 트리. 디렉토리 경로들을 입력받아 디렉토리 구조를 출력하는 문제. 객체 참조에 대해 복습할 수 있었다.

---

### Day 5 (07.11)

- 🔗 문제: [문자열 폭발](https://www.acmicpc.net/problem/9935)
- 📁 코드: [문자열 폭발.js](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/9935.%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%ED%8F%AD%EB%B0%9C/%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%ED%8F%AD%EB%B0%9C.js)
- 💡 메모: 스택. 폭발 문자열이 문자열에 없을 때까지 제거하고 최종 문자열을 출력하는 문제. 문자를 하나씩 스택에 넣다가, 스택의 길이가 폭발 문자열의 길이 이상이고 마지막 문자가 폭발 문자열의 마지막 문자와 같을 때 폭발 문자열이 맞는지 비교한다. 일치하면 폭발 문자열의 길이만큼 스택에서 제거한다. 마지막에 스택 요소들 이어 붙여서 출력

---

### Day 7 (07.13)

- 🔗 문제: [최소비용 구하기](https://www.acmicpc.net/problem/1916)
- 📁 코드: [최소비용 구하기.js](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/1916.%E2%80%85%EC%B5%9C%EC%86%8C%EB%B9%84%EC%9A%A9%E2%80%85%EA%B5%AC%ED%95%98%EA%B8%B0/%EC%B5%9C%EC%86%8C%EB%B9%84%EC%9A%A9%E2%80%85%EA%B5%AC%ED%95%98%EA%B8%B0.js)
- 💡 메모: 다익스트라. 출발 도시에서 도착 도시까지 가는 최소 비용을 구하는 문제. Day1의 배달 문제처럼 일반 큐로 풀었다가 시간초과가 나서 우선순위큐로 풀었다. 오랜만에 작성하려니까 기억이 잘 나지 않았다.

---

## 📌 이번 주 회고

-
