### @explicitHints 1

# 활동: 에이전트 광장 건설

## 단계 1
에이전트 활동과 관련된 시작코드가 준비되어 있어요. 에이전트를 원하는 위치에 배치시키고 이동시키는 데 도움이 될거에요.

```template
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
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

## 단계 2
에이전트 준비가 필요할 것 같네요. 에이전트가 무언가 설치하기 위해서는 먼저 설치할 블록을 에이전트에게 주어야 해요. 채팅명령어를 사용하면 이 과정을 쉽게 해결할 수 있을 것 같지만 아직은 이 작업을 완전히 자동화할 수는 없어요. 


## 단계 3
``||Player:다음 채팅명령어를 입력하면||``을 가져와 **givegold**로 바꾸세요.


## 단계 4
블록을 먼저 자기 자신이 받은 다음 게임으로 돌아가 에이전트에게 직접 주도록 할게요. ``||Mobs:블록이나 아이템주기||``를 가져와 대상은 **자기 자신@s**, 블록은 **황금 블록**, 수량은 **64**개로 바꾸세요. 인벤토리 한칸에 최대로 보관할 수 있는 양이 64개예요.


### ~ tutorialhint
``` blocks
player.onChat("givegold", function () {
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    GOLD_BLOCK,
    64
    )
})
```

## 단계 5
에이전트에게 블록을 줄게요. 먼저 채팅명령어 **givegold**를 실행하세요. 에이전트가 가까이 있다면 걸어가도 되지만 만약 어디에 있는지 모르겠다면 채팅명령어 **tp**를 입력하여 에이전트를 불러오세요. 


## 단계 6
에이전트에 마우스 오른쪽 클릭을 하여 에이전트와 플레이어의 인벤트리를 확인하세요. 그리고 황금 블록을 에이전트에게 주세요. 황금 블록을 놓을 때는 에이전트 인벤토리의 왼쪽 상단 모서리에 놓으세요. 에이전트는 기본적으로 왼쪽 상단에 있는 아이템을 사용해요.


## 단계 7
에이전트가 작은 사각형을 만들도록 해봅시다. 이제 에이전트가 황금 블록을 가지고 있으니, 무언가를 만들어야겠죠. 지난 번 시간에 배운 황금길을 기억하나요? 그 황금길과 연결되는 사각형 모양을 만들어도 좋겠죠. 


## 단계 8
에이전트가 블록을 바꿀 수 없지만 부술 수는 있어요. 바닥을 부수고 황금블록을 대신 놓을게요. ``||Player:다음 채팅명령어를 입력하면: "fd"||``을 복사해서 채팅명령어를 **square**로 바꾸세요. 


## 단계 9
사각형 모양을 만들기 위해서, 먼저 그것을 만들기 위해 무엇이 필요한지 생각해야 해요. 큰 목표에서 시작하여 그것을 실현하는 데 필요한 작은 작업들로 하나씩 나누어서 생각하세요. 코딩을 시작하면 가장 작은 부분부터 먼저 작업하고, 진행하면서 추가하는 것이 좋아요.

## 단계 10
이제 작은 사각형을 만들어 볼게요. 목표를 달성하기 위해 황금 블록 하나를 설치하는 것부터 시작해요. 이 작업을 수행하려면 어떤 코드가 있어야 할까요? 
``||Agent:에이전트가 블록 파괴||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "square"||``아래에 넣으세요.


## 단계 11
 ``||Agent:에이전트가 블록놓기||``를 가져와 ``||Agent:에이전트가 블록 파괴||``아래에 넣으세요. ``||Agent:에이전트가 블록놓기||``의 블록 놓는 방향은 **아래로** 바꾸세요. 에이전트는 자신의 인벤토리의 왼쪽 상단에 있는 블록을 사용할 거에요.


### ~ tutorialhint
``` blocks 
player.onChat("square", function () {
    agent.destroy(DOWN)
    agent.place(DOWN)
})

```

## 단계 12
성공! 이제 이 문제를 한 단계 더 발전시켜 볼게요. 반복문을 사용해서, 정사각형의 한 면을 만들어 봅시다! 에이전트가 이동하고 블록을 부수고 놓는 동작을 여러번 반복해야 하죠. 이것은 반복문의 완벽한 예시에요.
``||Loops:반복(repeat)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "square"||``아래에 넣으세요.


## 단계 13
``||Loops:반복(repeat)||``의 반복 횟수를 **6**회로 바꾸세요.


## 단계 14
``||Agent:에이전트가 이동 방향||``을 가져와 ``||Loops:반복(repeat)||``안 ``||Agent:에이전트가 블록놓기||``아래에 넣으세요.


### ~ tutorialhint
``` blocks
player.onChat("square", function () {
    for (let i = 0; i < 6; i++) {
        agent.destroy(DOWN)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})

player.onChat("tp", function () {
    agent.teleportToPlayer()
})
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
