# 📘 Week 2 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.26 ~ 2025.06.01

## 사용 언어: JavaScript

---

### Day 1 (05.26)

- 🔗 문제: [159994.카드 뭉치](https://school.programmers.co.kr/learn/courses/30/lessons/159994)
- 📁 코드: [lv1. 카드 뭉치 - 159994](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/159994.%E2%80%85%EC%B9%B4%EB%93%9C%E2%80%85%EB%AD%89%EC%B9%98)
- 💡 메모: `for...of` 를 사용해서 만들어야하는 배열을 만들기 위해 `shift()`를 사용하여 해결.
  <br>

      for(data of goal){
        if(cards1[0] === data){
            cards1.shift();
        }else if(cards2[0] === data){
            cards2.shift();
        }else{
            return "No";
        }

  }

---

### Day 2 (05.27)

- 🔗 문제: [12914.멀리 뛰기](https://school.programmers.co.kr/learn/courses/30/lessons/12914)
- 📁 코드: [lv2. 멀리 뛰기 - 12914](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12914.%E2%80%85%EB%A9%80%EB%A6%AC%E2%80%85%EB%9B%B0%EA%B8%B0)
- 💡 메모: 피보나치 수열을 활용하여, 1칸 또는 2칸을 뛸 수 있는 경우의 수를 구함. `f(n) = f(n-1) + f(n-2)` 방식으로 값을 도출. 만약, 3칸 점프가 생기게 되는 경우에는 `f(n) = f(n-1) + f(n-2) + f(n-3)` 방식으로 늘리면 된다. 계단 오르기 문제.

<br>

    const MOD = 1234567;

    if (n === 1) return 1;
    if (n === 2) return 2;

    a = 1;
    b = 2;

    for(let i = 3; i <= n; i++){
        let temp = (a + b) % MOD;
        a = b;
        b = temp;
    }

---

### Day 3 (05.28)

- 🔗 문제: [12953.N개의 최소공배수](https://school.programmers.co.kr/learn/courses/30/lessons/12953)
- 📁 코드: [lv2. N개의 최소공배수 - 12953](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12953.%E2%80%85N%EA%B0%9C%EC%9D%98%E2%80%85%EC%B5%9C%EC%86%8C%EA%B3%B5%EB%B0%B0%EC%88%98)
- 💡 메모: 이번 문제는 n개의 최소공배수를 구하는 문제였습니다. n개를 하기 위해서 0 ~ n -1번까지의 수를 앞에서부터 최대 공배수를 구하는 방식인 `gcd(a,b)`를 활용하여 최소공배수인 `lcm = (a * b) / gcd(a,b)`를 활용하였습니다. 연속적이기 때문에 `reduce()`를 활용.

  <br>

```js
  function solution(arr) {
    return arr.reduce((acc, curr) => lcm(acc, curr));
  }

  function gcd(a, b) {
    while (b !== 0) {
        let r = a % b;
        a = b;
        b = r;
    }
    return a;
    }

  function lcm(a, b) {
    return (a \* b) / gcd(a, b);
  }
```

---

### Day 4 (05.29)

- 🔗 문제: [131128. 숫자 짝꿍](https://school.programmers.co.kr/learn/courses/30/lessons/131128)
- 📁 코드: [lv1. 숫자 짝꿍 - 131128](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131128.%E2%80%85%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D)
- 💡 메모: 간단하게 풀릴줄 알았는데 생각보다 오래 걸린 문제. 일반적인 `String` 함수를 사용할까 했지만, 0~9까지의 숫자만 나오게 되기 때문에 `Map`을 사용하여, i값을 `String`으로 변경하여 비교를 시킴. 값이 여러번 나올 수도 있기 때문에 `Math.min()`으로 몇 번 들어가야하는지 생각하게 됨.
그리고 가장 큰 값으로 만들어야 하기 때문에 `map`과 `sort`를 사용하여 만들수 있는 가장 큰 짝수 값을 만듦.

  <br>

```js
for (let i = 0; i <= 9; i++) {
  let char = i.toString();

  if (left.has(char) && right.has(char)) {
    let loop = Math.min(left.get(char), right.get(char));
    for (let j = 0; j < loop; j++) {
      dataString.push(char);
    }
  }
}

dataString = dataString
  .map((data) => Number(data))
  .sort((a, b) => b - a)
  .join("");
```

<br>

---

### Day 5 (05.30)

- 💡 메모: 흥미로운 라이브러리가 생겨서 푸는 것을 까먹었습니다.

<br>

---

### Day 6 (05.31)

- 💡 메모: 흥미로운 라이브러리가 생겨서 푸는 것을 까먹었습니다.

---

### Day 7 (06.01)

- 🔗 문제: [12981. 영어 끝말잇기](https://school.programmers.co.kr/learn/courses/30/lessons/12981)
- 📁 코드: [lv2. 영어 끝말잇기 - 12981](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12981.%E2%80%85%EC%98%81%EC%96%B4%E2%80%85%EB%81%9D%EB%A7%90%EC%9E%87%EA%B8%B0)
- 💡 메모: 문제에 이전에 등장했던 단어를 사용할 수 없다는 의미를 잘못이해해서 중복을 허용하지 않게 하기 위해 `set`을 사용했는데, 생각해보니 `Map`을 사용하여 value가 2가 넘는게 있다면 바로 [0,0]을 리턴하도록 해야했는데 실수를 했다.

몇 번째의 사람이 몇번째의 loop에서 끝났는지 알기 위해서 if문에 걸리게 되면 `num = (i % n) + 1`과 `turm = Math.floor(i / n) + 1`로 `[num, turm]`을 구하게 했습니다.

```js
if (i > 0 && word[0] !== prev[prev.length - 1]) {
  let num = (i % n) + 1;
  let turm = Math.floor(i / n) + 1;
  return [num, turm];
}
```

- notion: [Link](https://www.notion.so/138476-1fe389abd42580708863d30e1671f248?pvs=4)

---

## 📌 이번 주 회고

- JS에 익숙해져서 전보다 알고리즘 문제를 푸는데 시간이 줄어든 것이 보여서 기분이 좋았습니다. 하지만 너무 `Map`과 `Set`을 많이 사용하는 거 같아서 주의해야 할꺼 같다는 생각을 했습니다.
