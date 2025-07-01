# 📘 Week 4 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.09 ~ 2025.06.15

## 사용 언어: JavaScript

---

### Day 1 (06.09)

- 🔗 문제: [Lv 2) 짝지어 제거하기 - 12973](https://school.programmers.co.kr/learn/courses/30/lessons/12973)
- 📁 코드: [Stack 활용 문제!](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12973.%E2%80%85%EC%A7%9D%EC%A7%80%EC%96%B4%E2%80%85%EC%A0%9C%EA%B1%B0%ED%95%98%EA%B8%B0)
- 💡 메모: 문제를 보니까 [퍼즐버블 게임](https://m.blog.naver.com/eeuu1133/221512704504)이 생각났다. 대신 스택 구조의. char를 쏴서 stack에 넣는데 제일 위의 stack이 방금 쏜 char과 같으면 둘이 펑! 터지는 느낌으로 풀었더니 잘 됐다.

### Day 2 (06.10)

- 🔗 문제: [Easy) 3442. Maximum Difference Between Even and Odd Frequency I](https://leetcode.com/problems/maximum-difference-between-even-and-odd-frequency-i/?envType=daily-question&envId=2025-06-10)
- 📁 코드: [frequency map의 이용](https://github.com/makee-ham/algo-gogo/tree/main/3753-maximum-difference-between-even-and-odd-frequency-i)
- 💡 메모: 재현 님의 퀘스트 중 "빈도수 세기 패턴"에 해당! + 힌트에 적혀있던 말: "Use a frequency map to identify the maximum odd and minimum even frequencies. Then, calculate their difference." frequency map이 뭔가 해서 찾아봤더니(영어로 하니까 못 알아먹은 1인) 정리가 간단하게 잘 되어 있는 블로그 글이 있었다. 참고 요망! [JavaScript Algorithms Techniques: Frequency Map](https://ipraveen.medium.com/javascript-algorithms-techniques-frequency-map-1ddee0829c60)

```javascript
const buildFrequencyMap = (items) => {
  const map = {};

  for (const item of items) {
    // Get the value and increment it or initialize it with 0 and increment it
    map[item] = (map[item] ?? 0) + 1;
  }

  return map;
};

console.log(buildFrequencyMap([1, 1, 1, 2, 2, 3, 4])); // Output: { '1': 3, '2': 2, '3': 1, '4': 1 }
```

### Day 3 (06.11)

- 🔗 문제: [Easy) 88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/?envType=problem-list-v2&envId=two-pointers)
- 📁 코드: [1. nums1의 뒤부터 큰 숫자 채워넣기 아이디어 발상이 어려웠음 && 2. nums1의 유효숫자 index 가리키는 포인터 하나, nums2 가리키는 포인터 하나, nums1의 꽁지 가리키는 포인터 하나... 이거 근데 쓰리 포인터 아니여?!](https://github.com/makee-ham/algo-gogo/tree/main/0088-merge-sorted-array)
- 💡 메모: 일단 코드 관련해선 코드 링크에 내용을 다 적어버린 것 같은데... 문제에서 배열이 "Non-decreasing order(비 내림차순)"라고 적혀 있었다. 직역하면 "감소 안 하는 순서"니까, Ascending order(오름차순)와 차이가 없는 거 아닌가? 해서 찾아봤는데... 같은 숫자가 뭐 [1, 2, 2, 3] 이렇게 포함될 수 있음을 암시한 단어라고 한다. 즉, "같은 숫자가 있을 수 있는 오름차순".

---

## 📌 이번 주 회고

- Pokedex 등으로 인해 완전 K.O. 리액트 실습이 우선시되어야 할 타이밍이라 문제 풀이를 미뤄두기로 합의했다. ㅠㅠ
- 미니 프로젝트 주간에도 어려울 것 같고... 일단 하는 만큼 해봐야지!
