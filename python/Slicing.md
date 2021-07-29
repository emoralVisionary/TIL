# Slicing 관련 기억해둘만한 것들 정리

## 기본

**_Sequence_[front: back: ​step]** 형태로 정의 및 사용하며, step을 생략하는 경우 간격은 자동으로 '1' 로 설정된다.  



## 사용법

위의 예시처럼 sequence_name 뒤에 원하는 값들을 기입해서 사용하면 된다. 

기본적으로 슬라이싱을 거치면 **타입**은 원래 sequence 와 동일하다. 



## 팁 및 참고사항

- step 값이 생략되거나, 양수일 경우 front 보다 back 의 값이 커야한다. 

- `Sequence_name[ : ] ` 의 각 element 는 원래 sequence 의 element 와 그 값이 같다. <br> **다만, 슬라이싱을 통해서 값을 할당하면 새로운 id 가 부여되며, 서로 영향을 받지 않는다! 아래 예시 참조.**

  