### @explicitHints 1

# 활동: 벌목하기

## 단계 1
이 활동에는 시작 코드가 준비되어 있어요. 
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **runchopper**로 바꾸세요.



```template
let flipturn = false
let height = 0
function chop() {
    height = 0
    while (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
        height += 1
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    }
    for (let i = 0; i < height; i++) {
        agent.move(SixDirection.Down, 1)
        agent.destroy(SixDirection.Forward)
    }
    agent.collectAll()
}
function follow() {
    agent.move(SixDirection.Forward, 1)
    if (agent.inspect(AgentInspection.Block, SixDirection.Forward) == blocks.block(Block.Grass)) {
        agent.destroy(SixDirection.Up)
        agent.move(SixDirection.Up, 1)
    } else if (!(agent.detect(AgentDetection.Block, SixDirection.Down))) {
        agent.move(SixDirection.Down, 1)
    } else {
 
    }
}
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
function turn() {
    agent.setAssist(AgentAssist.DetroyObstacles, true)
    if (flipturn) {
        agent.turn(TurnDirection.Right)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Right)
    } else {
        agent.turn(TurnDirection.Left)
        agent.move(SixDirection.Forward, 3)
        agent.turn(TurnDirection.Left)
    }
    flipturn = !(flipturn)
}
```
## 단계 2
벌목할 지역의 크기를 결정하기 위해 사각형 검색 영역의 한 쪽 길이를 나타내는 숫자를 "runchopper" 명령의 변수로 정할게요.
``||Player:다음 채팅명령어를 입력하면: runchopper||``에서  **(+)**을 눌러 변수  **num1**을 추가하고 드롭다운메뉴를 눌러 이름을 **area**로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onChat("runchopper", function(area) {

})
```

## 단계 3
“search” 함수를 만들어 볼게요. ``||Player:다음 채팅명령어를 입력하면: "runchopper"||``에 다른 함수들과 함께 호출하면 우리의 코드가 모두 완성될거에요.
``||Functions:함수||``에서 새로운 함수를 만들고 이름은 **search**로 바꾸세요.


## 단계 4
``||Functions:함수 search||``에 조건문이 필요해요. 에이전트가 주변에 나무가 있는지 확인하고 있으다면 ``||Functions:함수 chop||``를 호출하여 나무를 잘라낼거에요.


## 단계 5
``||Logic:만약이면 실행(if then else)||``을 가져와 ``||Functions:함수 search||``안에 넣으세요.
``||Logic:만약이면 실행(if then else)||``아래에 **(+)** 을 두번 눌러 두 개의 ``||Logic:아니면서 실행(Else if)||``을 추가해서 모두 네 가지 경우를 만들어요.



## 단계 6
에이전트의 왼쪽에 나무가 있는지 확인할게요. 
``||Logic:0 = 0||``을 가져와 ``||Logic:만약(if)||``의 조건식에 넣으세요.


## 단계 7
``||Agent:에이전트가 블록을 검사||``를 가져와  ``||Logic:0 = 0||``의 첫 번째 칸에 넣으세요.
``||Agent:에이전트가 블록을 검사||``의 방향은 **왼쪽**으로 바꾸세요.
``||Blocks:블록||``을 가져와 ``||Logic:0 = 0||``의 오른쪽 칸에 넣으세요.
``||Blocks:블록||``에 블록을 **참나무 원목**으로 바꾸세요.



### ~ tutorialhint
This tests to see if there is Oak Wood and if there is the agent will need to chop it!

``` blocks
function search() {
    if (agent.inspect(AgentInspection.Block, LEFT) == LOG_OAK) {

    } else if (0 == 0) {

    } else if (0 == 0) {

    } else {

    }
}
```

## 단계 8
``||Agent:에이전트가 회전||``을 가져와 ``||Logic:만약(if)||``의 경우에 넣으세요.


### ~ tutorialhint
If you do find some wood to the left of the agent, then you will want to turn the agent left and call the *chop()* function to chop down the tree. Finally, you will want the agent to turn back around and face forward again.

## 단계 9
``||Functions:호출 chop||``을 가져와 ``||Agent:에이전트가 회전||``아래에 넣으세요.
``||Agent:에이전트가 회전||``을 가져와 ``||Functions:호출 chop||``아래에 넣고 회전 방향을 **오른쪽**으로 바꾸세요.



### ~ tutorialhint

``` blocks
function search() {
    if (agent.inspect(AgentInspection.Block, LEFT) == LOG_OAK) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (false) {

    } else if (false) {

    } else {

    }
}
function chop()  {

}
```

## 단계 10
에이전트가 왼쪽에서 나무를 확인할 때 경우를 완성했어요. 이제는 앞에서 확인하는 경우를 만들어 볼게요. 앞서 경우에서 만든 코드를 활용하면 좋아요. 
앞서 작성한 ``||Logic:만약(if)||``의 조건식을 복사하여 첫 번째 ``||Logic:아니면서 실행(Else if)||``의 조건식에 넣으세요.


## 단계 11
단, 이번에는 방향이 바뀌었죠. 방금 복사한 조건식에 ``||Agent:에이전트가 블록 탐지||``의 탐지 방향을 **앞으로** 바꾸세요.
그리고 ``||Functions:호출 chop||``을 가져와 첫 번째 ``||Logic:만약(if)||``의 경우에 넣으세요.


### ~ tutorialhint
``` blocks
function search() {
    if (agent.inspect(AgentInspection.Block, LEFT) == LOG_OAK) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
        chop()
    } else if (false) {

    } else {

    }
}
function chop() {

}
```

## 단계 12
마지막으로 에이전트 오른쪽에 있는 나무 블록을 확인해야 해요. 앞서 작성한 ``||Logic:만약(if)||``의 조건식을 복사하여 두 번째 ``||Logic:아니면서 실행(Else if)||``의 조건식에 넣으세요.


### ~ tutorialhint
기본적으로 왼쪽에서 확인할 때와 같지만 몇 가지는 정반대일 거에요.


## 단계 13
방금 복사한 조건식에 ``||Agent:에이전트가 블록 탐지||``의 탐지 방향을 **오른쪽**으로 바꾸세요.
``||Agent:에이전트가 회전||``을 두 번 가져와 두 번째 ``||Logic:만약(if)||``의 경우에 넣으세요. 회전 방향은 순서대로 **오른쪽**, **왼쪽**으로 바꾸세요.


## 단계 14
``||Function:호출 chop||``을 가져와 방금 작성한 두 개의 ``||Agent:에이전트가 회전||``사이에 넣으세요.
정리하자면 에이전트가 오른쪽으로 돌아 함수를 호출한 뒤 다시 왼쪽으로 돌아 원래 방향으로 돌아오는 것이죠.


## 단계 15
``||Logic:아니면(if)||``의 경우는 그대로 남겨 둘게요.

### ~ tutorialhint
``` blocks
function search() {
    if (agent.inspect(AgentInspection.Block, LEFT) == LOG_OAK) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
        chop()
    } else if (agent.inspect(AgentInspection.Block, RIGHT) == LOG_OAK) {
        agent.turn(TurnDirection.Right)
        chop()
        agent.turn(TurnDirection.Left)
    } else {

    }
}
function chop() {

}
```

## 단계 16
에이전트가 이동하는 곳에 장애물이 있을 수도 있어요. 그때는 파괴하면서 나아가야 해요. 이 경우에는 에이전트가 쉽게 장애물을 파괴하도록 하는 명령블록을 활용할게요.
``||Agent:에이전트가 이동한 곳에 블록 놓기||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "runchopper"||``아래에 넣으세요.
그리고 ``||Agent:에이전트가 이동한 곳에 블록 놓기||``의 **이동한 곳에 블록 놓기**를 눌러 드롭다운메뉴를 열고 **장애물을 파괴하기**로 바꾸세요.


### ~ tutorialhint
``||Agent:에이전트가 이동한 곳에 블록 놓기||``는 매우 유용한 명령블록이에요. 도움말에서 활용할 수 있는 다른 경우도 활용해보세요. 에이전트 블록 파괴, 블록 놓기와 같은 명령을 반복할 필요없이 간단한 코드를 완성해줄거에요.



## 단계 17
 ``||Agent:에이전트가 장애물을 파괴하기||``의 **끄기**를 **켜기**로 바꾸세요.

## 단계 18
에이전트가 회전할 방향을 제어해야 해요. 에이전트는 마지막 이동 방향 끝에서 방향을 전환해야 합니다.
즉, 오른쪽으로 회전했다면 다음 회전은 왼쪽이 되고 그 다음 회전은 다시 오른쪽이 되어야 할거에요.
어느 방향으로 회전할 지 확인하기 위해 참거짓 변수를 만들어 볼게요. **오른쪽 회전**은 ``||Logic:참(true)||``, **왼쪽 회전**은 ``||Logic:거짓(false)||``으로 약속할게요.
``||Variables:변수 flipturn||``은 이미 생성되어 있어요. 이 변수를 참거짓 변수값으로 활용할거에요.
``||Variables:변숫값 저장||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "runchopper"||``아래에 넣으세요.
그리고 ``||Variables:변숫값 저장||``의 변수는  **flipturn**로 바꾸세요.



## 단계 19
``||Logic:거짓(false)||``을 가져와 ``||Variables:flipturn에 저장||``의 변숫값 **0**대신 넣으세요.


### ~ tutorialhint
``` blocks
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(DESTROY_OBSTACLES, true)
    flipturn = false;
})
```

## 단계 20
이제 모든 코드가 완성이 되었고 이제 제대로 모으기만 하면 돼요. 검색을 통해 에이전트를 이동하려면 에이전트가 격자의 한 행 아래로 이동하도록 하고, 끝에서 회전한 다음 사각형 영역이 완료될 때까지 행 아래로 계속 이동해요.


## 단계 21
이 기능들을 통합해 봅시다. 각 단에 대해 에이전트가 나무를 검색하고 지상 지형을 추적해요. 에이전트는 각 단을 사용하여 왼쪽, 오른쪽 및 앞으로 검색하기 때문에 검색을 통해 실제로 한 번에 세 개의 행을 검색합니다.

## 단계 22
``||Loops:반복(repeat)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "runchopper"||``의 ``||Variables:flipturn에 거짓(false)저장||``아래에 넣으세요. 


## 단계 23
채팅명령어와 함께 입력하는 변수 **area**는 각 행의 블록 갯수예요. ``||Variables:변수 area||``를 가져와 ``||Loops:반복(repeat)||``의 반복 횟수 **4**대신에 넣으세요.
이제 에이전트는 사용자가 지정한 개수에 관계없이 한 행의 모든 블록을 검색해요.
``||Functions:호출 search||``, and the ``||Functions:호출 follow||``를 가져와 ``||Loops:반복(repeat)||``아래에 넣으세요.



### ~ tutorialhint
``` blocks
let area = 0
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(DESTROY_OBSTACLES, true)
    flipturn = false
    for (let i = 0; i < area; i++) {
        search()
        follow()
    }
})
function search() {

}
function follow() {

}
```

## 단계 24
이제, 각 행의 끝에서 에이전트를 회전시켜야 해요. ``||Functions:호출 turn||``을 가져와 ``||Loops:반복(repeat)||``밖, ``||Player:다음 채팅명령어를 입력하면: "runchopper"||``의 마지막에 넣으세요.


### ~ tutorialhint
``` blocks
let flipturn = false
player.onChat("runchopper", function (area) {
    agent.setAssist(DESTROY_OBSTACLES, true)
    flipturn = false
    for (let i = 0; i < area; i++) {
        search()
        follow()
    }
    turn()
})
function search() {

}
function follow() {

}
function turn() {

}
```

## 단계 25
사각형 검색을 완료해 볼까요? 에이전트가 세 개의 행을 검색하고 나서 또 반복해주기 위해 ``||Loops:반복(repeat)||``를 한번 더 사용할게요.
``||Player:다음 채팅명령어를 입력하면: "runchopper"||``의 ``||Variables:flipturn에 거짓(false)저장||``아래의 모든 명령블록을 넣을 수 있도록 ``||Loops:반복(repeat)||``을 넣으세요.


## 단계 26
에이전트는 검색할 때 세 개의 블록을 검색하기 때문에 지정된 전체 영역에 대해 또 반복할 필요는 없어요. 그래서 주어진 면적을 3으로 나누어 반복할 거에요. 예를 들면 9X9의 영역을 검색할 때는 행을 세 번만 따라가면 된다는 것이죠.


## 단계 27
``||Math:0 ÷ 0||``을 가져와  ``||Loops:반복(repeat)||``의  **4**대신에 넣으세요.



## 단계 28
``||Variables:변수 area||``를 가져와 ``||Math:0 ÷ 0||``의 첫 번째 칸에 넣으세요.
``||Math:0 ÷ 0||``의 두 번째 칸에 **3**을 입력하세요. 
이를 코드를 테스트하려면 미리 제공된 ``||다음 채팅명령어를 입력하면: "tp"||``를 입력하여 에이전트를 자신의 위치로 순간 이동시키세요.



### ~ tutorialhint
``` blocks
let flipturn = false
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("runchopper", function (area) {
    agent.setAssist(DESTROY_OBSTACLES, true)
    flipturn = false
    for (let i = 0; i < area / 3; i++) {
        for (let i = 0; i < area; i++) {
            search()
            follow()
        }
        turn()
    }
})
function search() {
    if (agent.inspect(AgentInspection.Block, LEFT) == LOG_OAK) {
        agent.turn(TurnDirection.Left)
        chop()
        agent.turn(TurnDirection.Right)
    } else if (agent.inspect(AgentInspection.Block, FORWARD) == LOG_OAK) {
        chop()
    } else if (agent.inspect(AgentInspection.Block, RIGHT) == LOG_OAK) {
        agent.turn(TurnDirection.Right)
        chop()
        agent.turn(TurnDirection.Left)
    } else {

    }
}
function follow() {
    agent.move(FORWARD, 1)
    if (agent.inspect(AgentInspection.Block, FORWARD) == GRASS) {
        agent.destroy(UP)
        agent.move(UP, 1)
    } else if (!(agent.detect(AgentDetection.Block, DOWN))) {
        agent.move(DOWN, 1)
    } else {

    }
}
function turn() {
    agent.setAssist(DESTROY_OBSTACLES, true)
    if (flipturn) {
        agent.turn(TurnDirection.Right)
        agent.move(FORWARD, 3)
        agent.turn(TurnDirection.Right)
    } else {
        agent.turn(TurnDirection.Left)
        agent.move(FORWARD, 3)
        agent.turn(TurnDirection.Left)
    }
    flipturn = !(flipturn)
}
function chop() {
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
}
```
