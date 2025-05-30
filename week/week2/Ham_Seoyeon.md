# 📘 Week 2 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.26 ~ 2025.06.01

## 사용 언어: JavaScript

---

### Day 1 (05.26)

- 🔗 문제: [Lv 2) 피보나치 수 - 12945](https://school.programmers.co.kr/learn/courses/30/lessons/12945)
- 📁 코드: [무식한 풀이: 냅다 BigInt](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12945.%E2%80%85%ED%94%BC%EB%B3%B4%EB%82%98%EC%B9%98%E2%80%85%EC%88%98)
- 💡 메모: 지난 주에 공부한 재귀로도 풀어보고, 그냥 반복문으로도 풀어보고. 다 안 되는 게 숫자가 너무 커져서 그렇구나! 라면 보통 % 연산자를 써서 숫자 크기가 너무 안 커지게, 그때그때 나머지를 받아내서 풀었을 것이다. 하지만 너무도 상남자였던 나는 "그래, 숫자가 크단 말이지. 그럼 빅인트를 쓰면 되지 않겠나!" 하면서 럼주 마신 선장처럼 그렇게 n을 붙여 풀어버렸다 (...) 그래도 한 가지 알게된 건, **BigInt는 Number와 섞어서 연산할 수 없고, BigInt끼리만 연산 가능하다**는 것! ~~역시 사나이는 사나이를 알아보는 건가~~

### Day 2 (05.27)

- 🔗 문제: [LV 1) 가장 많이 받은 선물 - 258712](https://school.programmers.co.kr/learn/courses/30/lessons/258712)
- 📁 코드: [이게 레벨 1일 리가 없다 ~ 기나긴 객체 배열의 반복](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/258712.%E2%80%85%EA%B0%80%EC%9E%A5%E2%80%85%EB%A7%8E%EC%9D%B4%E2%80%85%EB%B0%9B%EC%9D%80%E2%80%85%EC%84%A0%EB%AC%BC)
- 💡 메모: 사실 그냥 제목이 귀여워서 들어갔다가 그렇지 않은 문제를 보고 기절할 뻔했다. 근데 너무 당황하지 말고 문제만 차근차근 정리하면 아주 어려운 건 아니었을 것 같긴 하다. 하지만 풀이 시간이 엄청 오래 걸렸다. / 대강 이름별로 객체를 만들어서 관련 정보를 모아 저장해주고 업데이트 했다. 음... 기억하고 싶은 건 reduce로 최소/최대값 구하는 방식이다. acc를 업데이트하는 걸 활용한 아래와 같은 방식인데... 뭔가 좋다.
  `arr.reduce((max, num) => max < num ? num : max, 0)`
  `arr.reduce((min, num) => min > num ? num : min, 0)`

### Day 3 (05.28)

- 오... 오늘 과제는 굉장한 Todo List였고 오후 8시 30분에 기절잠 해버렸다.

### Day 4 (05.29)

- 🔗 문제: [LV 1) 체육복 - 42862](https://school.programmers.co.kr/learn/courses/30/lessons/42862)
- 📁 코드: [filter로 요소 제거해주기](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/42862.%E2%80%85%EC%B2%B4%EC%9C%A1%EB%B3%B5)
- 💡 메모: 이 사람 문제 또 끝까지 안 읽었다. "여별 체육복 가져왔어도 도난당했으면 남 못 빌려줌"이란 조건을 놓쳐서 해당 조건을 추가하여 다시 풀었다. **제발 문제 좀 제대로 읽자!**

### Day 5 (05.30)

- 🔗 문제: [Lv 0) 옹알이 (1) - 120956](https://school.programmers.co.kr/learn/courses/30/lessons/120956)
- 📁 코드: ["/"로 replace 후 every char가 "/"인지 확인](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/0/120956.%E2%80%85%EC%98%B9%EC%95%8C%EC%9D%B4%E2%80%85%EF%BC%881%EF%BC%89)
- 💡 메모: 음... 뭔가 아기가 발음할 수 있는 문자열 부분을 "/"로 replace하고, 그래서 문자열의 모든 char가 every를 써서 "/"로만 구성되어 있는지, 그렇다면 result++ 식으로 풀었는데... 탐탁지 않아서 스터디원 분들의 생각과 아이디어를 여쭈었다.

### Day 6 (05.31)

- 🔗 문제: [Lv 2)]()
- 📁 코드: []()
- 💡 메모:

### Day 7 (06.01)

- 🔗 문제: [재현퀘스트 <재귀편>](https://github.com/maecote/algorithm-study/blob/main/quest/quest3/quest3.md)
- 📁 코드 1: [기초문제 - 재귀 연습](https://github.com/makee-ham/algo-gogo/tree/main/other-algorithms/recursive-basic)
- 📁 코드 2: [도전문제 - '삼총사' 재귀로 풀기](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131705.%E2%80%85%EC%82%BC%EC%B4%9D%EC%82%AC)
- 💡 메모:

---

## 📌 이번 주 회고

- 약간 뇌가 지친 느낌...?
