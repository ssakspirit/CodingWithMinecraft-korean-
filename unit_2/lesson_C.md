### @explicitHints 1

# 유리벽

## 단계 1
이 활동을 위해 미리 준비된 시작코드가 있어요. 여기에 추가해서 새로운 채팅명령어를 만들어 볼게요. ``||Player:플레이어||``카테고리에 ``||Player:다음 채팅명령어를 입력하면||``을 가져오세요. 그리고 채팅명령어 **"jump"**를 **"wall"**로 바꾸세요.

```template
let PlayerPosition: Position = null
let from_position: Position = null
let to_position: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    pos(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    pos(-6, 13, 0)
    )
})
```

## 단계 2
벽을 만들어 볼게요. ``||Blocks:블록||``카테고리에서   ``||Blocks:블록 채우기||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: wall||`` 아래에 넣으세요.


## 단계 3
벽을 만드는 블록을 바꾸어 줄게요. ``||Blocks:블록 채우기||``의 **잔디블록**을 **유리**로 바꾸세요.


## 단계 4
``||Variables:변수||``카테고리에서 변숫값 ``||Variables:from_position||``을 가져와 ``||Blocks:블록 채우기||``의 **시작좌표**에 넣으세요.


## 단계 5
같은 방법으로 ``||Variables:변수||``카테고리에서 변숫값 ``||Variables:to_position||``을 가져와 ``||Blocks:블록 채우기||``의 **끝좌표**에 넣으세요. 그리고 마인크래프트로 돌아가 실행해보세요.


### ~ tutorialhint
 ```blocks
        player.onChat("wall", function () {
                blocks.fill(
                GLASS,
                from_position,
                to_position,
                FillOperation.Replace
                )
})
```

## 단계 6
유리블록이 깨지면 실행되는 코드를 작성해볼게요. ``||Blocks:블록||``카테고리에서   ``||Blocks:블록이 깨지면 실행||``을 가져오세요.


## 단계 7
 ``||Blocks:블록이 깨지면 실행||``의 블록값 **잔디블록**을 **유리**로 바꾸세요.

## 단계 8
``||Blocks:블록||``카테고리에서   ``||Blocks:블록 놓기||``를 가져와 ``||Blocks:블록이 깨지면 실행||``아래에 넣으세요.

## 단계 9
``||Blocks:블록 놓기||``의 블록값 **잔디블록**을 **다이아몬드 블록**으로 바꾸세요.


### ~ tutorialhint
```blocks
blocks.onBlockBroken(GLASS, function () {
    blocks.place(DIAMOND_BLOCK, pos(0, 0, 0))
})
```
## 단계 10
블록이 놓이는 위치를 수정해볼게요. ``||Positions:위치||``카테고리에 ``||Positions:랜덤 위치 선택||``을 가져와 ``||Blocks:블록 놓기||``의 **좌표값(~0 ~0 ~0)**에 넣으세요.


## 단계 11
``||Variables:변수||``카테고리에서 변숫값 ``||Variables:from_position||``을 가져와 ``||Positions:랜덤 위치 선택||``의 **시작좌표**에 넣고 변숫값 ``||Variables:to_position||``은 **끝좌표**에 넣으세요.

### ~ tutorialhint
```blocks
blocks.onBlockBroken(GLASS, function () {
    blocks.place(DIAMOND_BLOCK, randpos(
    from_position,
    to_position
    ))
})
```

## 단계 12
``||Blocks:유리 블록이 깨지면 실행||``을 복사한 뒤 **유리**를 **다이아몬드 블록**으로 바꾸세요.

## 단계 13
그리고 ``||Blocks:다이아몬드 블록 놓기||``를 ``||Blocks:주황색 양털 놓기||``로 바꾸세요. 그리고 마인크래프트로 돌아가 코드를 실행하세요.

### ~ tutorialhint

```blocks

let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
blocks.onBlockBroken(GLASS, function () {
    blocks.place(DIAMOND_BLOCK, randpos(
    from_position,
    to_position
    ))
})
blocks.onBlockBroken(DIAMOND_BLOCK, function () {
    blocks.place(ORANGE_WOOL, randpos(
    from_position,
    to_position
    ))
})
player.onChat("wall", function () {
    blocks.fill(
    GLASS,
    from_position,
    to_position,
    FillOperation.Replace
    )
})
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    pos(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    pos(-6, 13, 0)
    )
})
```
