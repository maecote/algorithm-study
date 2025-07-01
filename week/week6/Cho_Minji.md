# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.23 ~ 2025.06.29

## 사용 언어: JavaScript

---

### Day 5 (06.27)

- 🔗 문제: [하노이의 탑](https://school.programmers.co.kr/learn/courses/30/lessons/12946)
- 📁 코드: [하노이의 탑.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12946.%E2%80%85%ED%95%98%EB%85%B8%EC%9D%B4%EC%9D%98%E2%80%85%ED%83%91/%ED%95%98%EB%85%B8%EC%9D%B4%EC%9D%98%E2%80%85%ED%83%91.js)
- 💡 메모: 유튜브 영상으로 하노이의 탑 재귀 공식을 이해한 뒤에 풀었다.

  - 기저 조건 num===1: 원반이 1개면 from에서 to로 이동한다.
  - 재귀:
    - 위의 num-1개의 원반을 from에서 via(중간 기둥)로 이동 `hanoi(num - 1, from, via, to, arr)`
    - 가장 큰 원반을 to로 이동 `arr.push([from, to])`
    - via에 있던 원반을 to로 이동 `hanoi(num - 1, via, to, from, arr)`

- 🔗 문제: [정수 삼각형](https://school.programmers.co.kr/learn/courses/30/lessons/43105)
- 📁 코드: [정수 삼각형.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/43105.%E2%80%85%EC%A0%95%EC%88%98%E2%80%85%EC%82%BC%EA%B0%81%ED%98%95/%EC%A0%95%EC%88%98%E2%80%85%EC%82%BC%EA%B0%81%ED%98%95.js)
- 💡 메모: 다이나믹 프로그래밍. 이것도 [유튜브 참고](https://www.youtube.com/watch?v=0bqfTzpWySY&t=439s)
  현재 위치에 도달 가능한 최대 합을 누적한다. 삼각형 마지막 줄에서 가장 큰 값을 출력한다.

---

### Day 6 (06.28)

- 🔗 문제: [쿼드압축 후 개수 세기](https://school.programmers.co.kr/learn/courses/30/lessons/68936)
- 📁 코드: [쿼드압축 후 개수 세기.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/68936.%E2%80%85%EC%BF%BC%EB%93%9C%EC%95%95%EC%B6%95%E2%80%85%ED%9B%84%E2%80%85%EA%B0%9C%EC%88%98%E2%80%85%EC%84%B8%EA%B8%B0/%EC%BF%BC%EB%93%9C%EC%95%95%EC%B6%95%E2%80%85%ED%9B%84%E2%80%85%EA%B0%9C%EC%88%98%E2%80%85%EC%84%B8%EA%B8%B0.js)
- 💡 메모: 분할정복+재귀. 무난하게 풀었음

---

### Day 7 (06.29)

- 🔗 문제: [N개의 최소공배수](https://school.programmers.co.kr/learn/courses/30/lessons/12953)
- 📁 코드: [N개의 최소공배수.js](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12953.%E2%80%85N%EA%B0%9C%EC%9D%98%E2%80%85%EC%B5%9C%EC%86%8C%EA%B3%B5%EB%B0%B0%EC%88%98/N%EA%B0%9C%EC%9D%98%E2%80%85%EC%B5%9C%EC%86%8C%EA%B3%B5%EB%B0%B0%EC%88%98.js)
- 💡 메모: 유클리드 호제법은 맨날 까먹어서 맨날 다시 찾아본다. 이제 좀 기억하길 바라며 정리 ->
  > - 유클리드 호제법: 최대공약수(GCD)를 구하는 알고리즘. b가 0이 될 때까지 GCD(b, a%b)를 재귀 호출. b가 0일 때 a값이 두 수의 최대공약수
  > - 최소공배수(LCM): 두 수의 곱 / 두 수의 최대공약수

---

## 📌 이번 주 회고

- 일주일 안풀다가 푸니까 약간 재밌는 것 같기도 하고 아닌 것 같기도 하고.. 아무튼 다시 열심히 풀어봅시다 화이팅
