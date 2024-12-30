### @explicitHints 1
# 에이전트를 소개합니다!

## 단계 1
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **"tp"**로 바꾸세요.



### ~ tutorialhint
```blocks
player.onChat("tp", function () {})
```

## 단계 2
에이전트를 텔레포트 시켜볼게요. ``||Agent:에이전트가 플레이어에게 텔레포트||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "tp"||``아래에 넣으세요.


### ~ tutorialhint
```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## 단계 3
이제 마인크래프트에서 채팅창에 **tp**를 입력하면 에이전트가 사용자의 위치로 바로 순간이동해요. 이 코드는 에이전트를 사용할 때마다 필요할 수 있어요. 에이전트를 이동하고 회전시키는 추가 명령도 이제 만들어 볼 수 있을거에요.



### ~ tutorialhint
```blocks 
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
```

## 단계 4
이렇게 하면 에이전트를 보다 쉽게 정확하게 제어할 수 있어요. 또는 언제든지 채팅명령어 **tp**로 에이전트를 원하는 위치로 불러올 수도 있지요.

