# 📘 Week 4 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.09 ~ 2025.06.15

## 사용 언어: JavaScript

---

### Day 1 (06.09)

- 🔗 문제: [[level 1] 크기가 작은 부분문자열 - 147355](https://school.programmers.co.kr/learn/courses/30/lessons/147355)
- 📁 코드: [슬라이딩 윈도우 패턴을 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/147355.%E2%80%85%ED%81%AC%EA%B8%B0%EA%B0%80%E2%80%85%EC%9E%91%EC%9D%80%E2%80%85%EB%B6%80%EB%B6%84%EB%AC%B8%EC%9E%90%EC%97%B4)
- 💡 메모:

  ```javascript
  function solution(t, p) {
    // 슬라이딩 윈도우 패턴
    const pl = p.length;
    let str = "";
    let answer = 0;

    for (let i = 0; i < t.length; i++) {
      str += t[i];

      if (i >= pl - 1) {
        answer += str <= p ? 1 : 0;
        str = str.slice(1);
      }
    }

    return answer;
  }
  ```

  <h5>입출력 예</h5>
  <table class="table">
    <thead><tr>
      <th>t</th>
      <th>p</th>
      <th>result</th>
    </tr>
    </thead>
    <tbody><tr>
      <td>"3141592"</td>
      <td>"271"</td>
      <td>2</td>
      </tr>
      <tr>
      <td>"500220839878"</td>
      <td>"7"</td>
      <td>8</td>
      </tr>
      <tr>
      <td>"10203"</td>
      <td>"15"</td>
      <td>3</td>
    </tr>
    </tbody>
  </table>

  이전에 풀었던 문제를 슬라이딩 윈도우 패턴을 이용해서 다시 풀었는데, 다음 문자열을 slice(1)로 구한 게 아쉬웠다... 제대로 된 슬라이딩 윈도우 패턴 풀이는 아닌 듯 하다.

---

### Day 2 (06.10)

- 🔗 문제: [[level 1] 2016년 - 12901](https://school.programmers.co.kr/learn/courses/30/lessons/12901)
- 📁 코드: [풀이](https://github.com/sysysysyb/Study_Algorithm/tree/082ab1756606e5d1c437c01c03d0b5aae940d6fd/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12901.%E2%80%852016%EB%85%84)
- 💡 메모:

  ```javascript
  function solution(a, b) {
    // 1월 1일이 금요일 -> 나머지가 1일 때 === week[1]일 때 FRI
    const week = ["THU", "FRI", "SAT", "SUN", "MON", "TUE", "WED"];
    const month = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];

    return week[
      (month.slice(0, a - 1).reduce((acc, cur) => {
        return acc + cur;
      }, 0) +
        b) %
        7
    ];
  }
  ```

  2016년의 날짜(요일)만 구하면 되기 때문에 2016년의 월별 일수랑 요일 순서를 하드 코딩하고 reduce로 계산했다.

---

### Day 3 (06.11)

- 🔗 문제: [[level 1] 모의고사 - 42840](https://school.programmers.co.kr/learn/courses/30/lessons/42840)
- 📁 코드: [풀이](https://github.com/sysysysyb/Study_Algorithm/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/42840.%E2%80%85%EB%AA%A8%EC%9D%98%EA%B3%A0%EC%82%AC)
- 💡 메모:

  ```javascript
  function solution(answers) {
    const arr1 = [1, 2, 3, 4, 5];
    const arr2 = [2, 1, 2, 3, 2, 4, 2, 5];
    const arr3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5];
    const tests = [
      { id: 1, score: 0 },
      { id: 2, score: 0 },
      { id: 3, score: 0 },
    ];
    const answer = [];

    for (const [idx, el] of answers.entries()) {
      if (arr1[idx % 5] === el) tests[0].score++;
      if (arr2[idx % 8] === el) tests[1].score++;
      if (arr3[idx % 10] === el) tests[2].score++;
    }

    const maxScore = Math.max(tests[0].score, tests[1].score, tests[2].score);
    tests.forEach(({ id, score }) => {
      if (score === maxScore) answer.push(id);
    });
    return answer;
  }
  ```

  3명의 학생이 자기 만의 문제 찍는 패턴이 정해져 있는데, 인자로 주어진 시험 답안으로 채점했을 때 가장 높은 점수가 무엇인지 리턴하는 문제였다. 뭔가 조금은 현실적인(?) 상황의 문제라서 재밌었다.

---

# 📘 Week 5 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.16 ~ 2025.06.22

(프로젝트, 심화반 보강 등등으로 한 주 휴식)

---

# 📘 Week 6 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.23 ~ 2025.06.29

## 사용 언어: JavaScript

---

### Day 3 (06.25)

- 🔗 문제: [[level 1] 과일 장수 - 135808](https://school.programmers.co.kr/learn/courses/30/lessons/135808?language=javascript)
- 📁 코드: [풀이](https://github.com/sysysysyb/Study_Algorithm/tree/4f9605e7f9d67ce18dd9e44cf8fec1c6a7153310/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/135808.%E2%80%85%EA%B3%BC%EC%9D%BC%E2%80%85%EC%9E%A5%EC%88%98)
- 💡 메모:

  ```javascript
  function solution(k, m, score) {
    // [4,4,4, 4,4,4, 2,2,2, 2,1,1] -> 4 4 2 1
    score.sort((a, b) => b - a);

    let maxSum = 0;
    const boxCount = Math.floor(score.length / m);

    for (let i = m - 1; i < boxCount * m; i += m) {
      maxSum += score[i] * m;
    }

    return maxSum;
  }
  ```

  **문제 조건이 자꾸 헷갈림 + 오랜만에 풀어서 머리가 굳음** 이슈로 푸는 데 엄청 오래 걸렸던 문제... 빈도수 세기 패턴을 가져와서 효울적으로 풀어보고 싶었는데 결국 실패하고 sort로 정렬해서 풀었다.

---

### Day 4 (06.26)

- 🔗 문제: [3442-maximum-difference-between-even-and-odd-frequency-i](https://leetcode.com/problems/maximum-difference-between-even-and-odd-frequency-i/description/)
- 📁 코드: [빈도수 세기 패턴을 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/main/LeetCode/3442-maximum-difference-between-even-and-odd-frequency-i)
- 💡 메모:

  ```javascript
  /**
   * @param {string} s
   * @return {number}
   */

  var maxDifference = function (s) {
    const countChar = {};
    const frequency = { odd: 0, even: 100 };

    for (const char of s) {
      countChar[char] = countChar[char] + 1 || 1;
    }

    Object.values(countChar).forEach((el) => {
      if (el % 2 === 0) {
        frequency.even = Math.min(frequency.even, el);
      } else {
        frequency.odd = Math.max(frequency.odd, el);
      }
    });

    return frequency.odd - frequency.even;
  };
  ```

  문자열에서 각 문자가 나온 빈도수를 구한 다음, 빈도수 중 가장 큰 홀수에서 가장 작은 짝수를 뺀 값은 반환하는 문제였다. 빈도수 세기 패턴으로 문자열의 빈도수를 구해서 풀었다.

---

### Day 6 (06.28)

- 🔗 문제: [0643-maximum-average-subarray-i](https://leetcode.com/problems/maximum-average-subarray-i/description/)
- 📁 코드: [슬라이딩 윈도우 패턴을 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/339b5a330327a82d3b5c2fdc608e738139383747/LeetCode/0643-maximum-average-subarray-i)
- 💡 메모:

  ```javascript
  /**
   * @param {number[]} nums
   * @param {number} k
   * @return {number}
   */
  var findMaxAverage = function (nums, k) {
    let prevSum = 0;
    const len = nums.length;

    for (let i = 0; i < k; i++) {
      prevSum += nums[i];
    }

    let maxSum = prevSum;

    for (let i = k; i < len; i++) {
      prevSum += nums[i] - nums[i - k];
      maxSum = Math.max(maxSum, prevSum);
    }

    return maxSum / k;
  };
  ```

  배열 안에 있는 숫자들을 k개씩 묶어서 더했을 때 가장 높은 평균 값을 찾는 문제였다. 슬라이딩 윈도우 패턴을 이용해서 앞의 값을 제거하고 뒤의 값을 더하면서 최대값을 찾았다.

---

## 📌 이번 주 회고

- 프로젝트만 하다가 알고리즘 문제를 다시 풀려니까 어렵다... 다시 꾸준히 문제를 풀면서 감을 찾도록 노력해야겠다🙃
