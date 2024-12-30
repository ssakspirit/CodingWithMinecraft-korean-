### @explicitHints 1
# 활동: 화살 카운터

## 단계 1

새로운 변수를 만들고 이름을 **arrows**로 약속하세요.

## 단계 2
쏜 화살의 갯수를 기록하기 위해 ``||Player:화살을 쏘면 실행||``을 가져오세요.


## 단계 3
``||Variables:변숫값 증가||``를 가져와 ``||Player:화살을 쏘면 실행||``에 넣으세요.


## 단계 4
``||Variables:변숫값 증가||``의 변수를 ``||Variables:arrows||``로 선택하세요.

## 단계 5
변숫값을 보여주도록 할게요. ``||Player:채팅창에 말하기||``를 가져와 작성중인 코드에 이어서 넣으세요.
``||TEXT:문자열||``카테고리에서 ``||Text:문자열 연결||``을 가져와 ``||Player:채팅창에 말하기||``의 메시지에 넣으세요. 

### ~ tutorialhint
 ``` blocks
 let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Hello" + "World")
})
```
## 단계 6
변수와 메시지를 연결하여 보여줄게요. ``||Text:문자열 연결||``의 첫 번째 칸에 **"Arrows Shot"**을 입력하세요.

## 단계 7
``||Variables:변수||``에서 ``||Variables:변수 arrows||``를 가져와 ``||Text:문자열 연결||``의 두 번째 칸에 넣으세요. 이제 화살을 쏠 때마다 화면 상단에 메시지를 보여준답니다.


### ~ tutorialhint
``` blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Arrows Shot: " + arrows)
})
```

## 단계 8
마인크래프트에 돌어가서 실행해 보세요! 채팅창에 다음 명령을 입력하여 활과 화살을 받으세요.
* /give @s bow
* /give @s arrows 64
