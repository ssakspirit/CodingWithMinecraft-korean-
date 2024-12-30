### @explicitHints 1

# 활동: 미로 찾기

## 단계 1
이 활동에는 준비된 코드가 있어요. **에이전트 소개**에서 배웠던 코드예요.

```template
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("fd", function () {
    agent.move(SixDirection.Forward, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(SixDirection.Back, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
```

## 단계 2
준비된 명령을 사용하여 에이전트를 미로의 시작 지점으로 이동해요. 먼저 플레이어를 미로의 시작 부분으로 이동시키고 채팅명령어 **"tp"**를 입력하세요. 에이전트가 그쪽으로 텔레포트를 해요. 그런 다음 에이전트를 미로 안쪽으로 향하게 하려면 에이전트를 **왼쪽("lt")** 또는 **오른쪽("rt")**으로 회전시켜야 해요.



## 단계 4
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **"mr"**로 바꾸세요.
``||Loops:반복(while)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "mr"||``아래에 넣으세요.
``||Loops:반복(while)||``반복문은 특정 조건을 만족할 때까지 계속 반복해요. 즉 에이전트가 도착점의 **레드스톤 블록** 위에 있을 때까지 반복하게 할거에요.


## 단계 5
``||Logic:반대로(not)||``을 가져와 ``||Loops:반복(while)||``의 조건식에 넣으세요.


## 단계 6
``||Agent:에이전트가 블록 탐지||``을 가져와 ``||Logic:반대로(not)||``안에 넣으세요.
``||Agent:에이전트가 블록 탐지||``에서 에이전트가 탐지할 **블록**을 **redstone**으로, 탐지 방향은 **아래**로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
    }
})
```

## 단계 7
에이전트가 왼쪽으로 가는 길을 확인해요. 왼쪽으로 길이 뚫려 있는지 확인하고, 뚫려 있으면 왼쪽으로 꺾어서 앞으로 나가도록 해요.

``||Logic:만약이면 실행(if then else)||``을 가져와 ``||Loops:반복(while)||``아래에 넣으세요.

## 단계 8
``||Logic:만약이면 실행(if then else)||``의 조건식의 **true**대신에 ``||Logic:반대로(not)||``를 넣으세요.


## 단계 9
``||Agent:에이전트가 블록 탐지||``을 가져와 ``||Logic:반대로(not)||``안에 넣으세요.

## 단계 10
``||Agent:에이전트가 블록 탐지||``에서 에이전트가 탐지 방향을 **왼쪽**으로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {

        } else {

        }
    }
})
```

## 단계 11
에이전트가 왼쪽에 아무 블록이 없다는 것을 확인하면 왼쪽으로 돌아 앞으로 이동하도록 할거에요. ``||Agent:에이전트가 회전||``과 ``||Agent:에이전트가 이동 방향||``을 가져와 ``||Logic:만약이면 실행(if then else)||``아래에 넣으세요.


## 단계 12
앞으로 또는 오른쪽으로 가는 경로를 확인해야 해요. 앞과 오른쪽을 확인하기 위해 두 가지 조건을 추가해요. ``||Logic:만약이면 실행(if then else)||``아래에 **(+)** 을 두번 눌러 두 개의 ``||Logic:아니면서 실행(Else if)||``을 추가해서 모두 네 가지 경우를 만들어요.


### ~ tutorialhint
``` blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {

        } else if (false) {

        } else if (false) {

        } else {

        }
    }
})
```

## 단계 13
첫 번째 ``||Logic:아니면서 실행(Else if)||``의 조건식을 만들어 볼게요.  ``||Logic:만약이면 실행(if then else)||``의 조건식 ``||Logic:반대로(not)||``를 두 번 복사해서 첫 번째와 두 번째 ``||Logic:아니면서 실행(Else if)||``의 조건식에 각각 넣으세요. 

## 단계 14
첫 번째 ``||Logic:아니면서 실행(Else if)||``의 블록 탐지 방향을 **왼쪽**에서 **앞으로**로 바꾸세요.


