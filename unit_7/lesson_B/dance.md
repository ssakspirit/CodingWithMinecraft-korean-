### @explicitHints 1

# 활동: 댄스 댄스 에이전트

## 단계 1
에이전트가 춤추는 코드를 만들어 볼게요. ``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **dance**로 바꾸세요.


## 단계 2
에이전트가 춤추는 동작을 ``||Agent:에이전트 이동 방향||``과 ``||Agent:에이전트 회전||``을 이용해서 만들어 보세요. 힌트에 나오는 코드는 한 가지 예시예요. 

### ~ tutorialhint
``` blocks
player.onChat("dance", function () {
    agent.move(LEFT, 1)
    agent.attack(FORWARD)
    agent.move(RIGHT, 1)
    agent.move(RIGHT, 1)
    agent.move(RIGHT, 1)
    agent.turn(TurnDirection.Left)
    agent.move(LEFT, 1)
})
```

## 단계 3
댄스는 계속되어야 하죠. ``||Loops:반복(repeat)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "dance" ||``아래에 작성한 코드가 모두 들어가도록 넣으세요.


## 단계 4
 ``||Loops:반복(repeat)||``의 반복 횟수를 원하는 만큼 입력해보세요.


### ~ tutorialhint
``` blocks
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(LEFT, 1)
        agent.attack(FORWARD)
        agent.move(RIGHT, 1)
        agent.move(RIGHT, 1)
        agent.move(RIGHT, 1)
        agent.turn(TurnDirection.Left)
        agent.move(LEFT, 1)
    }
})
```

## 단계 5
에이전트가 어디있죠? 에이전트가 춤추는 것을 보려면 에이전트가 근처에 있어야 하겠죠. 기억하세요. 에이전트는 텔레포트 할 수 있어요. 에이전트를 불러오는 채팅명령어를 만들어 볼게요.

## 단계 6
새로운 ``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **tp**로 바꾸세요.


## 단계 7
``||Agent:에이전트가 플레이어에게 텔레포트||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "tp"||``아래에 넣으세요.


## 단계 8
마인크래프트로 돌아가 채팅창에 **tp**를 입력하여 에이전트를 플레이어의 위치로 불러오세요. 그리고 채팅창에 **dance**입력하여 춤추게 해주세요.


### ~ tutorialhint
``` blocks
player.onChat("dance", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(LEFT, 1)
        agent.attack(FORWARD)
        agent.move(RIGHT, 1)
        agent.move(RIGHT, 1)
        agent.move(RIGHT, 1)
        agent.turn(TurnDirection.Left)
        agent.move(LEFT, 1)
    }
})
player.onChat("tp", function () {
    agent.teleportToPlayer()
})

```
