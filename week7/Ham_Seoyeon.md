# 📘 Week 7 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.30 ~ 2025.07.06

## 사용 언어: JavaScript

---

### Day 1 (06.30)

- 🔗 문제: [1528. Kids With the Greatest Number of Candies](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/description/)
- 📁 코드: [최다 캔디 보유자와의 비교](https://github.com/makee-ham/algo-gogo/tree/main/1528-kids-with-the-greatest-number-of-candies)
- 💡 메모: 캔디 최다 보유자 찾기 -> extraCandies 받았을 때 최다 보유자보다 캔디 많거나 같으면 result 배열에 push true, 아니면 push false -> return result

### Big O Notation 공부 중... (필기 공유)

- 지금까지 필기한 거 공유!

https://cs.slides.com/colt_steele/big-o-notation

# simple definition

> Big O is “a numeric representation of the performance of code”

# let’s compare 2 solutions to the same problem

Q. Write a function that calculates the sum of all numbers from 1 up to (and including) some number `n`.

(ex. if `n` is 3, the result would be: 1 + 2 + 3 → 6)

Here are two working solutions of the problem:

```jsx
// solution 1
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
```

```jsx
// solution 2
function addUpTo(n) {
  return (n * (n + 1)) / 2;
}
```

How can we find _which one is better?_

→ What does “better” mean?

# What does “better” mean?

- Faster?
- Less memory-intensive?
- More readable?
- (or brevity?)

⇒ **_“Faster” speed_** and **_“Less memory-intensive”_** are often can be more importent than the others

(of course, readability IS important to write good code)

**We’re gonna focus on evaluating speed first, and then memory things.**

# Ways to evaluate “speed”

## 1. Using built-in timing functions

`performance.now()` [mdn docs](https://developer.mozilla.org/ko/docs/Web/API/Performance/now)

By adding this code below to each of those solutions, we can figure out how much seconds has passed to execute each solutions’ code.

```jsx
var time1 = performance.now();
addUpTo(1000000000);
var time2 = performance.now();
console.log(`Time Elapsed: ${(time2 - time1) / 1000} seconds.`);
```

Result: solution 2 is significantly shorter in duration with the same data
→ much more efficient & better code

But this time-based evaluation has some problems:

- Different machines will record different times
- The same machine will record different times too
- For fast algorithms, speed measurements may not be precise enough

## 2. Counting Operations

Time, can change so much. Instead of it, let’s _count_ the number of simple _operations_ that a computer has to perform— because that remains _constant_, no matter what computer we’re on.

Solution 2 → `3` operations

- 1 multiplication
- 1 addition
- 1 division

Solution 1 → `2n ~ 5n + 2` operations

`total += i`

- n additions
- n assignments

`i++`

- n additions and n assignments

`let total = 0`

- 1 assignment

`let i = 1`

- 1 assignment

`i ≤ n`

- n comparisons

But the accurate number of operations doesn’t matter— what we care about is a _“general trend”_

WE ARE FOCUSED ON _BIG PICTURE_

So in this case(Solution 1), the number of operations grow roughly in proportion with n.

---

## 📌 이번 주 회고

- 백엔드 맛보기라면서요 흑흑... 그쪽 내용이 완전히 처음이라 그런가? 강의 다 듣고 나면 자정, 과제까지 하면 새벽 1시가 넘고 그래서... 단 5분도 쉬지 않고 했는데 이러니까 할 일 다 밀려서 정말 울고 싶은 판이었다ㅠㅠㅠ...
- 1주간 리액트도 아예 손 못 댔다. 알고리즘은 틈틈이 들어보려고 했는데, Big O 등장하기 직전에 끊겼다. 그래도 우선 정리본을 공유해본다...
- 할 수 있다... 건강 챙기면서 파이팅 하자!!
