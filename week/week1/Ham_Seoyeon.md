# 📘 Week 1 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.19 ~ 2025.05.25

## 사용 언어: JavaScript

---

### Day 1 (05.19)

- 🔗 문제: [Lv 2) 12941. 최솟값 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12941)
- 📁 코드: [sort를 이용한 풀이](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12941.%E2%80%85%EC%B5%9C%EC%86%9F%EA%B0%92%E2%80%85%EB%A7%8C%EB%93%A4%EA%B8%B0)
- 💡 메모: 가장 큰 수는 가장 작은 수, 그 다음 큰 수는 그 다음 작은 수와 짝 지어 곱하면 최솟값을 만들 수 있으니, 배열 둘 중 하나는 오름차순, 하나는 내림차순으로 정렬하여 답을 구했다. 생각해보니 reduce를 써도 좋았을 것 같다.

### Day 2 (05.20)

- 🔗 문제: [LV 2) 12951. JadenCase 문자열 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/12951)
- 📁 코드: [split의 향연](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12951.%E2%80%85JadenCase%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%EB%A7%8C%EB%93%A4%EA%B8%B0)
- 💡 메모: 문자열을 wordArr로 공백 기준 한 번 쪼개고, 반복문 안에서 word를 character로 쪼개서 처리했다. 문자열 s가 있을 때 s.toUpperCase() 하면 그 결과로 새로운 문자열만 반환하지 기존 문자열 s에 변화가 생기진 않는다는 걸 다시금 깨달았다. 잊지 말자, 문자열은 _immutable_...

### Day 3 (05.21)

- 🔗 문제: [Lv 2) 70129. 이진 변환 반복하기](https://school.programmers.co.kr/learn/courses/30/lessons/70129)
- 📁 코드: ['길이'는 곧 '개수', 이 사실에 Number.toString(n진수) 곁들이기](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/70129.%E2%80%85%EC%9D%B4%EC%A7%84%E2%80%85%EB%B3%80%ED%99%98%E2%80%85%EB%B0%98%EB%B3%B5%ED%95%98%EA%B8%B0)
- 💡 메모: **문제를 똑바로 읽자.** 제발 좀, 문제에 단서랑 답이 다 있다. 시간 초과하면 오답 하면 된다. 마음 편하게 차근차근 문제를 풀자.

### Day 4 (05.22)

- 🔗 문제: [Lv 2) 12924. 숫자의 표현](https://school.programmers.co.kr/learn/courses/30/lessons/12924)
- 📁 코드: [민지 님의 투 포인터와 재민 님의 반갈죽(?)의 결합](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12924.%E2%80%85%EC%88%AB%EC%9E%90%EC%9D%98%E2%80%85%ED%91%9C%ED%98%84)
- 💡 메모: js 코드를 보면 나의 투쟁(...)을 볼 수 있다. 배열로 멋지게 풀었다가 효율성 망하고, 원시값으로 풀었다가 효율성 망하고, 결국 스터디원 분들께 물어물어 "투 포인터 + 반까지만 계산해도 됨"을 알아서 겨우 풀 수 있었다... 다음에 재도전하자.

### Day 5 (05.23)

- 🔗 문제: [Lv 2) 12911. 다음 큰 숫자](https://school.programmers.co.kr/learn/courses/30/lessons/12911)
- 📁 코드: [정규표현식 외워야 하나 너무 편하다](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12911.%E2%80%85%EB%8B%A4%EC%9D%8C%E2%80%85%ED%81%B0%E2%80%85%EC%88%AB%EC%9E%90)
- 💡 메모: 그냥 딱 보자마자 Ah! regex 각! 하고 Number.toString(2) 고거랑 match(/1/g) 하고 length 구했더니 고마 쉽다. 멋지고 간편한데 생긴 게 무서워서 외울 엄두가 안 나는 정규표현식... 시간 나면 들여다 봐야겠다!

### Day 6 (05.24)

- 평일의 피로 + 주간 일정 수행 후 뻗어서 무려 16시간 수면으로 하루를 스킵하다.......🥲

### Day 7 (05.25)

- 🔗 문제: [재현퀘스트 <재귀편>](https://github.com/maecote/algorithm-study/blob/main/quest/quest3/quest3.md)
- 📁 코드 1: [기초문제 - 재귀 연습](https://github.com/makee-ham/algo-gogo/tree/main/other-algorithms/recursive-basic)
- 📁 코드 2: [도전문제 - '삼총사' 재귀로 풀기](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131705.%E2%80%85%EC%82%BC%EC%B4%9D%EC%82%AC)
- 💡 메모: 재귀 알고리즘은 Base Case로 stop condition을 정하고, Recursive Case에서 재귀를 돌리는데 이는 반드시 Base Case의 stop condition을 향해 수렴해야 한다. 이 로직은 문제를 쪼개어 푸는 것과 관련이 있으며, 중첩 반복문을 이용해 푸는 모든 문제는 재귀 알고리즘으로도 구현이 가능하다.

---

## 📌 이번 주 회고

- 전반적으로, 시간 내에 푼다는 생각 때문에 "문제 분석", "해법 설계"에 대한 투자가 부족했다. 조금 더 차분하게 이 문제는 어떻게, 무엇을 사용하여 풀면 좋을지 적어보면서 풀어나가면 좋을 것 같다.
- 그리고 문제 풀이에 대해 부담을 느끼지 않았으면 한다. 기존대로 재미있게, 이런 게 있구나~ 하면서 차차 나아가보자. 아직 기본적인 화면 구현도 어려워하는 때이기에, 원래 목적대로 "자바스크립트 활용에 능숙해지기"와 "프로그래밍적 사고 방식에 익숙해지기"에 집중하자. 파이팅!
