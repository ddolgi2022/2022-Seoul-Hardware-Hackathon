# Seoul Hardware Hackathon

## 제작 HW
![2](https://user-images.githubusercontent.com/97210816/148665884-19e1eb42-1089-4277-aa35-e6a62111187c.jpg)

## 개발 배경 이슈
1. 최근 5년간 독거노인 30% 증가 및 무연고 노인 고독사 2배 급증
2. 복지부의 '65세 이상 인구 사망자 수 및 무연고 사망자 수'에 따르면, 무연고 노인 사망자 수는 2015년 666명에서 2020년 1331명으로 약 2배(99.8%) 증가
3. 코로나 19의 확산 및 장기화로 복지관, 노인정 등을 방문하지 못해 더욱 고립된 상황


## 프로젝트 내용
### 카메라로 사람을 인지해서 주행
라즈베리파이 카메라를 이용하여 영상을 촬영 한 후 소켓 통신을 이용해 서버로 전송
서버에서 받은 영상을 처리하여 사람의 위치특정
영상의 좌표값에 따라 0~9 까지의 값을 블루투스로 STM32에 전송
받은 값에 따라 PWM 값을 조절하여 방향 제어
거리센서를 이용해 주행의 안정성 추가
동작감지 센서를 추가해 움직임이 없다고 판단 시 이메일로 알림 전송

### 치매예방 및 게임
코로나19의 장기화로 노인정, 복지관 이용의 어려움이 있음.
반려 동물이나 반려 식물을 키우는 여건이 안되는 경우도 있기에 반려 로봇의 개념을 도입함
라즈베리파이의 터치 디스플레이와 Opencv를 이용해 게임제작
치매 예방용으로 글자색 읽기, 기억력 테스트, 속담 맟추기, 연산문제 풀기, 질문에 대답하기, 초성 퀴즈가 있고
게임으로 틀린그림찾기, 숨은그림찾기, 가위바위보 를 제작

## 구성도
![3](https://user-images.githubusercontent.com/97210816/148665888-3cd4f2d4-975c-4d53-906e-1ceed4da2c03.jpg)
![4](https://user-images.githubusercontent.com/97210816/148665892-9b0937c9-3bc4-4f19-8f66-a080d46e2e55.jpg)
![5](https://user-images.githubusercontent.com/97210816/148665897-ec256bfd-9b99-44f5-b9fa-dad54e4155ab.jpg)
![6](https://user-images.githubusercontent.com/97210816/148665900-a38f7795-df54-450a-b386-f4c97c753a91.jpg)
![7](https://user-images.githubusercontent.com/97210816/148665901-7fdd70eb-396d-4899-8296-adaa3e089847.jpg)
![8](https://user-images.githubusercontent.com/97210816/148665903-3de7bbb3-ad16-492e-9dda-0957b8348381.jpg)
![9](https://user-images.githubusercontent.com/97210816/148665905-325c5261-39b5-4f8d-bd70-a8970f8370b9.jpg)
![10](https://user-images.githubusercontent.com/97210816/148665907-87fc2313-f386-42fd-b7f9-21249e08cfb8.jpg)

#### SubProcess/ 영상 촬영 , 게임
Raspberry pi 4 (OS: Raspbian)
python
opencv / socket / pygame

#### SubProcess / 영상처리 , 통신
Window
python
opencv , pyserial , SMTP

#### MainProcess/ 바퀴 제어
STM32B-L4S5I-IOT01A
c
PWM, ADC, USART, Timer
