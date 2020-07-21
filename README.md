# 방범키트 제작 (매화 TEAM)

**제작 목적 및 개념도**

> 자택 및 사업장에서 외출 혹은 가게에 사람이 없을 경우에 경비를 위해 만든 방범 키트입니다
외출 시 ON / 복귀 시 OFF 으로 설정 (ON일 때 감지하도록 만듬)
외출 시 사람이 감지되는 경우에는 감지된 사람을 사진 캡처 하기 위해 백색등이 켜지고 1.5초 뒤 사진 캡처가 된 후에 경고등인 빨간색으로 변경되고 텔레그램으로 감지 시간과 사진 캡처본이 전송

**사용된 모듈** 

* 라즈베리파이 3B+
* 카메라 모듈 (캡처기능)
* 마이크로비트 인체 감지 센서 [PIR 센서]
* LED 통합센서모드 (문 외부 상단 설치)
* 스마트터치보드

**개발 과정**

1. 인체감지센서, 카메라 
* 라즈베리파이 3B+ 인체 감지 센서 실행, 카메라 모듈에 카메라 촬영 및 캡처 성공

2. LED 
* 라즈베리파이 통합센서 이용하여 인체감지센서를 이용한 LED 조명  
> RGB / 
X: 빨간색 / 
O: 백색 /
W: 파란색 

``` 
def sense (update, context) : 
sense = sense Hat()

x = [255, 0, 0]
o = [255, 255, 255]
w = [0, 84, 255]
question_mark = [
o, o, o, o, o, o, o, o, 
o, o, o, o, o, o, o, o, 
o, o, o, x, x, o, o, o,
o, o, x, x, x, x, o, o,
o, o, w, w, w, w, o, o, 
o, o, o, w, w, o, o, o, 
o, o, o, o, o, o, o, o,
o, o, o, o, o, o, o, o
]
sense. set_pixels(question_mark)
time,sleep(2)

sense.clear(255, 0, 0)

def off (update, context) : 

def off (update, context) :
sense = senseHat ()
sense.clear(0, 0, 0)
```

