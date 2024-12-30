### @explicitHints 1
# 활동: 자유낙하

## 단계 1
``||Player:다음 채팅명령어를 입력하면||``을 가져오세요.

## 단계 2
``||Player:다음 채팅명령어를 입력하면||``을 마우스 오른쪽을 눌러 복사하세요. 이 동작을 한번 더 반복해서 세 개의 ``||Player:다음 채팅명령어를 입력하면||``을 만드세요. 

## 단계 3
``||Player:다음 채팅명령어를 입력하면||``의 채팅명령어를 각각 **"cr"** (크리에이티브), **"su"** (서바이벌), and **"pm"** (낙사확인)으로 바꾸세요.


## 단계 4
``||Player:플레이어가 걷고 있으면 실행||``과 ``||Player:플레이어가 사망하면 실행||``을 가져오세요.

## 단계 5
``||Player:플레이어가 걷고 있으면 실행||``의 **걷고**를  **떨어지고**로 바꾸세요.

### ~ tutorialhint
``` blocks
    player.onChat("cr", function () {

    })
    player.onChat("su", function () {

    })
    player.onTravelled(TravelMethod.Walk, function () {

    })
    player.onChat("pm", function () {

    })
    player.onDied(function () {

    })
```

## 단계 6
크리에이티브 모드로 바꿔볼까요? ``||Player:다음 채팅명령어를 입력하면: "cr"||``의 코드 작성해볼게요. 이 코드는 게임 모드를 크리에이티브로 바꿔줘요. 크리에이티브 모드에서는 비행할 수 있기 때문에 높은 곳으로 이동하는 데 도움이 돼요.

 
## 단계 7
``||Gameplay:게임 모드 변경||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "cr"||``아래에 넣으세요.


## 단계 8
``||Gameplay:게임 모드 변경||``에서 게임모드를 **크리에이티브**, 대상을 **자기자신(@s)**으로 바꾸세요.

### ~ tutorialhint
``` blocks
player.onChat("cr", function () {
    gameplay.setGameMode(
    CREATIVE,
    mobs.target(LOCAL_PLAYER)
    )
})
```

## 단계 9
이제 살아남아야죠. ``||Gameplay:게임 모드 변경||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "su"||``아래에 넣으세요.


## 단계 10
``||Gameplay:게임 모드 변경||``에서 대상을 **자기자신(@s)**으로 바꾸세요.

### ~ tutorialhint
``` blocks
player.onChat("su", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
})
```

## 단계 11
``||Variables:변수||``에서 **변수 만들기**를 누르고 변수 이름을 **fall** 로 약속하세요. 이 변숫값은 플레이어가 떨어지고 있을 때 계속해서 증가하도록 해줄거에요.

## 단계 12
떨어진다는 것을 기억하세요. ``||Variables:변수||``에서 **변수 만들기**를 누르고 변수 이름을 ``||Variables:report||``로 약속하세요.


## 단계 13
``||Variables:변숫값 증가||``를 가져와 ``||Player:플레이어가 떨어지고 있으면 실행||``아래에 넣으세요.


## 단계 14
``||Variables:변숫값 증가||``의 변숫값을 ``||Variable:fall||``로 바꾸고 증가하는 값 **0** 대신에 **1**로 바꾸세요.


## 단계 15
``||Variables:변숫값 저장||``을 가져온 다음 마우스 오른쪽 클릭하고 복사한 뒤 두 개로 만드세요.
두 개중 하나를 ``||Player:플레이어가 사망하면 실행||``아래에 넣으세요.


## 단계 16
``||Variables:변숫값 저장||``의 변숫값을  ``||Variable:report||``로 바꾸세요.


## 단계 17
변수 **fall**을 변수 **report**에 저장하도록 ``||Variables:report에 0 저장||``에 **0** 대신에 ``||Variables:변수 fall||``을 넣으세요.


## 단계 18
변수 **fall**의 값을 초기화 해주세요. 단계 15에서 생성한 ``||Variable:변숫값 저장||``을 가져와 ``||Player:플레이어가 사망하면 실행||``아래에 넣으세요. 그리고 변숫값을 **fall**로 바꾸세요.


### ~ tutorialhint
``` blocks
let fall = 0
let report = 0
player.onDied(function () {
    report = fall
    fall = 0
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
```

## 단계 19
변수 fall의 값을 알려주도록 해요. ``||Player:채팅창에 말하기||``를 ``||Player:다음 채팅명령어를 입력하면: "pm"||``아래에 넣으세요.


## 단계 20
``||Text:문자열||``카테고리에서 ``||Text:연결한 문자열||``을 가져와 ``||Player:채팅창에 말하기||``의 메시지에 넣으세요.


### ~ tutorialhint
``` blocks
let report = 0
player.onChat("pm", function () {
    player.say("Hello" + "World")
})
```

## 단계 21
변수와 메시지를 함께 보여줄게요. ``||Text:연결한 문자열||``의 첫 번째 칸에 **"You fell"**를 입력하세요. 


## 단계 22
``||Variables:변수 report||``를 가져와 ``||Text:연결한 문자열||``의 두 번째 칸에 넣으세요.


### ~ tutorialhint
```blocks
let report = 0
player.onChat("pm", function () {
    player.say("You fell " + report)
})
```
