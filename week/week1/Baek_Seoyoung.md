# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.19 ~ 2025.05.25

## 사용 언어: JavaScript

---

### Day 1 (05.19)

- 🔗 문제: [[level 1] 두 개 뽑아서 더하기 - 68644](https://school.programmers.co.kr/learn/courses/30/lessons/68644)
- 📁 코드: [중복 제거할 때는 Set 객체 활용하기](https://github.com/sysysysyb/Study_Algorithm/tree/2b5f918ba8e69d7bf445305769f071e8e096b7cc/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/68644.%E2%80%85%EB%91%90%E2%80%85%EA%B0%9C%E2%80%85%EB%BD%91%EC%95%84%EC%84%9C%E2%80%85%EB%8D%94%ED%95%98%EA%B8%B0)
- 💡 메모: 처음에는 배열을 중복되지 않는 요소만 남도록 처리하는 마땅한 방법이 떠오르지 않아서 includes를 활용했다. 이런 경우 `[...new Set(중복처리할 배열)]`와 같이 Set 객체로 보다 간편하게 중복 요소를 제거할 수 있다는 걸 알게 되어 코드를 수정한 뒤 실행시켜보니 includes를 사용할 때보다 더 빠르게 중복 요소가 제거된 배열이 반환되는 것을 확인할 수 있었다.

---

### Day 2 (05.20)

- 🔗 문제: [[level 1] 푸드 파이트 대회 - 134240](https://school.programmers.co.kr/learn/courses/30/lessons/134240)
- 📁 코드: [배열을 이용해 잘 풀었지만...](https://github.com/sysysysyb/Study_Algorithm/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/134240.%E2%80%85%ED%91%B8%EB%93%9C%E2%80%85%ED%8C%8C%EC%9D%B4%ED%8A%B8%E2%80%85%EB%8C%80%ED%9A%8C)
- 💡 메모: 로직을 생각해내는데 그렇게 오래 걸리지 않았던 문제였다. 문자열 변수 `str`을 선언하고 `str += ...`와 같이 코드를 작성해서 필요한 문자들을 추가해준 다음 `'0'`을 추가하고 `str`의 문자들이 반대로 정렬된 문자열을 바로 이어붙여주면 되겠다고 생각했다. 그러나 String 타입의 변수에는 `reverse` 메소드를 사용할 수 없다는 것을 깨닫고 `foodlist(fl)` 배열을 선언해서 그 곳에 정답을 추가한 뒤 `reverse`를 적용해 문제를 해결했다. **하지만** `[...str].reverse()`처럼 스프레드 연산자를 이용하면 문자열을 즉석에서 배열로 만들어 `reverse`를 사용할 수 있었을텐데 그러지 못한 점이 아쉽다... 다음에는 반드시 **스프레드 연산자**의 존재를 기억해서 문제를 풀어봐야겠다.

---

### Day 3 (05.21)

- 🔗 문제: [[level 1] K번째수 - 42748](https://school.programmers.co.kr/learn/courses/30/lessons/42748)
- 📁 코드: [구조 분해 할당을 잘 활용하자](https://github.com/sysysysyb/Study_Algorithm/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/42748.%E2%80%85K%EB%B2%88%EC%A7%B8%EC%88%98)
- 💡 메모: 이번 문제도 로직을 생각해내는데 오래 걸리지는 않았지만, 배열의 각 요소를 구조 분해 할당으로 나누어 변수에 값을 담을 수 있다는 점을 떠올리지 못한 게 아쉬웠다. 기존에 command[0], command[1], command[2]로 표현했던 것을 구조 분해 할당으로 i, j, k라는 변수에 나누어 담는 식으로 코드를 수정했더니 가독성이 훨씬 좋아졌다. js의 중요한 문법 중 하나인 **구조 분해 할당**도 잘 활용할 수 있도록 신경써야겠다.

---

### Day 4 (05.22)

- 🔗 문제: [[level 1] 숫자 문자열과 영단어 - 81301](https://school.programmers.co.kr/learn/courses/30/lessons/81301)
- 📁 코드: [replaceAll을 활용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/81301.%E2%80%85%EC%88%AB%EC%9E%90%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%EA%B3%BC%E2%80%85%EC%98%81%EB%8B%A8%EC%96%B4)
- 💡 메모: 문자열 내에서 특정 문자열을 모두 찾아 원하는 값으로 바꿀 수 있는 replaceAll을 활용해 문제를 풀었다. 그리고 다른 사람의 풀이에서 split과 join을 이용해 비슷한 로직을 구현할 수 있다는 점을 확인할 수 있었다. 다만 replaceAll은 문자열을 직접 바꾸는 것이 아닌, 수정된 문자열을 반환하는 함수라는 점을 잊지 말아야겠다.

---

## 📌 이번 주 회고

-
