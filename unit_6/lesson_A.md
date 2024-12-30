### @explicitHints 1

# 활동: 신뢰의 도약

## 단계 1
**고급**카테고리를 눌러 더 많은 카테고리를 확인하세요. ``||Functions:함수||``카테고리에서 함수만들기를 눌러 함수의 이름은 **pool**하고 **완료**를 눌러 함수를 만드세요.


## 단계 2
같은 방법으로 함수 두 개를 더 만들어 줄게요. 이름은 각각**platform**, **teleport**으로 바꾸세요.



## 단계 3
``||Loops:시작하면 실행||``가져오세요. 그리고 ``||Functions:호출 pool||``, ``||Functions:호출 platform||``, ``||Functions:호출 teleport||``를 가져와 ``||Loops:시작하면 실행||``아래에 넣으세요.

### ~ tutorialhint
``` blocks
pool()
platform()
teleport()
function pool(){}
function platform(){}
function teleport(){}
```

## 단계 4
``||Loops:시작하면 실행||``은 코드작성기가 시작될 때 실행돼요. 즉 코드작성기의 오른쪽 아래 초록색 버튼을 누르면 마인크래프트로 돌아가면서 바로 실행되는 것이지요.


## 단계 5
함수 pool을 작성해볼게요. ``||Blocks:블록 채우기||``를 가져와 ``||Functions:pool||``아래에 넣으세요. ``||Blocks:블록 채우기||``로 시작좌표와 끝좌표를 잇는 3차원 상자 공간을 블록으로 채울 수 있어요.


## 단계 6
``||Blocks:블록 채우기||``의 채울 블록을 **물**로 바꾸세요.
시작좌표는 **(0, -1, 0)**, 끝좌표는  **(2, -3, 2)**로 바꾸세요.

### ~ tutorialhint
``` blocks
function pool() {
    blocks.fill(
    WATER,
    pos(0, -1, 0),
    pos(2, -3, 2),
    FillOperation.Replace
    )
}
pool()
```

## 단계 7
도약을 위한 바닥을 만들어 볼게요. ``||Blocks:블록 채우기||``새로 가져와 ``||Functions:platform||``아래에 넣으세요. 채울 블록은 **참나무 판**으로 바꾸세요.


## 단계 8
``||Blocks:블록 채우기||``의 시작좌표는 **(1, 64, 1)**, 끝좌표는  **(3, 64, 3)**으로 바꾸세요.

### ~ tutorialhint
``` blocks
function platform() {
    blocks.fill(
    DOUBLE_WOODEN_SLAB,
    pos(1, 64, 1),
    pos(3, 64, 3),
    FillOperation.Replace
    )
}
platform()
```

## 단계 9
자기자신을 텔레포트 해볼게요. 마지막 단계는 자신을 바닥의 가운데 지점으로 이동시키는 것이에요. ``||Player:다음 좌표로 텔레포트||``를 가져와 ``||Functions:teleport||``아래에 넣으세요.


## 단계 10
``||Player:다음 좌표로 텔레포트||``에 좌표값을 **(2, 65, 2)**로 입력하세요.


## 단계 11
게임모드를 서바이벌 모드로 바꾸도록 할게요. ``||Gameplay:게임 모드 변경||``을 가져와 ``||Player:다음 좌표로 텔레포트||``아래에 넣으세요.


### ~ tutorialhint
``` blocks

function teleport() {
    player.teleport(pos(2, 65, 2))
    gameplay.setGameMode(
        SURVIVAL,
        mobs.target(LOCAL_PLAYER)
    )
}
teleport()

```

## 단계 12
실행할 빈공간을 찾아보세요. 기억하세요! 게임은 기본적으로 코드를 시작할 때 ``||Blocks:on start||``로 실행돼요. 신뢰의 도약을 실시하기 전에 플랫폼 위에서는 도약할 장소를 잘 확인하고 뛰어내려야 해요. 이때 Shift키를 누르면서 이동하면 떨어지지 않는다는 것도 알아두세요.



## 단계 13
자! 이제 신뢰도약을 시작해보세요. 만약 게임을 다시 시작하고 싶다면 코드작성기를 다시 열고 시작버튼을 눌러 코드를 실행해보세요.

### ~ tutorialhint
``` blocks

function pool() {
    blocks.fill(
    WATER,
    pos(0, -1, 0),
    pos(2, -3, 2),
    FillOperation.Replace
    )
}
function teleport() {
    player.teleport(pos(2, 65, 2))
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
}
function platform() {
    blocks.fill(
    DOUBLE_WOODEN_SLAB,
    pos(1, 64, 1),
    pos(3, 64, 3),
    FillOperation.Replace
    )
}
pool()
platform()
teleport()
```
