# 📘 Week 4 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.09 ~ 2025.06.15

## 사용 언어: JavaScript

---

### Day 1 (06.9)

- 🔗 문제: [131127. 할인 행사](https://school.programmers.co.kr/learn/courses/30/lessons/131127)
- 📁 코드: [lv2. 할인 행사 - 131127](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/131127.%E2%80%85%ED%95%A0%EC%9D%B8%E2%80%85%ED%96%89%EC%82%AC)
- 💡 메모: 이번 문제는 연속으로 원하는 제뭎과 수량이 할인하는 날짜와 10일 연속 일치하는지 찾는 문제였습니다. 그래서 현재부터 10일까지의 할인을 `map`을 통해 카운팅을 하고 그 값이랑 매칭하면 `return`하고 아니면 계속 진행하는 식으로 코드를 구성했습니다.

```js
function solution(want, number, discount) {
  var answer = 0;

  let discountMap = new Map();
  let wantMap = new Map();

  for (let j = 0; j < want.length; j++) {
    wantMap.set(want[j], number[j]);
  }

  for (let k = 0; k <= discount.length - 10; k++) {
    discountMap.clear();

    for (let i = k; i < k + 10; i++) {
      discountMap.set(discount[i], (discountMap.get(discount[i]) || 0) + 1);
    }

    let isMatch = true;
    for (const [key, value] of wantMap) {
      if (discountMap.get(key) !== value) {
        isMatch = false;
        break;
      }
    }

    if (isMatch) answer++;
  }

  return answer;
}
```

---

### Day 2 (06.10)

- 🔗 문제: [76502.괄호 회전하기](https://school.programmers.co.kr/learn/courses/30/lessons/76502)
- 📁 코드: [lv2. 괄호 회전하기 - 76502](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/76502.%E2%80%85%EA%B4%84%ED%98%B8%E2%80%85%ED%9A%8C%EC%A0%84%ED%95%98%EA%B8%B0)
- 💡 메모: 이번 문제는 옆으로 회전을 하며 올바른 갈호 문자열이 되게하는 x의 개수를 찾는 문제였습니다. 그렇기 때문에 따로 포인터를 사용하지 않고, 간단하게 두 개를 이어붙여 원을 만들게 되었습니다.

그 뒤로 문제를 해결하기 위해 `stack`을 활용하여, 매칭이 되는지를 판단하여 매칭이 된다면? 카운트를 늘리는 방식으로 해결해나갔습니다.

```js
function solution(s) {
  var answer = 0;

  const arr = s + s; // 왼쪽으로 x만큼 이동하기 때문에 그냥 이어 붙이기.

  for (let i = 0; i < s.length; i++) {
    let stack = [];
    let basket = arr.slice(i, s.length + i);
    let isTrue = true;

    for (let j = 0; j < basket.length; j++) {
      if (basket[j] === "{" || basket[j] === "(" || basket[j] === "[")
        stack.push(basket[j]);
      else {
        if (stack.length === 0) {
          isTrue = false;
          break;
        }
        let popData = stack.pop();

        if (
          (popData === "(" && basket[j] !== ")") ||
          (popData === "{" && basket[j] !== "}") ||
          (popData === "[" && basket[j] !== "]")
        ) {
          isTrue = false;
          break;
        }
      }
    }
    if (isTrue && stack.length === 0) {
      answer++;
    }
  }

  return answer;
}
```

---

### Day 3 (06.11)

- 🔗 문제: [87390.n^2 배열 자르기](https://school.programmers.co.kr/learn/courses/30/lessons/87390)
- 📁 코드: [lv2. n^2 배열 자르기 - 87390](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/87390.%E2%80%85n%EF%BC%BE2%E2%80%85%EB%B0%B0%EC%97%B4%E2%80%85%EC%9E%90%EB%A5%B4%EA%B8%B0)
- 💡 메모: 이번 문제는 `[0,0]` 에서 부터 점점 증가되는 값을 1차원 배열로 만들어서 `return` 해야하는 문제였습니다. 이러한 특징 때문에 처음에는 배열을 만들고 그 뒤 1차원으로 만들었지만, timeout이 발생하게 되어 이를 점점 고도화하여, 처음부터 1차원배열에 값을 넣는 방식으로 해결을 했습니다.

행과 열을 각각 `row = Math.floor(i / n) + 1`, `col = i % n + 1`로 연산을 한 뒤, `answer.push(Math.max(row,col))`를 하여 큰 값을 넣게 하여 같은 행이더라도 열이 늘어날 수록 값이 증가하기 때문에 이렇게 연산을 진행하였고, 결국에는 `left`와 `right`로 잘라줘야하기때문에 `for-loop`을 다음과 같이 지정하여 결과를 도출했습니다. `for(let i = left; i <= right; i++)`

```js
function solution(n, left, right) {
  var answer = [];

  let row = 0; // 층수
  let col = 0; // 몇 번째 인지

  for (let i = left; i <= right; i++) {
    row = Math.floor(i / n) + 1;
    col = (i % n) + 1;

    answer.push(Math.max(row, col));
  }

  return answer;
}
```

---

### Day 6 (06.14)

- 🔗 문제: [12949.행렬의 곱셈](https://school.programmers.co.kr/learn/courses/30/lessons/12949)
- 📁 코드: [lv2. 행렬의 곱셈 - 12949](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12949.%E2%80%85%ED%96%89%EB%A0%AC%EC%9D%98%E2%80%85%EA%B3%B1%EC%85%88)
- 💡 메모: 이번에 푼 문제는 행렬의 곱셈을 처리하는 `return` 하는 문제였습니다. 이 문제는 간단하게 수학 시간에 배웠던 행렬의 곱셈을 구하는 식을 소스코드로 구현하여 최종적으로 `arr3`에 더한 값을 넣어서 return을 하였습니다.
  연산 방식: `sum += arr1[i][k] * arr2[k][j]`

![alt text](https://gaussian37.github.io/assets/img/math/la/block_matrix_multiplication/0.png)

```js
function solution(arr1, arr2) {
  var answer = [[]];

  // arr1의 행열, arr2의 행열 구하기.
  const row = arr1.length;
  const col = arr2[0].length;
  const n = arr1[0].length;

  const arr3 = Array.from({ length: row }, () => Array(col).fill(0));

  for (let i = 0; i < row; i++) {
    for (let j = 0; j < col; j++) {
      let sum = 0;
      for (let k = 0; k < n; k++) {
        sum += arr1[i][k] * arr2[k][j];
      }

      arr3[i][j] = sum;
    }
  }

  return arr3;
}
```

---

## 📌 이번 주 회고

- 이전보다는 뭔가 수학적으로 풀이를 진행했다는 점에서 점차 성장하고 있다는 생각을 하게 되었습니다.

---

# 📘 Week 5 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.16 ~ 2025.06.22

(프로젝트, 심화반 보강 등등으로 한 주 휴식)

---

# 📘 Week 6 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.23 ~ 2025.06.29

## 사용 언어: JavaScript

---

### Day 2 (06.24)

- 🔗 문제: [42747.H-Index](https://school.programmers.co.kr/learn/courses/30/lessons/42747?language=javascript)
- 📁 코드: [lv2. H-Index - 42747](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42747.%E2%80%85H%EF%BC%8DIndex)
- 💡 메모: 이번에 해결한 문제는 `n편 중, h번 이상 인용된 논문이 h편 이상이고 나머지 논문이 h번 이하 인용되었다면 h의 최댓값이 이 과학자의 H-Index`로 H-index값을 return 해야하는 문제였습니다.

이 내용은 말만 어렵게 낸 문제인데 간단하게 `n`번째 loop을 할 때, n번이상이 몇개인지를 판단하기만 하면 되는 문제였습니다. 그렇기 때문에 `filter`로 `i`값보다 크거나 값은 것의 값을 넣어서 체크하고 값이 나오게 되는지를 check하였습니다.

```js
function solution(citations) {
  var answer = 0;
  let length = citations.length;

  for (let i = 0; i <= length; i++) {
    const count = citations.filter((acc) => acc >= i).length;

    if (count >= i) {
      answer = i;
    }
  }

  return answer;
}
```

## 📌 이번 주 회고

- 최근에 쉬지 못한거 같아서 휴가를 가서 푹 쉬다보니 알고리즘을 손대지 못하여서 이점이 아쉽습니다.
