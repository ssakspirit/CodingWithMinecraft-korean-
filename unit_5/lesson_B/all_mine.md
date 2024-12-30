### @explicitHints 1

# Activity: 광부 에이전트

## 단계 1
에이전트를 조종하는 코드를 작성해볼게요. ``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **do**로 바꾸세요.


## 단계 2
에이전트 명령을 처리하는 간단한 메뉴를 만들 수 있어요. ``||Logic:만약이면 실행(if then else)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면:"do"||``아래에 넣으세요.
그리고 조건문의 **(+)**을 눌러 한 가지 경우를 더 만들어 모두 세 가지 경우가 될 수 있도록 하세요.

## 단계 3
``||Player:다음 채팅명령어를 입력하면:"do"||``의 **(+)**을 눌러 변수를 추가하고 **num1**를 **AgentOrder**로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onChat("do", function (AgentOrder) {
    if (true) {

    } else if (false) {

    } else {

    }
})
```

## 단계 4
이제 에이전트가 어떤 행동을 할지 정해보도록 해요. 각 조건문에 에이전트가 텔레포트하고 회전하는 명령을 만들어 볼게요. 그리고 마지막 조건문에는 변수 **AgentOrder**에 아무것도 입력하지 않은 경우에 메시지를 보여주도록 할게요. ``||Logic:0 = 0||``를 두 번 가져와 ``||Logic:만약이면 실행(if then)||``와 ``||Logic:아니면서 만약(else if)||``조건식에 각각 넣으세요.


## 단계 5
여러분들이 입력한 **AgentOrder** 대로 명령이 실행되도록 해야해요. ``||Variables:변수 AgentOrder||``를 두 번 가져와 ``||Logic:0 = 0||``의 왼쪽 칸에 각각 넣으세요. ``||Variables:변수 AgentOrder||``가 **1**이면 텔레포트하는 것으로 하고 **2**이면 회전하는 것으로 약속할게요.



### ~ tutorialhint
``` blocks
player.onChat("do", function (AgentOrder) {
    if (AgentOrder == 1) {

    } else if (AgentOrder == 2) {

    } else {

    }
})

