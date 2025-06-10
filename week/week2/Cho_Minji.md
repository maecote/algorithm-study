# 📘 Week 2 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.26 ~ 2025.06.01  
## 사용 언어: JavaScript

---

### Day 1 (05.26)

- 🔗 문제: [별 찍기 - 11](https://www.acmicpc.net/problem/2448)
- 📁 코드: [2448. 별 찍기 － 11](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/2448.%E2%80%85%EB%B3%84%E2%80%85%EC%B0%8D%EA%B8%B0%E2%80%85%EF%BC%8D%E2%80%8511/%EB%B3%84%E2%80%85%EC%B0%8D%EA%B8%B0%E2%80%85%EF%BC%8D%E2%80%8511.js)
- 💡 메모: 재귀+분할 정복. 크기 N의 삼각형은 세 개의 크기 N/2의 삼각형으로 나뉘는 구조. 삼각형의 꼭짓점 좌표를 기준으로 재귀적으로 호출한다. 가장 작은 단위가 크기 3인 삼각형이므로 N===3을 기저 조건으로 한다.
  ```js
  // 재귀 함수
  paintStar(n, mid, line)
  ```
  - n: 현재 삼각형의 높이
  - mid, line: 꼭짓점 좌표
  ```js
  // 재귀 호출
  const half = n / 2;
  paintStar( half, mid, line );
  paintStar( half, mid - half, line + half );
  paintStar( half, mid + half, line + half );
  ```
  
  N=12일 때 호출 예) 
  ```
  paintStar(12, 11, 0)
  ├─ paintStar(6, 11, 0)
  │   ├─ paintStar(3, 11, 0)
  │   ├─ paintStar(3, 8, 3)
  │   └─ paintStar(3, 14, 3)
  ├─ paintStar(6, 5, 6)
  │   ├─ paintStar(3, 5, 6)
  │   ├─ paintStar(3, 2, 9)
  │   └─ paintStar(3, 8, 9)
  └─ paintStar(6, 17, 6)
      ├─ paintStar(3, 17, 6)
      ├─ paintStar(3, 14, 9)
      └─ paintStar(3, 20, 9)
  ```
  재귀 문제라는 점에만 집중했을 때는 반복 구조를 구성하는 데에 어려움을 겪어 다른 풀이들을 참고해서 풀었지만 분할정복 영상을 보고 다시 시도하니 수월하게 풀 수 있었다.

---

### Day 4 (05.29)

