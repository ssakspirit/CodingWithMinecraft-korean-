### @explicitHints 1

# 활동: 피라미드 건설

## 단계 1
이 활동에는 미리 준비된 코드가 있어요.


```template
player.onChat("tp", function () {
        player.teleport(positions.create(3, 0, 3))
        agent.teleportToPlayer() 
        player.teleport(positions.create(-3, 0, -3)) 
}) 
player.onChat("pyramid", function (BaseSize) {
        agent.setAssist(AgentAssist.PlaceOnMove, true)
        for (let i = 0; i <= 3; i++) {
                agent.move(SixDirection.Forward, BaseSize - 1)
                agent.turn(TurnDirection.Left)
        } 
        agent.move(SixDirection.Up, 1)
        agent.setAssist(AgentAssist.PlaceOnMove, false)
        agent.move(SixDirection.Forward, 1)
        player.runChatCommand("pyramid " + (BaseSize - 2))
})
player.onChat("turn", function () {
        agent.turn(TurnDirection.Left)
})
```
## 단계 2
이 코드를 실행해보고 코드의 문제점을 찾아보세요. 뭔가 이상한 점을 발견할 수 있을거에요.


## 단계 3
에이전트에게 블록을 주도록 할게요.
게임으로 돌아가 채팅명령어 **tp**를 실행하고 에이전트를 가까이 불러오세요. 에이전트 회전 명령도 입력할 수 있지만 꼭 하지 않아도 괜찮아요.
에이전트에게 마우스 오른쪽 클릭을 하여 아이템창을 열고 건축에 사용할 블록을 에이전트의 아이템 슬롯으로 옮기세요.


## 단계 4
채팅명령어 **pyramid 5**를 입력하고 어떻게 에이전트가 명령을 수행하는지 보세요. 에이전트가 계속 반복해서 짓고 있기만 하면서 코드가 무한반복해요. 이것은 코드의 맨 끝에서 코드를 다시 호출하기 때문에 발생하는 문제예요.


### ~ tutorialhint
```blocks
let BaseSize = 0
player.runChatCommand("pyramid " + (BaseSize - 2))
```

## 단계 5
이 코드에 **조건문**을 추가해서 무한 반복을 멈추도록 해볼게요.


### ~ tutorialhint
If you are caught in an infinite loop, you will need to stop your code from the code connection window. Click the stop button in the lower-left corner of your code connection window.

## 단계 6
무한 반복을 멈춰볼까요? 반복을 멈추기 위해서 코드를 중지하도록 판단하는 변수를 활용해야겠죠. 이런 상황에서는 조건문을 사용하는 것이 좋아요. 
``||Logic:만약이면 실행(if then else)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "pyramid"||``안의 모든 명령블록을 둘러싸도록 넣으세요.


### ~ tutorialhint
```blocks
player.onChat("pyramid", function (BaseSize) {
    if (true) {
        agent.setAssist(PLACE_ON_MOVE, true)
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 단계 7
이제 조건식을 입력해볼게요. **BaseSize**가 **0**아래로 내려가면 반복이 중지되도록 해요. 다시 채팅명령어가 시작할 때 **BaseSize**는 **2**가 줄어 들고 있어요.


<!--
```blocks
let BaseSize = 0
player.runChatCommand("pyramid " + (BaseSize - 2))
```
-->

## 단계 8
``||Logic:0 = 0||`` 또는 ``||Logic:0 < 0||``가져와 ``||Logic:만약이면 실행(if then else)||``의 조건식에 넣으세요. 

### ~ tutorialhint
```blocks
let MadePyramid = false
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(PLACE_ON_MOVE, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})

```

## 단계 9
``||Variables:변수 BaseSize ||``를 가져와 조건식에 넣어 ``||Logic: BaseSize > 0||``를 완성하세요. 이제 **BaseSize**가 0보다 커야만 블록을 놓을거에요. 만약 그렇지 않다면 메시지를 보여주도록 할수도 있어요.

### ~ tutorialhint
```blocks
let MadePyramid = false
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(PLACE_ON_MOVE, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 단계 10
이렇게 조건문으로 무한 반복이 멈췄어요. 이 코드를 더 개선할 방법이 있을까요? **BaseSize**가 0이 되는 경우는 두 가지예요. 에이전트가 방금 피라미드 건축을 마쳤거나 플레이어가 채팅명령어를 입력할 때 피라미드의 크기 **BaseSize**를 입력하지 않은 경우이지요. 이 경우를 포함하려면 조건식에 새로운 경우를 추가하여 해결할 수 있겠지요.

## 단계 11
앞서 설명한 경우를 코드로 구현할 수 있을까요? 이것을 해결하기 전에 최종 코드를 자세히 살펴보세요. 해결을 위한 힌트가 있을거에요.

### ~ tutorialhint
```blocks
let MadePyramid = false
// Teleports the agent near you but a little away so
// you have time to get out of his way when he starts
// building
player.onChat("tp", function () {
    player.teleport(pos(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(pos(-3, 0, -3))
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("pyramid", function (BaseSize) {
    // Detect if we should continue building pyramid
    if (BaseSize > 0) {
        agent.setAssist(PLACE_ON_MOVE, true)
        // Builds one level of the pyramid
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 단계 12
변수와 조건문 활용해서 이 도전과제를 완수하세요.


