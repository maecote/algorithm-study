# 📘 Week 7 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.30 ~ 2025.07.06

## 사용 언어: JavaScript

---

### Day 6 (07.05)

- 🔗 문제: [136798. 기사단원의 무기](https://school.programmers.co.kr/learn/courses/30/lessons/136798)
- 📁 코드: [lv1. 기사단원의 무기 - 136798](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/136798.%E2%80%85%EA%B8%B0%EC%82%AC%EB%8B%A8%EC%9B%90%EC%9D%98%E2%80%85%EB%AC%B4%EA%B8%B0)
- 💡 메모: 이번 문제는 1부터 `number`까지의 각각의 약수의 갯수가 `limit`을 초과하면 약수 갯수 대신에 `power`을 대신 하여 추가를 합니다. `answer += count > limit ? power : count;` 삼항연산자를 활용하여 문제를 풀었습니다.

약수는 `%` 연산을 했을 때, 나누어 떨어지면 또 다른 약수를 가지기 때문에 count를 늘리고, 만약에 나눠서 나오는 값이 다르다면? 9의 약수 중 3은 하나인데, 12의 약수 중 2,6은 두 개가 나오기 때문에 하나 더 한다.

이렇게 연산은 제한 사항에 `j * j <= i;` 를 추가하여 절반만 연산을 하기에 6과 2가 추가적으로 늘어나는 것을 방지하며, loop의 길이를 루트로 줄임.

```js
function solution(number, limit, power) {
  var answer = 0;

  for (let i = 1; i <= number; i++) {
    let count = 0;

    for (let j = 1; j * j <= i; j++) {
      if (i % j === 0) {
        count++;

        if (j !== i / j) count++;
      }
    }
    answer += count > limit ? power : count;
  }

  return answer;
}
```

---

### Day 7 (07.06)

- 🔗 문제: [42578. 의상](https://school.programmers.co.kr/learn/courses/30/lessons/42578)
- 📁 코드: [lv2. 의상 - 42578](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42578.%E2%80%85%EC%9D%98%EC%83%81)
- 💡 메모: 이번 문제는 각 종류별로 최대 1가지 의상만 착용할 수 있으며, 기본적인 종류의 합성을 하면 됨. 또한, 최소한 한개의 의상을 입어야 함.

해당 문제는 딱히 조합 된 이름을 return 하지 않아도 되기 때문에, `Map`을 사용하여, `	Map(2) { 'headgear' => 2, 'eyewear' => 1 }` 다음과 같이 나오도록 합니다. 이 값을 활용하여, type별로 +1한 값을 곱하면 모든 조합의 수가 나오게 됩니다. 하지만 이렇한 경우에 아무것도 안입은 경우의 수도 추가가 되기 때문에 마지막에 -1을 합니다.

```js
function solution(clothes) {
  var answer = 1;
  let clothesMap = new Map();

  for (let i = 0; i < clothes.length; i++) {
    const type = clothes[i][1];
    clothesMap.set(type, (clothesMap.get(type) || 0) + 1);
  }

  for (let count of clothesMap.values()) {
    answer *= count + 1;
  }

  answer -= 1;

  return answer;
}
```

---

### Day 7 (07.06)

- 🔗 문제: [12901.2016년](https://school.programmers.co.kr/learn/courses/30/lessons/12901)
- 📁 코드: [lv1. 2016년 - 12901](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12901.%E2%80%852016%EB%85%84)
- 💡 메모: 이번 문제는 2016년의 a월 b일이 무슨 요일인지 찾는 문제입니다.

이때, `new Date(YYYY, MM, DD)`를 활용하여 YYYY 인자에는 제공되는 인자가 없으므로 2016을 임의로 입력하고, MM은 0부터 시작하는데 a는 5월을 나타내므로 `a-1`을 인자로 입력하고, DD는 1부터 시작하기에 `b` 그대로 집어넣어 `let date = new Date(2016,a-1,b);`와 같이 사용합니다.

또한, `date.getDay()`를 하게 되면 0~6까지의 값이 나오게 되기에 요일 이름을 미리 매핑해두고 사용합니다. `const day = ["SUN","MON", "TUE", "WED", "THU", "FRI", "SAT"];`

최종적으로 `answer = day[date.getDay()];`를 return 하여 요일을 얻게 됩니다.

```js
function solution(a, b) {
  var answer = "";

  const day = ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"];

  let date = new Date(2016, a - 1, b);

  answer = day[date.getDay()];

  return answer;
}
```

---

## 📌 이번 주 회고

- JS 내장 함수를 사용하니 너무 문제가 쉽게 풀리는데 너무 좋은거 같습니다.
