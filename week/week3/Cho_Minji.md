# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.02 ~ 2025.06.08  
## 사용 언어: JavaScript

---

### Day 1 (06.02)

- 🔗 문제: [인간-컴퓨터 상호작용](https://www.acmicpc.net/problem/16139)
- 📁 코드: [16139. 인간－컴퓨터 상호작용](https://github.com/minji105/algorithm/blob/main/%EB%B0%B1%EC%A4%80/Silver/16139.%E2%80%85%EC%9D%B8%EA%B0%84%EF%BC%8D%EC%BB%B4%ED%93%A8%ED%84%B0%E2%80%85%EC%83%81%ED%98%B8%EC%9E%91%EC%9A%A9/%EC%9D%B8%EA%B0%84%EF%BC%8D%EC%BB%B4%ED%93%A8%ED%84%B0%E2%80%85%EC%83%81%ED%98%B8%EC%9E%91%EC%9A%A9.js)
- 💡 메모: 누적합. 문자열 S에서 특정 알파벳이 구간 [l, r] 사이에 몇 번 나타나는지 구하는 문제. 
  
  크기가 [26][S.length]인 2차원 배열을 생성하고 각 알파벳의 누적 출현 횟수를 배열에 저장한다. 알파벳 'a'가 [l, r] 구간 사이에 나타나는 횟수는 `prefix[0][r + 1] - prefix[l]`로 구할 수 있다.
  ```js
  for (let i = 0; i < S.length; i++) {
    const char = S.charCodeAt(i) - 97;

    for (let j = 0; j < 26; j++) {
      prefix[j][i + 1] = prefix[j][i] + (j === char ? 1 : 0);
    }
  }
  ```

---

### Day 2 (06.03)

- 🔗 문제: [문자열 다루기 기본
](https://school.programmers.co.kr/learn/courses/30/lessons/12918)
- 📁 코드: [12918. 문자열 다루기 기본](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12918.%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%EB%8B%A4%EB%A3%A8%EA%B8%B0%E2%80%85%EA%B8%B0%EB%B3%B8/%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%EB%8B%A4%EB%A3%A8%EA%B8%B0%E2%80%85%EA%B8%B0%EB%B3%B8.js)
- 💡 메모: 문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 판별.
  `Number(s) ? true : false;` 방식으로 작성했다가 s가 '0'으로만 이루어진 경우를 따로 작성해주지 않아서 오답이 떴었다. 조건문을 중첩하지 않고 한 줄로 처리하고 싶어서 every() 배열 메서드를 사용했다. s의 각 문자가 '0'이상 '9'이하의 문자인지 확인한다.
  ```js
    if (s.length !== 4 && s.length !== 6)
      return false;
    return [...s].every(c => c >= '0' && c <= '9');
  ```

---

### Day 3 (06.04)

- 🔗 문제: [이중우선순위큐
](https://school.programmers.co.kr/learn/courses/30/lessons/42628#)
- 📁 코드: [42628. 이중우선순위큐](https://github.com/minji105/algorithm/blob/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/3/42628.%E2%80%85%EC%9D%B4%EC%A4%91%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84%ED%81%90/%EC%9D%B4%EC%A4%91%EC%9A%B0%EC%84%A0%EC%88%9C%EC%9C%84%ED%81%90.js)
- 💡 메모: 최소힙과 최대힙을 함께 사용하면서 두 힙의 동기화를 위해 객체를 사용.
  1. 명령어가 'I num'이면, 최소힙과 최대힙에 num을 삽입하고 map[num] 값을 1 증가시킨다.
  2. 명령어가 'D 1'이면, cleanHeap()함수 실행 후 최대힙에서 최댓값을 추출하고 map[최댓값]을 1 뺀다.
  3. 명령어가 'D -1'이면, cleanHeap()함수 실행 후 최소힙에서 최솟값을 추출하고 map[최솟값]을 1 뺀다.
     * cleanHeap(): 힙의 top 값이 map에 없는 경우 다른 힙에서 이미 삭제된 값이기 때문에 힙에서도 제거하여 정리하는 함수. 다른 힙에서 삭제된 값을 동기화하면서 메모리 누수 방지.
  4. map에 남아 있는 값 중에서 최소값과 최대값을 구함

---

### Day 5 (06.06)

- 🔗 문제: [다음 큰 숫자
](https://school.programmers.co.kr/learn/courses/30/lessons/12911)
- 📁 코드: [12911. 다음 큰 숫자](https://github.com/minji105/algorithm/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12911.%E2%80%85%EB%8B%A4%EC%9D%8C%E2%80%85%ED%81%B0%E2%80%85%EC%88%AB%EC%9E%90)
- 💡 메모: 2진수에서 1의 개수가 같은 n보다 큰 자연수 중 가장 작은 수 찾는 문제.
  처음에는 2진수에서 값을 하나씩 증가시키면서 1의 개수가 같을 때 그 2진수를 다시 숫자로 변환하여 리턴하도록 작성했다. 근데 그냥 10진수를 1씩 증가시켜도 될텐데 왜 굳이 while문을 중첩시키면서 풀었지하는 생각이 들어서 다시 풀었다.
  ```js
    const countOne = (num) => {
      return num.toString(2).split('1').length - 1;
    }
    
    const one = countOne(n);
    let result = n + 1;
    
    while (countOne(result) !== one) {
      result++;
    }
  ```
---

## 📌 이번 주 회고
- 앉아만 있는데도 체력이 고갈된다. 운동을 시작해야겠다.