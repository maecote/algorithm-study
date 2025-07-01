# 📘 Week 6 알고리즘 문제 풀이 기록

## ✅ 진행 날짜: 2025.06.23 ~ 2025.06.29

## 사용 언어: JavaScript

---

### Day 1 (06.23)

- 🔗 문제: [1894. Merge Strings Alternately](https://leetcode.com/problems/merge-strings-alternately/description/)
- 📁 코드: [한 문자열 당 한 포인터, 총 두 개의 포인터로 풀이](https://github.com/makee-ham/algo-gogo/tree/main/1894-merge-strings-alternately)
- 💡 메모: 힌트를 봤더니 "Use two pointers, one pointer for each string."라고 적혀 있어서 얌전히 두 개를 썼다. 그런데 Editorial을 보니 [One Pointer 풀이](https://leetcode.com/problems/merge-strings-alternately/editorial/#approach-2-one-pointer) 가 있었다! 요약하자면 i(index)를 공통 포인터로 써서, 두 문자열 중 더 긴 문자열의 길이 len를 찾은 뒤 그냥 i가 len보다 작을 때까지 1씩 더해가며... 더 짧은 쪽은 그냥 무시하고 남은 것만 다 더하고 끝내면 된다는 로직이었다.

### Day 2 (06.25)

- 🔗 문제: [1146. Greatest Common Divisor of Strings](https://leetcode.com/problems/greatest-common-divisor-of-strings/description/)
- 📁 코드: ['최대공약문자열'이라니 그게 대체 뭔데요](https://github.com/makee-ham/algo-gogo/tree/main/1146-greatest-common-divisor-of-strings)
- 💡 메모: 조건을 하나 놓쳐서 계속 실패했던 문제다. (1시간 반 동안 풀었다...) '최대공약문자열'을 찾기 위해, [ '최대'니까 가장 글자수가 많아야 하므로, 두 문자열 중 '더 짧은 문자열'로 통째로 나누는 것부터 시작해서 글자수를 점차 줄어들게 하자 ]는 아이디어까진 냈던 것 같다. 문제는 내가 이걸, '더 짧은 문자열'의 약수가 되는지부터 구하고 나서 '더 긴 문자열'로 넘어가 약수가 되는지 구했다는 것이다. 너무 복잡하게 접근했다... [ 두 문자열을 한 번의 반복에서 모두, 동시에 나눌 수 있는 가장 긴 문자열 찾기 ] 라는 설계를 진즉 생각했더라면... 모두가 행복할 수 있었을 것이다...

---

## 📌 이번 주 회고

- 미니 프로젝트 끝나고 열심히 디벨롭 하느라 이번 주도 문제를 많이 풀기 어려웠다...ㅜㅜ
- 시간 분배를 어떻게 하면 좋을지 모르겠다. 이번 주까진 어쩔 수 없었다고 해도, 다음 주부터는 원래대로 제대로 하고 싶다.
- 실습 위주로 공부하고 싶은데, 백엔드 쪽 맛보기 진도도 대강 하래도 대강 하기가 어렵고... 진퇴양난이다!!!
