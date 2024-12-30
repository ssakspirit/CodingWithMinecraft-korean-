### @explicitHints 1

# 활동: 나무꾼 에이전트

## 단계 1
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **tp**로 바꾸세요.

``||Agent:에이전트가 플레이어에게 텔레포트||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "tp"||``아래에 넣으세요.

## 단계 2
이제, 에이전트가 회전할 수 있도록 방향 전환 명령도 만들어 볼게요.  ``||Player:다음 채팅명령어를 입력하면: "tp"||``를 마우스 오른쪽 클릭하여 복사하세요. 그리고 채팅명령어를 **"lt"**로 바꾸세요.

## 단계 3
복사한 코드 안에 ``||Agent:에이전트가 플레이어에게 텔레포트||``를 지우고 ``||Agent:에이전트가 회전||``을 가져와 넣으세요.


### ~ tutorialhint
``` blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```

## 단계 4
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **chop**으로 바꾸세요.
나이의 높이를 알 수 있도록 변수를 만들어 볼게요. 
``||Variables:변수||``에서 **변수 만들기**를 누르고 변수 이름을 **height**로 약속하세요. 


## 단계 5
높이의 처음 값은 **0**이에요. ``||Variables:변숫값 저장||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "chop"||``아래에 넣으세요.


## 단계 6
``||Variables:변숫값 저장||``의 드롭다운메뉴에서 변수를 **height**로 선택하고 값은 **0**으로 바꾸세요.


### ~ tutorialhint
``` blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
})
```

## 단계 7
나무의 가장 아래에서 에이전트는 작업을 시작해요. 즉 "chop"명령이 실행되었을 때 에이전트는 나무의 가장 아래에 있어야 해요. "tp"와 "lt" 명령을 이용하여 에이전트를 정확한 자리에 배치시킨 다음 "chop"명령을 실행할 거에요. 이 작업을 위해 ``||Loops:반복(while)||``을 사용할 거에요. 이 반복문은 특정 조건을 만족하면 반복하는 코드예요. 에이전트 앞에 나무 블록이 있으면 계속해서 나무 위로 올라가도록 하는 것이지요.


## 단계 8
``||Loops:반복(while)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "chop"||``코드의  ``||Variables:'height'값 저장||`` 아래에 넣으세요.



## 단계 9
``||Agent:에이전트가 블록을 검사||``를 가져와 ``||Loops:반복(while)||``의 조건식에 넣으세요.


### ~ tutorialhint
``` blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {

    }
})
```

## 단계 10
에이전트는 나무 위로 올라가면서 나무의 높이를 확인해요. ``||Variables:변숫값 증가||``를 가져와 ``||Loops:반복(while)||``안에 넣으세요.
``||Variables:height 1 증가||``가 바르게 들어갔는지 확인하세요. 에이전트는 앞에 블록이 있으면 변수 height를 1증가시키고 위로 한칸 이동할거에요. 이 코드를 통해 나무의 높이를 알 수 있는 것이지요.


## 단계 11
그런데 에이전트가 위로 이동하다보면 잎이나 가지와 같은 장애물이 있을 수 있어요. 이를 제거하기 위한 코드를 작성해볼게요. ``||Agents: 에이전트가 블록 파괴||``를 가져와 ``||Variables:height 1 증가||``아래에 넣으세요. 그리고 파괴 방향을 드롭다운메뉴로 **앞으로**에서 **위로**바꾸세요. 


## 단계 12
장애물이 없으니 에이전트가 위로 이동할 수 있게 해줄게요. ``||Agent:에이전트 이동 방향||``을 가져와 넣으세요. 이전 단계에서 한 것처럼 방향을 **앞으로**에서 **위로**바꾸세요. 


### ~ tutorialhint
``` blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        height += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
})
```

## 단계 13
이제 에이전트가 나무의 높이만큼 다시 내려가도록 할게요. ``||Loops:반복(repeat)||``를 가져와 ``||Loops:반복(while)||``아래에 넣으세요.


## 단계 14
``||Variables:변수 height||``를 가져와 ``||Loops:반복(repeat)||``의 반복횟수에 넣으세요.


### ~ tutorialhint
``` blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        height += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
    for (let i = 0; i < height; i++) {

    }
})
```

## 단계 15
에이전트는 이제 내려오면서 나무를 캐게 돼요. 즉 에이전트는 나무의 가장 위까지 올라간 다음 다시 내려오면서 앞에 있는 나무 블록을 부숴 수집하는 것이지요.
``||Agent:에이전트 이동 방향 ||``과 ``||Agent:에이전트가 블록 파괴||``를 가져와 ``||Loops:반복(repeat)||``안에 순서대로 넣으세요.


## 단계 16
이제 방금 넣은 명령블록의 설정을 확인해볼게요.
에이전트는 **아래로 이동**해야 하고 **앞**에 있는 나무를 파괴해야 해요. ``||Agent:에이전트 이동 방향 ||``의 이동방향을 **아래로** 바꾸고 ``||Agent:에이전트가 블록 파괴||``의 방향은 **앞으로**되어 있는지 확인하세요.


## 단계 17
이제 마지막으로 잘라낸 나무를 수집하도록 해요.  ``||Agent:에이전트가 모든 블록 수집하기||``를 가져와 ``||Loops:반복(repeat)||``의 아래에 넣으세요. 이것은 ``||Player:다음 채팅명령어를 입력하면: "chop"||``코드의 가장 마지막 명령블록이 돼요.


### ~ tutorialhint
``` blocks 
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        height += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
    for (let i = 0; i < height; i++) {
        agent.move(DOWN, 1)
        agent.destroy(FORWARD)
    }
    agent.collectAll()
})
```