## 단계 15
두 번째 ``||Logic:아니면서 실행(Else if)||``의 블록 탐지 방향을 **왼쪽**에서 **오른쪽**으로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {
            agent.turn(TurnDirection.Left)
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
        } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
        } else {
        }
    }
})
```

## 단계 16
에이전트가 앞에 있는 블록을 감지하지 못하면 앞으로 이동해야 해요. ``||Agent:에이전트가 이동 방향||``을 가져와 첫 번째 ``||Logic:아니면서 실행(Else if)||``의 경우에 넣으세요.


## 단계 17
에이전트가 왼쪽에 아무 블록이 없다는 것을 확인하면 오른쪽으로 돌아 앞으로 이동하도록 할거에요.

## 단계 18
``||Agent:에이전트가 회전||``과 ``||Agent:에이전트가 이동 방향||``을 가져와 두 번째 ``||Logic:아니면서 실행(Else if)||``의 경우에 순서대로 넣으세요.


## 단계 19
``||Agent:에이전트가 회전||``의 회전 방향은 **오른쪽**으로 바꾸세요.


## 단계 20
또는 앞에서 작성한 명령블록들을 복사해서 작성해도 좋아요.

### ~ tutorialhint
``` blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {
            agent.turn(TurnDirection.Left)
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
            agent.turn(TurnDirection.Right)
            agent.move(FORWARD, 1)
        } else {
        }
    }
})
```

## 단계 21
왼쪽, 앞쪽, 오른쪽 모두 막혀있는 막다른 골목이라면 어떻게 할까요? 이때는 에이전트가 뒤로 돌아서 반대 방향을 보도록 해야 해요.
``||Agent:에이전트가 회전||``을 두 번 가져와 ``||Logic:아니면(else)||``의 경우에 넣으세요. 
그리고 ``||Agent:에이전트가 이동 방향||``을 가져와 ``||Agent:에이전트가 회전||``아래에 넣으세요.



### ~ tutorialhint
``` blocks
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {
            agent.turn(TurnDirection.Left)
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
            agent.turn(TurnDirection.Right)
            agent.move(FORWARD, 1)
        } else {
            agent.turn(TurnDirection.Left)
            agent.turn(TurnDirection.Left)
            agent.move(FORWARD, 1)
        }
    }
})
```

## 단계 22
미로를 통과해서 레드스톤 블록을 찾았나요? 에이전트가 미로를 통과했으니 행복한 춤을 추게 할 수도 있어요. 지난 시간에 배웠던 "댄스 댄스 에이전트"를 활용해도 좋아요.


## 단계 23
춤추는 에이전트를 지금 작성해볼까요? ``||Player:다음 채팅명령어를 입력하면: "dance"||``를 가져와 채팅명령어를 dance로 바꾸고 에이전트 명령 블록을 활용해서 만들어 보세요. 그리고 완성한 채팅명령어 **"dance"**를 자동으로 실행하도록 하기 위해서는 ``||Player:다음 채팅명령어를 입력하면: "mr"||``에서 실행하도록 해요. 
``||Player:다음 채팅명령어를 실행||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "mr"||`` 코드의 가장 아래에 넣으세요. 그리고 ``||Player:다음 채팅명령어를 실행||``의 채팅명령어는 **"dance"**로 바꾸세요. 이렇게 하면 채팅명령어 **"dance"**를 따로 입력하지 않고 호출해서 실행하게 돼요.



### ~ tutorialhint
``` blocks
player.onChat("fd", function () {
    agent.move(FORWARD, 1)
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("bk", function () {
    agent.move(BACK, 1)
})
player.onChat("rt", function () {
    agent.turn(TurnDirection.Right)
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("mr", function () {
    while (!(agent.detect(AgentDetection.Redstone, DOWN))) {
        if (!(agent.detect(AgentDetection.Block, LEFT))) {
            agent.turn(TurnDirection.Left)
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else if (!(agent.detect(AgentDetection.Block, RIGHT))) {
            agent.turn(TurnDirection.Right)
            agent.move(FORWARD, 1)
        } else {
            agent.turn(TurnDirection.Left)
            agent.turn(TurnDirection.Left)
            agent.move(FORWARD, 1)
        }
    }
    player.runChatCommand("dance")
})
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(LEFT, 1)
        agent.attack(FORWARD)
        agent.move(RIGHT, 1)
        agent.move(RIGHT, 1)
        agent.move(LEFT, 1)
    }
})
```
