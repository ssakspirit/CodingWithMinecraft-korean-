 ### @explicitHints 1
 
# 활동: 이삿짐 회사

## 단계 1
``||Player:다음 채팅명령어를 입력하면||`` 을 세 번 가져오세요. 각각의 채팅명령어를 **"start"**, **"stop"**, 그리고 **"copy"**로 바꾸세요.


### ~ tutorialhint
```blocks
player.onChat("start", function () { })
player.onChat("stop", function () { })
player.onChat("copy", function () { })
```

## 단계 2
``||Variables:변수||``카테고리에서 **변수만들기**를 눌러 변수를 만드세요.
변수 이름은 **start**로 하고 **확인**버튼을 누르세요.


## 단계 3
같은 방법으로 이름이 **stop**인 변수를 하나 더 만드세요. 

## 단계 4
변수를 설정해볼게요.
``||Variables: 변수에 저장||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: start||`` 아래에 넣으세요.
``||Variables: 변수에 저장||``의 변수는 **start**으로 바꾸세요.


## 단계 5
``||Player:플레이어 절대좌표||``를 가져와 ``||Variables: start에 저장||``의 **0**에 넣으세요.

### ~ tutorialhint
```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
})
```
## 단계 6
메시지를 보여주도록 할게요. ``||Player:채팅창에 말하기||``를 가져와 ``||Variables: start에 저장||``아래에 넣으세요.

### ~ tutorialhint
```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Hi!")
})
```

## 단계 7
``||Text:문자열||``카테고리에서 ``||Text:연결한 문자열||``을 가져와 ``||Player:채팅창에 말하기||``의 메시지에 넣으세요.
``||Text:연결한 문자열||``의 첫 번째칸에 **"Starting Point Set"**라고 입력하세요.


## 단계 8
그 다음 ``||Variables: 변수||``카테고리에서 ``||Variables: 변수 start||``를 가져와``||Text:연결한 문자열||``의 두 번째 칸에 넣으세요.


### ~ tutorialhint
```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Starting Point Set: " + start)
})

```

## 단계 9
``||Player:다음 채팅명령어를 입력하면: stop||``은 이전에 작성한 코드를 활용할게요. ``||Player:다음 채팅명령어를 입력하면: start||``를 오른쪽 클릭하고 복사를 선택하세요. 그리고 채팅명령어를 **stop**으로 바꾸세요. ``||Player: 채팅창에 말하기||``의 메시지를 **"Stopping Point Set"**으로 바꾸고 ``||Variables: 변수 start||``를 눌러 ``||Variables: 변수 stop||``으로 바꾸세요.


### ~ tutorialhint
``` blocks
let stop: Position = null
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping Point Set: " + stop)
})
```
## 단계 10
단계1에서 생성한 ``||Player:다음 채팅명령어를 입력하면: stop||``은 삭제하세요.


## 단계 11
구조물을 복사하는 코드를 작성할게요. ``||Blocks:블록||``카테고리에 첫 번째 ``||Blocks:블록 복사하기||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: copy||``에 넣으세요.

### ~ tutorialhint
``` blocks
player.onChat("copy", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 단계 12
``||Variables:변수||``카테고리에서 변숫값 ``||Variables:start||``을 가져와 ``||Blocks:블록 복사하기||``의 **시작좌표**에 넣으세요. 이 좌표는 블록 **복사의 시작점**을 의미해요.


## 단계 13
``||Variables:변수||``카테고리에서 변숫값 ``||Variables:stop||``을 가져와 ``||Blocks:블록 복사하기||``의 **끝좌표**에 넣으세요. 이 좌표는 블록 **복사의 끝점**을 의미해요.


### ~ tutorialhint
```blocks
player.onChat("copy", function () {
    let stop: Position = null
    let start: Position = null
    blocks.clone(
    start,
    stop,
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 단계 14
마인크래프트로 돌아가 코드를 실행해 볼게요. 먼저 여러분이 복사하고 싶은 집이나 구조물을 만들어 보세요. 그리고 플레이어를 구조의 아래쪽 모서리 중 하나로 이동하고 대화창에 "start" 명령을 입력하세요.


## 단계 15
"start"명령을 실행한 곳으로부터 대각선 상단 모서리로 이동하세요. 그리고 대화창에 "stop" 명령을 입력하세요.
복사할 구조물이 저장되었어요. 이제 구조물을 복사할 빈 공간으로 이동하고 대화창에 "copy" 명령을 입력하세요.
어떤가요? 구조물이 그대로 복사되었나요?

### ~ tutorialhint
``` blocks
let start: Position = null
let stop: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Starting Point Set: " + start)
})
player.onChat("copy", function () {
    blocks.clone(
    start,
    stop,
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
player.onChat("stop", function () {
    stop = player.position()
    player.say("Stopping Point Set: " + stop)
})
```
