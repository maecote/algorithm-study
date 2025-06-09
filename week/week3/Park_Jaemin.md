# 📘 Week 3 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.02 ~ 2025.06.08

## 사용 언어: JavaScript

---

### Day 1 (05.19)

- 🔗 문제: [132267.콜라문제](https://school.programmers.co.kr/learn/courses/30/lessons/132267)
- 📁 코드: [lv1. 콜라 문제 - 132267](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/132267.%E2%80%85%EC%BD%9C%EB%9D%BC%E2%80%85%EB%AC%B8%EC%A0%9C)
- 💡 메모: 간단한 사칙 연산을 사용하는 문제. a개당 b개의 보너스 상품에 대한 값을 구하는 문제
  <br>

      while (n >= a) {
              const exchanged = Math.floor(n / a) * b;
              answer += exchanged;
              n = exchanged + (n % a);
          }

---

### Day 2 (05.20)

- 🔗 문제: [134240.푸드파이트대회](https://school.programmers.co.kr/learn/courses/30/lessons/134240)
- 📁 코드: [lv1. 콜라 문제 - 132267](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/134240.%E2%80%85%ED%91%B8%EB%93%9C%E2%80%85%ED%8C%8C%EC%9D%B4%ED%8A%B8%E2%80%85%EB%8C%80%ED%9A%8C)
- 💡 메모: 좌우에 같은 양의 char을 배치해야하는 문제. 중간에는 0이 와야하는 String 문자열을 만들어야 했습니다. for문을 통해서 간단하게 구현을 실행. `repeat()`를 사용하는 방식이 있는 것 같은데 이것보단 `join()`을 쓴 경우는 좋은 것 같아서 나중에 비슷한 문제를 풀 때, 참고해야 겠다.
  <br>

      food.shift();

      for(let i = 0; i < food.length; i++){
          for(let j = 0; j < Math.floor(food[i]/2); j++){
                 answer += (i + 1);
          }
      }
      answer += 0;

      for(let i = food.length - 1; i >= 0; i--){
          for(let j = 0; j < Math.floor(food[i]/2); j++){
                 answer += (i + 1);
          }
      }

---

### Day 3 (05.21)

- 🔗 문제: [12915.문자열내마음대로정렬하기](https://school.programmers.co.kr/learn/courses/30/lessons/12915)
- 📁 코드: [lv1. 문자열 내 마음대로 정렬하기 - 12915](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12915.%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%EB%82%B4%E2%80%85%EB%A7%88%EC%9D%8C%EB%8C%80%EB%A1%9C%E2%80%85%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0)
- 💡 메모: `sort()`를 사용하여 푼 문제입니다. `map()`을 통해 key로 원본 문자열, value로 n번째의 문자열을 객체로 만들고자 했는데 굳이 그렇게까지는 안해도 된다고 판단을 했습니다.
  주현님이 `localeCompare()`에 대해 설명해준 것이 기억이 나서 사용을 시작함. `localeCompare()`은 비교값에 위치에 따라 1,0,-1을 반환하는 것. `sort()`와 같이 활용하여 간단하게 정렬을 완료.
  <br>

          return strings.sort((a,b) =>
      		a[n] === b[n] ? a.localeCompare(b) : a[n].localeCompare(b[n]);

- notion: [Link](https://www.notion.so/12915-1fa389abd4258010857bfe3c4ae183a5?pvs=4)

---

### Day 4 (05.22)

- 🔗 문제: [138477. 명예의 전당(1)](https://school.programmers.co.kr/learn/courses/30/lessons/138477)
- 📁 코드: [lv1. 명예의 전당 (1)](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/138477.%E2%80%85%EB%AA%85%EC%98%88%EC%9D%98%E2%80%85%EC%A0%84%EB%8B%B9%E2%80%85%EF%BC%881%EF%BC%89)
- 💡 메모: 이번 문제는 상위 n명 중에서 최하위인 사람을 return해서 저장하는 문제였습니다. 처음에는 `for` loop와 `sort()`를 사용하여 문제를 풀었지만, `reduce`와 친해지기 위해서 `reduece`를 사용하여 새롭게 풀어봤습니다. 하지만 막상 풀고난 뒤에 보니 완전히 `reduce`를 활용한 거 같지는 않아 추가적으로 학습을 하고자 합니다.
  <br>

          function solution(k, score) {
              var answer = [];

              const data = [];

              score.reduce((acc,curr) => {
                  if(data.length < k){
                      data.push(curr);
                      data.sort((a,b) => a-b);
                      answer.push(data[0]);
                  }
                  else{
                      if(data[0] < curr){
                          data.push(curr);
                          data.shift();
                          data.sort((a,b) => a-b);
                          answer.push(data[0]);
                      }else{
                          answer.push(data[0]);
                      }
                  }
              },[]);

              return answer;
          }

<br>

- notion: [Link](https://www.notion.so/138477-1-1fb389abd42580b98302c519f041bfa9?pvs=4)

---

### Day 5 (05.23)

- 🔗 문제: [12980. 점프와 순간 이동](https://school.programmers.co.kr/learn/courses/30/lessons/12980)
- 📁 코드: [lv2. 점프와 순간 이동](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/12980.%E2%80%85%EC%A0%90%ED%94%84%EC%99%80%E2%80%85%EC%88%9C%EA%B0%84%E2%80%85%EC%9D%B4%EB%8F%99)
- 💡 메모: 이번 문제는 가장 적은 cost를 사용하여 움직이는 방법이였습니다. 0부터 N까지 가기위해서 K값이 소요하는 이동과 현재까지 이동한 거리에 \* 2만큼 이동하는 텔레포트의 비용은 0인 문제에서 가장 적은 합계 cost값을 구해야했습니다. K의 값은 정해지지 않았기 때문에 가장 적은 1을 선정하고, 2배를 이동하는 no cost를 최대한 활용하기 위해 2진수에서 1값인 것만 추출하는 방식을 사용했습니다.
  <br>

          function solution(n){
              return n.toString(2).split('').filter(e => e === '1').length;
          }

<br>

- notion: [Link](https://www.notion.so/12980-1fc389abd42580f6887efaa8686a8b86?pvs=4)

---

### Day 6 (05.24)

- 🔗 문제: [42885. 구명보트](https://school.programmers.co.kr/learn/courses/30/lessons/42885)
- 📁 코드: [lv2. 구명보트](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/42885.%E2%80%85%EA%B5%AC%EB%AA%85%EB%B3%B4%ED%8A%B8)
- 💡 메모: 이번 문제는 그리디 알고리즘을 사용했습니다. 그 중 시작과 끝점의 이동을 사용하는 투 포인터 방식을 응용하여 문제를 해결했습니다. 최대 2명씩 탈 수 있는 보트에 사람을 넣어서 움직이는 최소의 경우수를 찾아야 했기에, `sort()`를 통해 값을 정렬하고, 가장 큰값과 가장 작은 값을 이동하면서 찾을 수 있도록 했습니다. 제한을 넘기지 않는다면 start값을 올려 위치를 올려 limit에 걸리게 되면 end값을 줄이며 answer을 올리게 했습니다.

<br>

    let start = 0;
    let end = people.length - 1;

    while(start <= end ){
        if(people[start] + people[end] <= limit){
            start++;
        }
        end--;
        answer++;
    }

<br>

---

### Day 7 (05.25)

- 🔗 문제: [138476. 귤 고르기](https://school.programmers.co.kr/learn/courses/30/lessons/138476)
- 📁 코드: [lv2. 귤 고르기](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/2/138476.%E2%80%85%EA%B7%A4%E2%80%85%EA%B3%A0%EB%A5%B4%EA%B8%B0)
- 💡 메모: 이번 문제는 종류를 최소한하여, k의 값을 얻는 방법을 구하는 문제였습니다. 이러한 문제는 `Map`을 사용하여, 각각의 key값에 value를 늘려서 최소한의 가짓수를 구해야하는 것이기 때문에 `sort()`를 하여 가장 많은 경우의 수를 가진 것의 value의 값을 빼는 것으로 연산을 진행했습니다.

- notion: [Link](https://www.notion.so/138476-1fe389abd42580708863d30e1671f248?pvs=4)

---

## 📌 이번 주 회고

- 아직 다른 언어로 알고리즘을 구축하는 것이 좀 더 편하여서 JS에서 좀 더 편하게 할 수 있는 방식을 어렵게 푸는 경향이 사라지지 않았다는 생각이 많이 들었습니다. 좀 더 JS로 풀다보면 익숙해지지 않을까 생각합니다.
