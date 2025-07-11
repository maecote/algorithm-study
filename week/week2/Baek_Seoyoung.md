# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.26 ~ 2025.06.01

## 사용 언어: JavaScript

---

### Day 1 (05.26)

- 🔗 문제: [[level 1] 콜라 문제 - 132267](https://school.programmers.co.kr/learn/courses/30/lessons/132267)
- 📁 코드: [알고리즘이 아니라 수학 문제](https://github.com/sysysysyb/Study_Algorithm/tree/ae8cb3f2403901be59029d86313e5fcc6271786b/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/132267.%E2%80%85%EC%BD%9C%EB%9D%BC%E2%80%85%EB%AC%B8%EC%A0%9C)
- 💡 메모: 로직을 생각해내는 것 자체는 어렵지 않았지만 수학을 잘 하는 사람이면 코드를 더욱 간단하게 작성할 수 있는 문제였다. 콜라 20병(n)이 있는 상황에서 가게에 빈 병 2개(a)를 줬을 때 새 콜라 1개(b)를 받는 조건이라면, 콜라 빈 병 20개를 가게에 주고 그럼 다시 10병을 받고 그럼 다시 빈 병 10개 주고 또 5병을 받고... 이렇게 반복이 이루어지기 때문에 while문을 사용해서 문제를 해결했다. 그런데 다른 사람의 풀이를 확인하니, `solution = (a, b, n) => Math.floor(Math.max(n - b, 0) / (a - b)) * b` 이렇게 수학적 원리를 이용해서 한 줄로 코드를 작성한 풀이가 있었다. 요약하자면, 한 번 가게와 콜라를 주고받을 때 실제로 잃는 콜라(빈 병)의 개수는 $a - b$이고, 내가 갖고 있는 전체 콜라의 개수가 $a - b$보다 작아지면 더이상 주고받을 수 없기 때문에 k를 교환 횟수라고 할 때 $n - k(a - b)$이 0보다 클 때까지 교환이 가능하다. 그렇기 때문에 최대 교환 횟수는 k를 기준으로 식을 정리한 $(n - b) / (a - b)$이 되는 것이고, 거기에 한 번 교환할 때마다 b만큼의 새 콜라를 얻기 때문에 새로 얻을 수 있는 콜라의 전체 개수는 $k * b$, 즉 $(n - b) / (a - b) * b$가 되는 것이다...... 이해하는데 시간이 꽤 걸렸지만 다음에 이런 문제를 또 풀게 되면 수학적 원리를 이용해서 똑똑한 풀이를 할 수 있도록 시도해봐야겠다.

---

### Day 2 (05.27)

- 🔗 문제: [[level 1] 문자열 내 마음대로 정렬하기 - 12915](https://school.programmers.co.kr/learn/courses/30/lessons/12915)
- 📁 코드: [localeCompare 함수를 활용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/a53d38d74eb8709635f41729e2a32c056053470d/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12915.%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%EB%82%B4%E2%80%85%EB%A7%88%EC%9D%8C%EB%8C%80%EB%A1%9C%E2%80%85%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0)
- 💡 메모: 스터디 시간에 스터디원 중 한 분이 발표해주셨던 문제다. localeCompare을 사용하셨던 게 기억이 나서 두 문자열의 순서를 비교할 수 있는 localeCompare 함수를 활용해 코드를 간결하게 작성할 수 있었다.

---

### Day 4 (05.29)

- 🔗 문제: [[level 1] 명예의 전당 (1) - 138477](https://school.programmers.co.kr/learn/courses/30/lessons/138477)
- 📁 코드: [알고보니 스택 문제](https://github.com/sysysysyb/Study_Algorithm/tree/3dd2ea6c6f2fe81d34ce16ba2dd7a522809430de/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/138477.%E2%80%85%EB%AA%85%EC%98%88%EC%9D%98%E2%80%85%EC%A0%84%EB%8B%B9%E2%80%85%EF%BC%881%EF%BC%89)
- 💡 메모: 처음에는 이중 for문을 사용해서 코드를 작성했다. 3개의 명예의 전당 점수를 담을 list 배열을 선언하고 score의 값을 list의 값과 비교하며 명예의 전당의 최하위 점수를 answer 배열에 담아 출력하는 방식을 사용했는데, for 문을 이중으로 사용한데다 조건문이나 push 등 여러 코드가 나열되어 있으니 가독성이 좋지 못했다. 그래서 이 방법으로 문제를 한 번 풀고 난 뒤 slice를 이용해서 score 배열을 반복문을 통해 slice 해주며 명예의 전당 최하위 점수를 구하는 방식을 사용했더니 코드가 훨씬 간결해졌다. 그러나 성능 시간이 20ms가 나왔던 전자의 방법에 비해 slice를 사용한 후자의 방법은 시간이 114ms가 나왔다... 가독성과 성능 모두 만족할 수 있는 방법은 없는지 궁금해서 다른 사람의 풀이를 참고했더니 스택 자료구조를 이용해서 풀었을 때가 가장 효율적인 듯 했다. 이후에 시간을 내서 스택으로도 한번 풀어보고 다른 문제를 풀 때도 스택, 큐 등의 자료구조를 잘 적용할 수 있도록 신경써야겠다.

---

### Day 5 (05.30)

- 🔗 문제: [[level 1] 카드 뭉치 - 159994](https://school.programmers.co.kr/learn/courses/30/lessons/159994)
- 📁 코드: [shift를 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/39b41b588132924d6da8139db9baa83f45f033ce/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/159994.%E2%80%85%EC%B9%B4%EB%93%9C%E2%80%85%EB%AD%89%EC%B9%98)
- 💡 메모: 두 카드의 맨 앞글자를 비교하고 해당하는 것이 있으면 shift 메소드로 삭제해가는 방식으로 풀었던 문제다. card의 요소의 개수가 10 이하로 낮게 지정되어 있던 문제였기 때문에 shift를 사용해도 성능에 크게 문제가 없었다.

---

### Day 6 (05.31)

- 🔗 문제: [[level 1] [1차] 비밀지도 - 17681](https://school.programmers.co.kr/learn/courses/30/lessons/17681)
- 📁 코드: [toString과 padStart를 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/fd5c568e01c7c140c22253560c1d2e2a3ce3bd74/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/17681.%E2%80%85%EF%BC%BB1%EC%B0%A8%EF%BC%BD%E2%80%85%EB%B9%84%EB%B0%80%EC%A7%80%EB%8F%84)
- 💡 메모: 10진수를 무조건 5자리의 2진수로 변환해야 된다는 점이 중요했던 문제였는데, toString(2)를 통해 10진수를 2진수로 바꿔주고 padStart를 통해 변환한 2진수가 5자리가 아니면 앞의 비는 곳은 0으로 채우도록 설정했다. 

---

## 📌 이번 주 회고

- string이나 array의 다양한 메소드들을 문제 풀이에 잘 활용했다.
- 어떤 문제는 수학적 접근을 통해 더 간편하게 풀 수 있다는 것을 알았다.
