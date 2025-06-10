# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.02 ~ 2025.06.08

## 사용 언어: JavaScript

---

### Day 1 (06.02)

- 💡 메모: react에 새로운 기능을 공부하느라 못풀었습니다.

---

### Day 2 (06.03)

- 🔗 문제: [17681.[1차] 비밀지도](https://school.programmers.co.kr/learn/courses/30/lessons/17681)
- 📁 코드: [lv1. [1차] 비밀지도 - 17681](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/17681.%E2%80%85%EF%BC%BB1%EC%B0%A8%EF%BC%BD%E2%80%85%EB%B9%84%EB%B0%80%EC%A7%80%EB%8F%84)
- 💡 메모: 이번 문제는 `toString`과 `padStart`를 사용하여 쉽게 문제를 풀었습니다. `arr.toString(2)`을 하게 되면 `9 = 1001`로 값이 변경되게 됩니다.

하지만 이렇게 되면 n값이 5인 경우에 앞이 0이 붙어야 하는데 이를 해결할 수 없어서 사용한 것이 `padStart(n, '0'))`입니다. 이 함수를 사용하면 n의 자리만큼 빈칸에 '0'을 채울 수 있었습니다. 만약에 '1'을 채우고 싶다면 0대신 1을 넣으면 됩니다. 마지막으로 두 값 중 하나만 1이면 #이 들어가니 `AND연산자(||)`를 사용하여 풀이를 마무리 했습니다.

```js
const data1 = arr1.map((arr) => arr.toString(2).padStart(n, "0"));
const data2 = arr2.map((arr) => arr.toString(2).padStart(n, "0"));

for (let i = 0; i < n; i++) {
  let dataString = "";

  let mapA = data1[i].split("");
  let mapB = data2[i].split("");

  for (let j = 0; j < n; j++) {
    if (mapA[j] === "1" || mapB[j] === "1") dataString += "#";
    else dataString += " ";
  }
  answer.push(dataString);
}
```

---

### Day 3 (06.04)

- 🔗 문제: [176963.추억 점수](https://school.programmers.co.kr/learn/courses/30/lessons/176963)
- 📁 코드: [lv1. 추억 점수 - 176963](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/176963.%E2%80%85%EC%B6%94%EC%96%B5%E2%80%85%EC%A0%90%EC%88%98)
- 💡 메모: 이번 문제는 `Map`을 사용하여 key와 value값을 트리거하여 sum을 하여 retunr하는 배열에 넣으면 되는 문제였습니다. 그래서 name을 key값, yearnig을 value값으로 photo에 있는 2중 배열의 값에서 각각 추출하여 더했습니다.

```js
for (let j = 0; j < photo.length; j++) {
  let sum = 0;

  for (let k = 0; k < photo[j].length; k++) {
    if (nameMap.has(photo[j][k])) sum += nameMap.get(photo[j][k]);
  }

  answer.push(sum);
}
```

---

### Day 4 (06.05)

- 💡 메모: 나태하여 못풀었습니다.

---

### Day 5 (06.06)

- 💡 메모: 현충일

---

### Day 6 (06.07)

- 💡 메모: redux를 공부하느라 못풀었습니다.

---

### Day 7 (06.08)

- 🔗 문제: [131701. 연속 부분 수열 합의 개수](https://school.programmers.co.kr/learn/courses/30/lessons/131701)
- 📁 코드: [lv2. 연속 부분 수열 합의 개수 - 131701](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/131701.%E2%80%85%EC%97%B0%EC%86%8D%E2%80%85%EB%B6%80%EB%B6%84%E2%80%85%EC%88%98%EC%97%B4%E2%80%85%ED%95%A9%EC%9D%98%E2%80%85%EA%B0%9C%EC%88%98)
- 💡 메모: 이번 문제는 원형 수열에서 나올 수 있는 모든 경우의 수를 찾는 문제였습니다. 원형이기 때문에 포인터로 풀 수 있지만 간단하게 두 개를 붙여서 풀었습니다. `dataString = elements.concat(elements)` 그 뒤 n ~ n -1번까지 돌면서 `slice`를 활용하여 배열로 나눈 뒤, `set`으로 중복을 피하며 reduce로 값을 추가하였습니다. 최종적으로 원하는 것은 갯수이기 때문에 `Set`의 size를 return 하였습니다.

```js
for (let i = 0; i < length; i++) {
  // i가 start값.
  set.add(dataString[i]);
  for (let j = 1; j < length + 1; j++) {
    arr = dataString.slice(i, i + j);
    set.add(arr.reduce((a, b) => a + b, 0));
  }
}

answer = set.size;
```

---

## 📌 이번 주 회고

- 이번 주는 알고리즘 공부를 좀 나태하게 진행한 거 같습니다. 좀 더 열심히 해야 겠다고 생각들었습니다.
