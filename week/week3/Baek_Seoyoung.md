# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.02 ~ 2025.06.08

## 사용 언어: JavaScript

---

### Day 1 (06.02)

- 🔗 문제: [[level 1] 추억 점수 - 176963](https://school.programmers.co.kr/learn/courses/30/lessons/176963)
- 📁 코드: [map과 reduce를 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/13b540ff39837248be1ced872e99ed7b48c7b040/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/176963.%E2%80%85%EC%B6%94%EC%96%B5%E2%80%85%EC%A0%90%EC%88%98)
- 💡 메모: map과 reduce를 적절히 사용했다고 생각하지만, 다른 사람의 풀이를 참고했을 때 굳이 객체를 생성하지 않고 `yearning[name.indexOf(이름)]` 같은 방법으로도 바로 접근이 가능했다.

---

### Day 3 (06.04)

- 🔗 문제: [[level 1] 기사단원의 무기 - 136798](https://school.programmers.co.kr/learn/courses/30/lessons/136798)
- 📁 코드: [시간 초과를 조심해서 약수의 개수를 구하는 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/95cd3bca8fa05a73cf29a2f513482d536c4ba395/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/136798.%E2%80%85%EA%B8%B0%EC%82%AC%EB%8B%A8%EC%9B%90%EC%9D%98%E2%80%85%EB%AC%B4%EA%B8%B0)
- 💡 메모: 시간 초과를 조심해야 하는 문제였다. 주어진 숫자의 약수의 개수를 구하고 만약 개수가 제한 숫자보다 크다면 정해진 다른 수를 반환하는 문제인데, 제한 숫자가 있기는 하지만 주어지는 숫자가 최대 100,000까지 될 수 있기 때문에 약수의 개수를 구하면서 어떻게 시간 초과를 피할 건지가 관건이었다. 난 주어진 숫자가 소수인지 확인(제곱근 이하의 숫자까지만 나눗셈)하고, 1과 자기 자신을 제외한 약수의 첫번 째 쌍(12를 예시로 들자면 2, 6) 사이의 숫자들로만 약수를 찾도록 코드를 작성했다. 이 방법으로 시간 초과는 피할 수 있었지만 코드도 복잡하고 엄청나게 시간이 많이 소요되는 케이스도 있었는데, 다른 사람의 풀이를 확인하니 똑같이 소수인지 확인하면서 약수가 하나 나타나면 제곱근이면 1, 제곱근이 아니면 2를 count에 더해서 계산하는 간결한 풀이 방식을 사용한 사람도 있었다. 내가 생각한 방식과 비슷한 면이 있지만 훨씬 가독성이 좋아보여서 간결한 풀이 작성에 좀 더 신경써야겠다고 생각했다.

---

### Day 4 (06.05)

- 🔗 문제: [[level 1] 폰켓몬 - 1845](https://school.programmers.co.kr/learn/courses/30/lessons/1845)
- 📁 코드: [Set을 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/84d78ef7bcd119766a285f5773dc22474fd1d3c8/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/1845.%E2%80%85%ED%8F%B0%EC%BC%93%EB%AA%AC)
- 💡 메모: Set으로 중복 요소를 제거해서 간단하게 푼 문제였다. 한 줄로 작성했지만 `new Set(nums).size`와 `nums.length`를 따로 변수로 선언해서 작성했다면 더 가독성이 좋았을 것 같다.

---

### Day 7 (06.08)

- 🔗 문제: [[level 1] 숫자 짝꿍 - 131128](https://school.programmers.co.kr/learn/courses/30/lessons/131128)
- 📁 코드: [빈도수 세기 패턴을 사용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/082ab1756606e5d1c437c01c03d0b5aae940d6fd/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131128.%E2%80%85%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D)
- 💡 메모: 객체에 각 문자열의 문자의 빈도수를 저장해서 비교하여 푼 문제였다. 빈도수를 저장해서 활용하는 방식은 생각해본 적 없는데 이번 **숫자 짝꿍** 같은 문제에서 정말 유용하게 쓰일 것 같은 방식이라 잘 기억해둬야겠다.

---

- 🔗 문제: [[level 2] 숫자의 표현 - 12924](https://school.programmers.co.kr/learn/courses/30/lessons/12924?language=javascript)
- 📁 코드: [다중 포인터 패턴을 사용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/082ab1756606e5d1c437c01c03d0b5aae940d6fd/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12924.%E2%80%85%EC%88%AB%EC%9E%90%EC%9D%98%E2%80%85%ED%91%9C%ED%98%84)
- 💡 메모: 이 문제를 처음 봤을 때 대체 어떻게 풀어야 할지 감이 안왔는데 다중 포인터 패턴을 이용하니 어렵지 않게 풀 수 있었다. 다만 딱 한 개의 효율성 테스트 케이스에서 시간 초과가 났는데, 반복을 줄이고자 주어진 숫자의 반을 올림한 숫자까지만 계산했더니 해결할 수 있었다. 이 방법도 유용하게 쓰일 것 같아서 기억해두어야겠다.

---

## 📌 이번 주 회고

- 빈도수 세기 패턴, 다중 포인터 패턴 등 유용한 패턴을 잘 활용해야겠다.
- 가독성에 좀 더 신경써서 문제를 풀어야겠다.
