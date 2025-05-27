# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.19 ~ 2025.05.25  
## 사용 언어: JavaScript

---

### Day 1 (05.19)

- 🔗 문제: [N번째 큰수](https://www.acmicpc.net/problem/2075)
- 📁 코드: [2075. N번째 큰 수](https://github.com/minji105/algorithm/tree/main/%EB%B0%B1%EC%A4%80/Silver/2075.%E2%80%85N%EB%B2%88%EC%A7%B8%E2%80%85%ED%81%B0%E2%80%85%EC%88%98)
- 💡 메모: N*N의 표에서 N번째 큰 수를 찾는 문제입니다. 최소힙을 사용해 쉽게 풀 수 있었습니다. 표의 숫자를 하나씩 힙에 넣는데 힙의 크기가 N이 되고 숫자가 힙의 최솟값보다 크면 최솟값을 제거하고 숫자를 삽입합니다. 마지막엔 힙에 가장 큰 N개의 수만 남고 그 중 가장 작은 값이 N번째 큰 수입니다. 
  

---

### Day 4 (05.22)

- 🔗 문제: [도키도키 간식드리미](https://www.acmicpc.net/problem/12789)
- 📁 코드: [12789. 도키도키 간식드리미](https://github.com/minji105/algorithm/tree/main/%EB%B0%B1%EC%A4%80/Silver/12789.%E2%80%85%EB%8F%84%ED%82%A4%EB%8F%84%ED%82%A4%E2%80%85%EA%B0%84%EC%8B%9D%EB%93%9C%EB%A6%AC%EB%AF%B8)
- 💡 메모: 중간중간에 스택에서 꺼내는 경우도 고려해야 합니다. 수를 순서대로 확인하며 order와 일치하지 않으면 스택에 넣고 일치하면 order를 1 증가 시킵니다. 스택의 top이 order와 같을 때마다 pop을 진행합니다.

---

### Day 6 (05.24)

- 🔗 문제: [삼총사(재귀 도전문제)](https://school.programmers.co.kr/learn/courses/30/lessons/131705)
- 📁 코드: [131705. 삼총사](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131705.%E2%80%85%EC%82%BC%EC%B4%9D%EC%82%AC/%EC%82%BC%EC%B4%9D%EC%82%AC.js)
- 💡 메모: 번호 조합을 배열로 저장하면서 그 길이가 3이 되면 reduce로 합을 계산하고 0이면 count를 증가시킵니다. 다음 인덱스 값과 새로운 배열을 재귀로 호출하여 다음 숫자를 선택합니다. 재귀를 호출할 때마다 배열을 복사하고 있는데, 이 부분은 더 나은 방법이 있을 것 같습니다.

---

### Day 7 (05.25)

- 🔗 문제: [별 찍기 - 10](https://www.acmicpc.net/problem/2447)
- 📁 코드: [2447. 별 찍기 － 10](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/2447.%E2%80%85%EB%B3%84%E2%80%85%EC%B0%8D%EA%B8%B0%E2%80%85%EF%BC%8D%E2%80%8510/%EB%B3%84%E2%80%85%EC%B0%8D%EA%B8%B0%E2%80%85%EF%BC%8D%E2%80%8510.js)
- 💡 메모: 재귀적으로 별 패턴을 출력하는 문제입니다. 처음에는 문자열을 이어붙이는 방식으로 했었는데 줄바꿈 처리가 잘 되지않아 배열을 사용했습니다. N이 1일 경우 ['*']를 반환하지고, N을 3으로 나눈 값을 기준으로 재귀적으로 이전 단계의 별 패턴을 생성합니다.

---

## 📌 이번 주 회고
- 재귀로 로직을 구현하는 게 아직 익숙하지 않아 좀 더 연습이 필요하다고 느꼈습니다.