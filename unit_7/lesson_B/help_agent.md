### @explicitHints 1

# 활동: 농사짓는 에이전트

## 단계 1
이번 활동에서는 채팅명령어가 두 개 필요해요. ``||Player:다음 채팅명령어를 입력하면||``을 두 번 가져오세요.

## 단계 2
채팅명령어 하나는 **"tp"**로, 다른 하나는 **"farm"**으로 바꾸세요.

## 단계 3
``||Agent:에이전트가 플레이어에게 텔레포트||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "tp"||``아래에 넣으세요.



### ~ tutorialhint
``` blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("farm", function () {
})
```

## 단계 4 
농사를 지으려면 땅을 개간해야 해요.  ``||Loops:반복(repeat)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "farm"||``아래에 넣으세요.


## 단계 5
이 반복 횟수는 밭의 길이를 의미해요. ``||Loops:반복(repeat)||``의 반복 횟수를 **4**에서 **6**으로 바꾸세요. 

## 단계 6
``||Agent:에이전트 경작||``, ``||Agent:에이전트 이동 방향||``을 가져와 ``||Loops:반복(repeat)||``안에 넣으세요.



### ~ tutorialhint
``` blocks
player.onChat("farm", function () {
    for (let i = 0; i < 6; i++) {
        agent.till(FORWARD)
        agent.move(FORWARD, 1)
    }
})
```

## 단계 7
에이전트가 다시 돌아가면서 땅을 개간하도록 할게요. 지금까지 코드를 실행하면 에이전트는 바라보는 방향으로 경작하면서 앞으로 가요. 이 동작은 반복구조때문에 여섯 번 반복해요. 

## 단계 8
반복 여섯 번이 끝나면 에이전트는 어디에 있게 되는지 확인해야 해요. 경작지가 한 줄 완성되었지만 우리는 한 줄 더 필요해요. 에이전트는 뒤돌아서 옆쪽에 한 줄 더 경작해야 하는 것이죠.


## 단계 9
다시 한번 ``||Loops:반복(repeat)||``을 사용해야 할 것 같아요. 그리고 에이전트가 방향을 바꾸기 위해서는 다른 명령블록이 더 필요할 것 같네요. 어렵다면 예시 코드를 확인하고 시도해보세요.


### ~ tutorialhint
``` blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("farm", function () {
    for (let i = 0; i < 2; i++) {
        for (let j = 0; j < 6; j++) {
            agent.till(FORWARD)
            agent.move(FORWARD, 1)
        }
        agent.turn(TurnDirection.Left)
        agent.move(FORWARD, 1)
        agent.turn(TurnDirection.Left)
    }
})
```

## 단계 10
이 코드를 실행해보았다면 약간의 문제가 있다는 것을 알게 되었을 거에요. 에이전트가 잘 위치해 있지 않았고 두 번째 줄이 첫 번째 줄과 정확히 맞지 않는 것 같아요.
이 문제를 어떻게 해결할 수 있을까요? 경작지의 모습이 정확한 모습이어야 해요. 에이전트가 마지막에 바라보는 방향은 크게 중요하지 않아요. 

