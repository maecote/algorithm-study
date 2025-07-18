# 📘 Week 8 알고리즘 학습 기록

## ✅ 진행 날짜: 2025.07.07 ~ 2025.07.13

## 사용 언어: JavaScript

---

### Big O Notation 강의 정리

[Big-O-Notation.md](https://github.com/makee-ham/algo-gogo/blob/main/JS-algo-ds-masterclass/01-Big-O-Notation/Big-O-Notation.md)

- "더 나은 코드"가 뭘까? 라고 했을 때, < 1) 처리 속도가 빠르고 2) 메모리 집약적이지 아니한 > 코드라는 관점에서 출발하여 코드들의 성능을 평가한다고 하니 이해가 잘 됐습니다.
- 속도의 측면에서 내장된 타이밍 함수들을 써서 비교하는 건 부정확하니, 컴퓨터가 처리하는 연산자의 수를 세자~ 여기서 정확한 개수가 아닌 general trend(일반적 경향성)을 보는 시선으로 단순화 해서(+ 그중에서도 Worst Case Scenario를 상정하여) Big O 표기법이 나왔다는 과정이 흥미로웠습니다.
- 공간 복잡도에 대해서 처음으로 자세히 알게 되었습니다.
  - booleans, numbers, undefined, null -> constant space -> O(1)
  - strings -> string length === n -> O(n)
  - Reference types -> array length, the number of object keys === n -> "generally" O(n)
    - 참조 타입에 관해 기술적으로 정확히는 "length"에 대한 게 아니라고 하지만, 여기선 개념 이해를 위해 러프하게 짚고 넘어갔다고 합니다.
- 로그가... 분명 학생 때 배웠을 텐데 기억이 잘 안 나서 와닿지가 않더라고요. 거듭제곱의 반대 개념 느낌~ 이라고는 하는데, 이진 탐색으로 생각해보면 n 크기의 문제를 반씩 잘라서 푼다... 근데 이것도 좀 모호해요. 앞으로 진도 나가면서 예시와 설명 많으니 익혀가면 된다고는 하더라고요. 믿습니다ㅠㅠ

---

## 📌 이번 주 회고

- 모두에게 말씀드렸던 대로, 현재 상황에선 실습과 구현부터 익히는 것이 중요도가 높아 알고리즘은 강의를 시간 날 때마다 듣고 정리하는 식으로 공부하고자 합니다. (거기에 퀴즈도 있어서, 이론을 적용해 보면서 익힐 수 있더라고요!)
- 영어 공부가 될 수 있도록 못하는 영어지만, 부러 영어 강의를 영어 자막으로 보고 영문으로 필기하고 있습니다... (오래 걸리네요...) 가능한 만큼 지속해보려고 합니다.
- 파이팅!
