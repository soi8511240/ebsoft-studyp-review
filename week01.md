# 리뷰 내용
## 2025-02-21 

- DBConnect 는 매소드 실행시 매번 새로 커넥션을 발생시켜서 써야함.<br />
  그렇지않으면 리소스 누수가 쌓이고 <br />
  메모리가 부족해져서 서버가 떨어짐. 커넥션 close를 잘해줘야댐 
- TryWithResource 에러시 커넥션 close 처리

- 매서드 추출?
- exception?
- 코드를 가독성있게.. 아따 어려운데<br />
  *DATA의 input과 output 이 눈에 보이는것이 중요*

- 구동이든 작동보단 코드퀄리티를 중점으로 봅시다.
