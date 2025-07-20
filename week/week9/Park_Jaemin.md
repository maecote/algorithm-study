# 📘 Week 8 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.07.14 ~ 2025.07.20

## 사용 언어: JavaScript

---

### Day 1 (07.14)

- 🔗 문제: [42840. 모의고사 ](https://school.programmers.co.kr/learn/courses/30/lessons/42840)
- 📁 코드: [lv1. 모의고사 - 42840](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/42840.%E2%80%85%EB%AA%A8%EC%9D%98%EA%B3%A0%EC%82%AC)
- 💡 메모: 이번 문제는 수포자인 3명의 사람이 문제를 찍었을때 가장 문제를 많이 맞힌 사람을 찾는 문제였습니다. 각각 정해진 루틴에 맞춰서 정답을 찍기 때문에 `supo[i][j % (supo[i].length)] === answers[j]` 한 식을 만들어서 가장 많이 나온 사람을 return 했습니다.

```js
function solution(answers) {
  var answer = [];

  const supo = [
    [1, 2, 3, 4, 5],
    [2, 1, 2, 3, 2, 4, 2, 5],
    [3, 3, 1, 1, 2, 2, 4, 4, 5, 5],
  ];
  let supoSum = [0, 0, 0];

  for (let i = 0; i < supo.length; i++) {
    for (let j = 0; j < answers.length; j++) {
      if (supo[i][j % supo[i].length] === answers[j]) supoSum[i]++;
    }
  }

  const maximum = Math.max(supoSum[0], supoSum[1], supoSum[2]);

  for (let k = 0; k < 3; k++) {
    if (supoSum[k] === maximum) {
      answer.push(k + 1);
    }
  }

  return answer;
}
```

---

### Day 2 (07.15)

- 🔗 문제: [17680. ［1차］캐시](https://school.programmers.co.kr/learn/courses/30/lessons/17680)
- 📁 코드: [lv2. ［1차］캐시 - 17680](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/17680.%E2%80%85%EF%BC%BB1%EC%B0%A8%EF%BC%BD%E2%80%85%EC%BA%90%EC%8B%9C)
- 💡 메모: 이번 문제는 운영체제의 cache와 관련된 문제입니다. cache가 있다면 1을 더하고, 없다면 5를 더하기 때문에 `Map`를 사용하게 되었으며, 조건에 캐시 교체 알고리즘인 `LRU(Least Recently Used)`를 해야 하기 때문에 DoubleLinkedList를 만들어서 풀게 되었습니다.

LRU 알고리즘은 head에 가까운 node일수록 가장 최근에 참고된 페이지, tail에 가까운 node 일수록 가장 오랫도안 참조되지 않는 페이지이며, cache size를 넘어서면 tail에 있는 것을 우선적으로 삭제되게 하는 알고리즘입니다.

```js
function Node(data){
    this.data = data;
    this.prev = null;
    this.next = null;
}

function DoubleLinkedList(){
    this.head = null;
    this.tail = null;
    this.length = 0;
}

DoubleLinkedList.prototype.append = function (value){
    let node = new Node(value);

    if(this.head === null){
        this.head = node;
        this.tail = node;
    }else{
        this.tail.next = node;
        node.prev = this.tail;
        this.tail = node;
    }

    this.length++;
}

DoubleLinkedList.prototype.remove = function (node){
    if(!node)
        return;

    if(node === this.head && node === this.tail){
        this.head = null;
        this.tail = null;
    } else if(node === this.head){
        this.head = node.next;
        this.head.prev = null;
    } else if(node === this.tail){
        this.tail = node.prev;
        this.tail.next = null;
    } else{
        node.prev.next = node.next;
        node.next.prev = node.prev;
    }



    this.length--;
}

function solution(cacheSize, cities) {
    var answer = 0;
    const list = new DoubleLinkedList();
    const cacheMap = new Map();

    for(let city of cities){
        city = city.toLowerCase();

        if(cacheSize === 0){
            answer += 5;
            continue;
        }

        //1. cache Hit
        if(cacheMap.has(city)){
            answer += 1;
            const node = cacheMap.get(city);
            list.remove(node);
            list.append(city);
            cacheMap.set(city, list.tail);
        } // 2. cache miss
        else{
            answer += 5;

            if(list.length >= cacheSize){
                const oldNode = list.head;
                list.remove(oldNode);
                cacheMap.delete(oldNode.data);
            }
            list.append(city);
            cacheMap.set(city, list.tail);
        }
    }

    return answer;
}
}
```

---

### Day 7 (07.20)

- 🔗 문제: [161989. 덧칠하기](https://school.programmers.co.kr/learn/courses/30/lessons/161989)
- 📁 코드: [lv1. 덧칠하기 - 161989](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/161989.%E2%80%85%EB%8D%A7%EC%B9%A0%ED%95%98%EA%B8%B0)
- 💡 메모: 이번 문제는 페인트로 덧칠하기 위해서 `section[x]`에 들어있는 곳부터 시작하여 일부분만을 칠하면 되기 때문에 안에 들어있는 값을 기준으로 시작을 하기에 greedy algorithm을 활용하여 풀어나갔습니다.

제한사항에 벽을 넘어가지 않고, 구역의 일부분만 포함되도록 칠하면 안된다고 했기에 `i < section.length && section[i] < start + m`와 같은 조건을 활용하여, 구역 이탈을 못하도록 했습니다.

```js
function solution(n, m, section) {
  var answer = 0;
  let i = 0;

  while (i < section.length) {
    const start = section[i]; // 페인트를 시작할 위치
    answer++;

    while (i < section.length && section[i] < start + m) {
      i++;
    }
  }

  return answer;
}
```

---

## 📌 이번 주 회고

- 오랜만에 캐시 교체 알고리즘인 (LRU)에 대해 공부를 하게 되면서 OS 부분을 다시 공부를 조금 진행을 했는데 역시 운영체제는 어려운거 같다고 생각이 든 한 주였습니다.
