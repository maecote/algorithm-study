# 📘 Week 8 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.07.07 ~ 2025.07.13

## 사용 언어: JavaScript

---

### Day 1 (07.07)

- 🔗 문제: [42586.기능개발 ](https://school.programmers.co.kr/learn/courses/30/lessons/42586)
- 📁 코드: [lv2. 기능개발 - 42586](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42586.%E2%80%85%EA%B8%B0%EB%8A%A5%EA%B0%9C%EB%B0%9C)
- 💡 메모: 이번 문제는 앞의 progresses가 진척도가 100이 되면 배포가 이루어지게 되는 경우로, 순서대로 진행이 이루어지기에 앞의 값이 100이상이 아니면 뒤에 내용이 계속 밀리게 되는 구조를 가지게 되는데 이때, 몇개가 배포가 되는지를 return 하면 되는 문제였습니다.

그래서 저는 이 문제를 queue를 사용해서 FIFO 방식을 사용하기 위해서 `shift`를 활용하며, 진행속도인 speed를 progresses 각각에 더하며, 연산을 진행했습니다.

```js
function solution(progresses, speeds) {
  var answer = [];

  while (progresses.length !== 0) {
    let count = 0;

    for (let i = 0; i < progresses.length; i++) {
      progresses[i] = progresses[i] + speeds[i];
    }

    while (progresses.length > 0 && progresses[0] >= 100) {
      progresses.shift();
      speeds.shift();
      count++;
    }

    if (count !== 0) {
      answer.push(count);
    }
  }

  return answer;
}
```

---

### Day 7 (07.08)

- 🔗 문제: [87946.피로도](https://school.programmers.co.kr/learn/courses/30/lessons/87946)
- 📁 코드: [lv2. 피로도 - 87946](https://school.programmers.co.kr/learn/courses/30/lessons/87946)
- 💡 메모: 이번 문제는 n개의 던전이 있을 때, 피로도를 효율적으로 소모할 수 있는 방법을 찾는 문제였습니다.

그렇기 때문에 최대로 갈 수 있는 방법을 가짓수를 찾기 위해 가장 멀리간 값을 count 하기에는 DFS(깊이 우선 탐색)이 좋을 것 같다고 생각하여 해당 알고리즘으로 풀이를 시작했습니다.

이 때, 모든 노드에서 가장 깊게 들어간 경우를 max로 값을 가져서 리턴하는 방식으로 코드를 작성하였습니다.

```js
function solution(k, dungeons) {
  let max = 0;

  const visited = Array(dungeons.length).fill(false);

  function dfs(initHeath, count) {
    max = Math.max(max, count);

    for (let i = 0; i < dungeons.length; i++) {
      const [need, cost] = dungeons[i];

      if (!visited[i] && initHeath >= need) {
        visited[i] = true;
        dfs(initHeath - cost, count + 1);
        visited[i] = false;
      }
    }
  }

  dfs(k, 0);

  return max;
}
```

---

## 📌 이번 주 회고

- 오랜만에 DFS로 문제를 해결하려고 하니 복잡하기도 하고, 다른 사람에게 설명할 정도는 아니기에 좀 더 공부를 진행을 해야겠다고 생각했습니다.