- 🔗 문제: [(퀘스트) 숫자 짝꿍
](https://school.programmers.co.kr/learn/courses/30/lessons/131128)
- 📁 코드: [131128. 숫자 짝꿍](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/131128.%E2%80%85%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D/%EC%88%AB%EC%9E%90%E2%80%85%EC%A7%9D%EA%BF%8D.js)
- 💡 메모: 두 정수에 공통으로 나타나는 정수로 만들 수 있는 가장 큰 정수를 만드는 문제. 처음에는 객체를 사용해 작성하다가 0~9 사이의 숫자 빈도는 배열을 사용하는게 더 간단하게 작성할 수 있을 것 같아 배열을 사용했다. 
  1. X와 Y 각각의 숫자 빈도를 저장하기 위해 크기가 10이고 0으로 채운 배열 counterX, counterY를 생성한다.
  2. X와 Y를 각각 순회하면서 해당 인덱스 값을 1 증가시킨다.
  3. i=9부터 0까지 역순으로 순회하면서 counterX[i]와 counterY[i]의 최솟값만큼 i를 문자열 result에 더한다.
  ```js
    const counterX = Array(10).fill(0);
    const counterY = Array(10).fill(0);
    
    for (let n of X) counterX[n]++;
    for (let n of Y) counterY[n]++;
    
    let result = '';
    
    for (let i = 9; i >= 0; i--) 
        result += (i + '').repeat(Math.min(counterX[i], counterY[i]));
  ```
  
<br>

- 🔗 문제: [(퀘스트) 크기가 작은 부분 문자열
](https://school.programmers.co.kr/learn/courses/30/lessons/147355)
- 📁 코드: [147355. 크기가 작은 부분문자열](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/147355.%E2%80%85%ED%81%AC%EA%B8%B0%EA%B0%80%E2%80%85%EC%9E%91%EC%9D%80%E2%80%85%EB%B6%80%EB%B6%84%EB%AC%B8%EC%9E%90%EC%97%B4/%ED%81%AC%EA%B8%B0%EA%B0%80%E2%80%85%EC%9E%91%EC%9D%80%E2%80%85%EB%B6%80%EB%B6%84%EB%AC%B8%EC%9E%90%EC%97%B4.js)
- 💡 메모: t에서 p와 길이가 같은 부분문자열 중에서 p보다 작거나 같은 수의 횟수를 구하는 문제.
  substr()가 자바스크립트에서 deprecated된 함수라는 것을 알고 subString()을 사용하도록 수정했다.
  ```js
  if (t.substr(i, len) <= p) count++;
  if (t.substring(i, i + len) <= p) count++;
  ```
  참고)
  - substr(시작 인덱스, 잘라낼 길이)
  - subString(시작 인덱스, 종료 인덱스) (종료 인덱스는 부분문자열에서 제외)

---

### Day 5 (05.30)

- 🔗 문제: [부분합](https://www.acmicpc.net/problem/1806)
- 📁 코드: [1806. 부분합](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/1806.%E2%80%85%EB%B6%80%EB%B6%84%ED%95%A9/%EB%B6%80%EB%B6%84%ED%95%A9.js)
- 💡 메모: 누적합+투포인터. 수열의 부분합 중 그 합이 S 이상이 되는 것 중 가장 짧은 것의 길이를 구하는 문제.
  ```js
  // 변수 선언
  let [start, end, sum] = [0, 0, arr[0]]; // 시작 포인터, 끝 포인터, 현재 구간의 합
  let minLen = N; // 최소 길이. 수열의 길이인 N으로 초기화
  let isMore = false; // S 이상인 부분합이 존재하는지 여부
  ```
  투 포인터 기법으로 부분합을 구한다. 합이 S 이상이 되면 그 길이와 minLen을 비교하여 최솟값을 저장하고 isMore을 true로 설정한다. 마지막에 isMore의 값에 따라 minLen 또는 0을 출력한다.

<br>

- 🔗 문제: [두 용액](https://www.acmicpc.net/problem/2470)
- 📁 코드: [2470. 두 용액](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Gold/2470.%E2%80%85%EB%91%90%E2%80%85%EC%9A%A9%EC%95%A1/%EB%91%90%E2%80%85%EC%9A%A9%EC%95%A1.js)
- 💡 메모: 투 포인터. 합이 0에 가장 가까운 두 정수를 찾아 오름차순으로 출력하는 문제.
  ```js
  // 변수 선언
  let [start, end] = [0, N - 1]; // 시작 포인터와 끝 포인터.
  let twoSum = [0, 0, Infinity]; // 두 용액과 그 합을 저장
  ```
  용액 수열을 오름차순으로 정렬하고, 포인터는 양 끝에 두어 가운데로 좁혀간다.

  start가 end보다 작을 때까지 반복하며, 두 수의 합의 절댓값이 twoSum[2]보다 작으면 twoSum에 현재 두 수와 합의 절댓값을 저장한다. 반복이 끝난 후 twoSum[0]과 twoSum[1]을  출력한다.

---

## 📌 이번 주 회고
- 투 포인터를 사용한 '부분합'과 '두 용액' 문제는 이전에 풀었던 투 포인터 문제들과 풀이 구조가 비슷한 것 같아 다음엔 좀 더 난이도있는 문제에 도전해보고 싶습니다.