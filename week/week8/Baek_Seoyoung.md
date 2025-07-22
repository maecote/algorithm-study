# 📘 Week 8 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.07.07 ~ 2025.07.13

## 사용 언어: JavaScript

---

### Day 1 (07.07)

- 🔗 문제: [[level 1] 소수 찾기 - 12921](https://school.programmers.co.kr/learn/courses/30/lessons/12921)
- 📁 코드: [풀이](https://github.com/sysysysyb/Study_Algorithm/tree/a0cc1760af1031ecf6e2c90e97eb8a4e94e54511/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12921.%E2%80%85%EC%86%8C%EC%88%98%E2%80%85%EC%B0%BE%EA%B8%B0)
- 💡 메모:

  ```javascript
  function solution(n) {
    const prime = [];
    let count = 0;

    // 1 ~ n 사이의 소수 리스트 생성
    for (let i = 2; i * i <= n; i++) {
      let isPrime = true;
      for (let j = 2; j * j <= i; j++) {
        // console.log(`j : ${j}`);
        if (i % j === 0) {
          isPrime = false;
          break;
        }
      }
      // console.log(`${i}는 소수`);
      {
        isPrime && prime.push(i);
      }
    }

    // console.log(prime);

    // 소수인지 확인
    for (let i = 2; i <= n; i++) {
      let isPrime = true;
      for (const p of prime) {
        if (i % p === 0) {
          isPrime = false;
          break;
        }
      }
      {
        isPrime && count++;
      }
    }

    return count + prime.length;
  }
  ```

  <h5>입출력 예</h5>
  <table class="table">
  <thead><tr>
  <th>n</th>
  <th>result</th>
  </tr>
  </thead>
  <tbody><tr>
  <td>10</td>
  <td>4</td>
  </tr>
  <tr>
  <td>5</td>
  <td>3</td>
  </tr>
  </tbody>
  </table>

  1부터 n의 제곱근보다 작거나 같은 수까지의 소수를 구해 배열에 저장하고, 1부터 n까지의 숫자들을 배열에 저장한 소수로 나누어서 나누어 떨어지는 지 확인하는 방식으로 코드를 작성했다. 이 때 배열 안에 들어 있는 소수는 이후 확인할 때 소수가 아니라고 판단이 되기 때문에(배열 안에 7이 있을 때, 7 나누기 7은 0이므로 7은 소수가 아니라고 판단됨) 정답을 반환할 때는 count 값과 prime 배열의 길이를 합쳐서 리턴했다.

---

### Day 2 (07.08)

- 🔗 문제: [[level 1] 소수 만들기 - 12977](https://school.programmers.co.kr/learn/courses/30/lessons/12977)
- 📁 코드: [재귀를 이용한 풀이](https://github.com/sysysysyb/Study_Algorithm/tree/5bece201b1c8765f7845cea73c1c2a771e4f63ec/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12977.%E2%80%85%EC%86%8C%EC%88%98%E2%80%85%EB%A7%8C%EB%93%A4%EA%B8%B0)
- 💡 메모:

  ```javascript
  function isPrime(n) {
    for (let i = 2; i * i <= n; i++) {
      if (n % i === 0) return false;
    }

    // console.log(`${n}은 소수`);
    return true;
  }

  function solution(nums) {
    const arr = [];

    function combination(idx, cnt, sum) {
      if (cnt > 2) {
        arr.push(sum);
        // console.log(`idx: ${idx}, cnt: ${cnt}, sum: ${sum}`);
        return;
      }

      for (let i = idx; i < nums.length; i++) {
        const currentSum = sum + nums[i];
        // console.log(`currentSum: ${currentSum}`);
        combination(i + 1, cnt + 1, currentSum);
      }
    }

    combination(0, 0, 0);

    const answer = arr.filter((el) => isPrime(el));

    return answer.length;
  }
  ```

  <h5>입출력 예</h5>
  <table class="table">
  <thead><tr>
  <th>nums</th>
  <th>result</th>
  </tr>
  </thead>
  <tbody><tr>
  <td>[1,2,3,4]</td>
  <td>1</td>
  </tr>
  <tr>
  <td>[1,2,7,6,4]</td>
  <td>4</td>
  </tr>
  </tbody>
  </table>

  배열 nums의 길이 중 3개를 뽑아 합하면 소수가 되는 지 확인해야 하기 때문에, 재귀 함수를 이용해서 중복 되지 않는 모든 조합의 합을 가지고 소수인지 확인하도록 코드를 작성했다.

---

### Day 3 (07.09)

- 🔗 문제: [[level 2] 최댓값과 최솟값 - 12939](https://school.programmers.co.kr/learn/courses/30/lessons/12939)
- 📁 코드: [풀이](https://github.com/sysysysyb/Study_Algorithm/tree/ccff25114ae4a4c7fd0d45209748f0993169abb3/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12939.%E2%80%85%EC%B5%9C%EB%8C%93%EA%B0%92%EA%B3%BC%E2%80%85%EC%B5%9C%EC%86%9F%EA%B0%92)
- 💡 메모:

  ```javascript
  function solution(s) {
    const arr = s.split(" ");
    const minNum = Math.min(...arr);
    const maxNum = Math.max(...arr);

    return `${minNum} ${maxNum}`;
  }
  ```

  <h5>입출력 예</h5>
  <table class="table">
      <thead><tr>
  <th>s</th>
  <th style="text-align: center">return</th>
  </tr>
  </thead>
      <tbody><tr>
  <td>"1 2 3 4"</td>
  <td style="text-align: center">"1 4"</td>
  </tr>
  <tr>
  <td>"-1 -2 -3 -4"</td>
  <td style="text-align: center">"-4 -1"</td>
  </tr>
  <tr>
  <td>"-1 -1"</td>
  <td style="text-align: center">"-1 -1"</td>
  </tr>
  </tbody>
      </table>

  주어진 문자열에 split을 사용해 숫자를 구한 다음 Math의 min과 max를 이용해서 최댓값과 최솟값을 구하도록 코드를 작성했다.

---

### Day 4 (07.10)

- 🔗 문제: [[level 2] 최솟값 만들기 - 12941](https://school.programmers.co.kr/learn/courses/30/lessons/12941)
- 📁 코드: [풀이](https://github.com/sysysysyb/Study_Algorithm/tree/ef9ae571e50cefd5ab2c1f2c163e7bb0a88e0602/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12941.%E2%80%85%EC%B5%9C%EC%86%9F%EA%B0%92%E2%80%85%EB%A7%8C%EB%93%A4%EA%B8%B0)
- 💡 메모:

  ```javascript
  function solution(A, B) {
    let result = 0;

    A.sort((a, b) => a - b); // [1, 2, 3, 4, 5]
    B.sort((a, b) => b - a); // [5, 4, 3, 2, 1]

    for (const i in A) {
      result += A[i] * B[i];
      // console.log(`i : ${i}, result : ${result}`)
    }

    // console.log(A)
    // console.log(B)
    return result;
  }
  ```

  <h5>입출력 예</h5>
  <table class="table">
      <thead><tr>
  <th>A</th>
  <th>B</th>
  <th>answer</th>
  </tr>
  </thead>
      <tbody><tr>
  <td>[1, 4, 2]</td>
  <td>[5, 4, 4]</td>
  <td>29</td>
  </tr>
  <tr>
  <td>[1,2]</td>
  <td>[3,4]</td>
  <td>10</td>
  </tr>
  </tbody>
      </table>

  각 요소를 곱한 값의 합의 최솟값이 나오려면 한 배열에서 가장 큰 수를 다른 배열의 가장 작은 수랑 곱하는 방식으로 계산해야 된다고 생각했다. 그래서 배열 A, B를 sort를 이용해서 각각 오름차순, 내림차순으로 정렬한 뒤 반복문으로 같은 인덱스의 요소를 곱하도록 코드를 작성했다.

---

## 📌 이번 주 회고

- 메인 프로젝트에 들어가기 전에 하려고 계획해뒀던 건 많은데 벌써 약 2주 밖에 남지 않았다... 시간 분배를 잘 해서 남은 기간을 잘 보내도록 노력해야겠다.
