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

### Day 3 (06.11)

- 🔗 문제: [Easy) 88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/?envType=problem-list-v2&envId=two-pointers)
- 📁 코드: [1. nums1의 뒤부터 큰 숫자 채워넣기 아이디어 발상이 어려웠음 && 2. nums1의 유효숫자 index 가리키는 포인터 하나, nums2 가리키는 포인터 하나, nums1의 꽁지 가리키는 포인터 하나... 이거 근데 쓰리 포인터 아니여?!](https://github.com/makee-ham/algo-gogo/tree/main/0088-merge-sorted-array)
- 💡 메모: 일단 코드 관련해선 코드 링크에 내용을 다 적어버린 것 같은데... 문제에서 배열이 "Non-decreasing order(비 내림차순)"라고 적혀 있었다. 직역하면 "감소 안 하는 순서"니까, Ascending order(오름차순)와 차이가 없는 거 아닌가? 해서 찾아봤는데... 같은 숫자가 뭐 [1, 2, 2, 3] 이렇게 포함될 수 있음을 암시한 단어라고 한다. 즉, "같은 숫자가 있을 수 있는 오름차순".

### Day 4 (06.12)

- 🔗 문제: [LV 1) 체육복 - 42862](https://school.programmers.co.kr/learn/courses/30/lessons/42862)
- 📁 코드: [filter로 요소 제거해주기](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/42862.%E2%80%85%EC%B2%B4%EC%9C%A1%EB%B3%B5)
- 💡 메모: 이 사람 문제 또 끝까지 안 읽었다. "여별 체육복 가져왔어도 도난당했으면 남 못 빌려줌"이란 조건을 놓쳐서 해당 조건을 추가하여 다시 풀었다. **제발 문제 좀 제대로 읽자!**

### Day 5 (06.13)

- 🔗 문제: [Lv 0) 옹알이 (1) - 120956](https://school.programmers.co.kr/learn/courses/30/lessons/120956)
- 📁 코드: ["/"로 replace 후 every char가 "/"인지 확인](https://github.com/makee-ham/algo-gogo/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/0/120956.%E2%80%85%EC%98%B9%EC%95%8C%EC%9D%B4%E2%80%85%EF%BC%881%EF%BC%89)
- 💡 메모: 음... 뭔가 아기가 발음할 수 있는 문자열 부분을 "/"로 replace하고, 그래서 문자열의 모든 char가 every를 써서 "/"로만 구성되어 있는지, 그렇다면 result++ 식으로 풀었는데... 탐탁지 않아서 스터디원 분들의 생각과 아이디어를 여쭈었다.

### Day 6 (06.14) + Day 7 (06.15)

- 한 주간 과제를 총망라한 실습을 해보느라 코테나 알고리즘 공부를 할 시간이 없었다...
- 그래도 혹시 모르니 레포지토리 공유!!! [키메라 투두](https://github.com/makee-ham/todo-list)

---

## 📌 이번 주 회고

- 약간 뇌가 지친 느낌...?이었다. 온종일 몹시 피곤하고 모든 일이 힘들게 느껴졌던 한 주였다.
- 확 퍼지지 않도록 건강이나 기분 관리 잘 하면서 공부해야겠다는 생각이 많이 들었다.
- 생각보다 주말에 복습에 투자해야 할 시간이 많이 늘어날 것 같다. 주중에도 재현퀘스트(알고리즘 공부)를 시간이 나면 하는 게 좋겠다.
- 그래도 스터디원 분들과 수다 떠는 시간도 가졌어서 즐겁고 보람찬 한 주라고 생각한다. 차근차근 파이팅!
