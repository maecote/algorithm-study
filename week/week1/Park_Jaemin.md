# 📘 Week n 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.05.19 ~ 2025.05.25  
## 사용 언어: JavaScript

---

### Day 1 (05.19)

- 🔗 문제: [132267.콜라문제](https://school.programmers.co.kr/learn/courses/30/lessons/132267)
- 📁 코드: [lv1. 콜라 문제 - 132267](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/132267.%E2%80%85%EC%BD%9C%EB%9D%BC%E2%80%85%EB%AC%B8%EC%A0%9C)
- 💡 메모: 간단한 사칙 연산을 사용하는 문제. a개당 b개의 보너스 상품에 대한 값을 구하는 문제
    ```
    while (n >= a) {
            const exchanged = Math.floor(n / a) * b;
            answer += exchanged;
            n = exchanged + (n % a);
        }
    ```

### Day 2 (05.20)

- 🔗 문제: [134240.푸드파이트대회](https://school.programmers.co.kr/learn/courses/30/lessons/134240)
- 📁 코드: [lv1. 콜라 문제 - 132267](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/134240.%E2%80%85%ED%91%B8%EB%93%9C%E2%80%85%ED%8C%8C%EC%9D%B4%ED%8A%B8%E2%80%85%EB%8C%80%ED%9A%8C)
- 💡 메모: 좌우에 같은 양의 char을 배치해야하는 문제. 중간에는 0이 와야하는 String 문자열을 만들어야 했습니다. for문을 통해서 간단하게 구현을 실행. `repeat()`를 사용하는 방식이 있는 것 같은데 이것보단 `join()`을 쓴 경우는 좋은 것 같아서 나중에 비슷한 문제를 풀 때, 참고해야 겠다.
    ```
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
    ```

---

### Day 3 (05.21)

- 🔗 문제: [12915.문자열내마음대로정렬하기](https://school.programmers.co.kr/learn/courses/30/lessons/12915)
- 📁 코드: [lv1. 문자열 내 마음대로 정렬하기 - 12915](https://github.com/jamminP/javascript-algorithms/tree/main/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EC%8A%A4/1/12915.%E2%80%85%EB%AC%B8%EC%9E%90%EC%97%B4%E2%80%85%EB%82%B4%E2%80%85%EB%A7%88%EC%9D%8C%EB%8C%80%EB%A1%9C%E2%80%85%EC%A0%95%EB%A0%AC%ED%95%98%EA%B8%B0)
- 💡 메모: 좌우에 같은 양의 char을 배치해야하는 문제. 중간에는 0이 와야하는 String 문자열을 만들어야 했습니다. for문을 통해서 간단하게 구현을 실행. `repeat()`를 사용하는 방식이 있는 것 같은데 이것보단 `join()`을 쓴 경우는 좋은 것 같아서 나중에 비슷한 문제를 풀 때, 참고해야 겠다.
    ```
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
    ```
- notion: [Link](https://www.notion.so/12915-1fa389abd4258010857bfe3c4ae183a5?pvs=4)

---

## 📌 이번 주 회고
- 