```

## 단계 6
마지막으로 각 경우에 에이전트가 행동하는 코드를 작성해볼게요. ``||Agent:에이전트가 플레이어에게 텔레포트||``를 가져와 ``||Logic:만약이면 실행(if then)||``안에 넣으세요.

## 단계 7
``||Agent:에이전트가 회전||``을 가져와 ``||Logic:아니면서 만약(else if)||``안에 넣으세요.


## 단계 8
마지막 경우에는 메시지를 보여줄게요. ``||Player:채팅창에 말하기||``를 가져와 ``||Logic:아니면(else)실행||``안에 넣으세요.


## 단계 9
``||Player:채팅창에 말하기||``의 메시지에 **Enter 1 to teleport or 2 to turn**라고 입력하세요.


## 단계 10
이제 땅을 파는 명령을 만들어 볼게요. ``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **dig**로 바꾸세요.


## 단계 11
서바이벌 모드에서만 채굴할 수 있어요. 크리에이티브 모드에서는 블록을 파괴할 뿐이죠. 먼저 게임모드를 바꿔줄게요. ``||Gameplay:게임 모드 변경||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: "dig"||``아래에 넣으세요.


## 단계 12
``||Gameplay:게임 모드 변경||``의 대상에 드롭다운메뉴를 눌러 **자기자신(@s)**으로 바꾸세요.


## 단계 13
``||Logic:만약이면 실행(if then else)||``을 가져와 ``||Gameplay:게임 모드 변경||``아래에 넣으세요.


### ~ tutorialhint
``` blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    if (true) {
    } else {
    }
})
```

## 단계 14
다이아몬드를 찾아볼까요? 만약 에이전트가 다이아몬드와 같은 귀한 아이템을 찾았다면 알림을 보내주는 건 어떨까요? ``||Logic:만약이면 실행(if then else)||``의 조건식에 ``||Logic:0 = 0||``를 넣으세요.


## 단계 15
``||Agent:에이전트가 블록 탐지||``를 가져와 ``||Logic:0 = 0||``의 첫 번째 칸에 넣으세요. 에이전트가 바라보는 앞쪽의 블록이 무엇인지 확인할 수 있도록 할게요.
``||Blocks:블록||``을 가져와 ``||Logic:0 = 0||``의 두 번째 칸에 넣으세요. ``||Blocks:블록||``의 드랍다운메뉴를 눌러 **다이아몬드 광물**를 선택하세요.




### ~ tutorialhint
``` blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {

    } else {

    }
})
```

## 단계 16
부자가 되어볼까요? 만약 에이전트가 **다이아몬드 광물**을 찾았다면 메시지로 보여줘야겠죠? ``||Player:채팅창에 말하기||``를 가져와 ``||Logic:만약이면 실행(if then else)||``안에 넣으세요. ``||Player:채팅창에 말하기||``의 메시지를 **"We’re rich!"**로 바꾸세요.


## 단계 17
``||Agent:에이전트가 블록 파괴||``, ``||Agent:에이전트 이동 방향||``그리고  ``||Agent:에이전트가 모든 블록 수집하기||``를 ``||Player:채팅창에 말하기||``아래로 순서대로 넣으세요.



### ~ tutorialhint
``` blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
        player.say("We're rich!")
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.collectAll()
    } else {
    }
})
```

## 단계 18
블록들을 파괴하면서 계속해서 채굴을 하는 코드를 작성해볼게요. 만약 에이전트가 다이아몬드를 발견하지 못했다면 에이전트 앞에 있는 다른 블록들을 파괴하면서 계속해서 채굴을 이어가도록 해야해요. 물론 다이아몬드가 아니라면 블록을 수집할 필요도 없죠.
``||Agent:에이전트가 블록 파괴||``, ``||Agent:에이전트 이동 방향||``을 가져와 ``||Logic:아니면서 만약(else if)||``안에 순서대로 넣으세요.


## 단계 19
이 과정을 **64**번 반복하도록 할게요. ``||Loops:반복(repeat)||``을 가져와 ``||Logic:만약이면실행(if then else)||``전체를 반복하도록 감싸 넣으세요. 즉 ``||Loops:반복(repeat)||``안에 ``||Logic:만약이면 실행(if then else)||``가 있어야 해요. ``||Loops:반복(repeat)||``의 반복횟수는 **64**로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    for (let i = 0; i < 64; i++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
            player.say("We’re rich!")
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
            agent.collectAll()
        } else {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        }
    }
})
```

## 단계 20
에이전트는 채굴하기 위해 앞으로 **64**이동했어요. 그렇다면 다시 돌아오면서 또 채굴하도록 해야겠죠. 그래서 또다른 반복을 해줘야 해요. ``||Loops:반복(repeat)||``를 가져와 원래 있던 ``||Loops:반복(repeat) 64회||``전체를 반복하도록 감싸 넣으세요. 반복 안에 또 반복이 있기때문에 이것을 중첩 반복이라고 해요. 


## 단계 21
새로운  ``||Loops:반복(repeat)||``에 횟수는 **2**로 바꾸세요. 왜냐하면 에이전트는 두 줄의 블록을 채굴하기 때문이죠. 처음 한 줄의 마지막 블록을 파괴한 다음, 에이전트는 위로 이동한 다음 뒤로 돌아야 해요.


## 단계 22
작성한 ``||Loops:반복(repeat) 2회||``코드 밖으로 이어서 코드를 작성해볼게요. ``||Agent:에이전트가 블록 파괴||``, ``||Agent:에이전트 이동 방향||``, ``||Agent:에이전트가 회전||``를 순서대로 가져와 넣으세요. 하지만 이대로는 제대로 실행이 되지 않아요. 에이전트는 위로 블록을 파괴해야 한 뒤 위로 한칸 이동하고 뒤를 돌아보기 위해 회전을 2회 해야 해요. 드롭다운 메뉴를 활용해서 완성시켜보세요.



### ~ tutorialhint
``` blocks 
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 64; i++) {
            if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE || agent.inspect(AgentInspection.Block, FORWARD) == GOLD_ORE) {
                player.say("We're rich!")
                agent.destroy(FORWARD)
                agent.move(FORWARD, 1)
                agent.collectAll()
            } else {
                agent.destroy(FORWARD)
                agent.move(FORWARD, 1)
            }
        }
        agent.destroy(UP)
        agent.move(UP, 1)
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
    }
})
```


