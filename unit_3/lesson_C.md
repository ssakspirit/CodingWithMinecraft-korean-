### @explicitHints 1

# 활동: 자동 사육장

## 단계 1
``||Player:플레이어가 걷고 있으면 실행||``을 가져오세요.
``||Mobs:소환||``을 가져와 ``||Player:플레이어가 걷고 있으면 실행||`` 아래에 넣으세요. ``||Mobs:소환||``의 소환할 동물로 **양**을 선택하세요. 또는 여러분의 농장에서 기르고 싶은 동물을 선택해도 좋아요.


## 단계 3
``||Mobs:소환||``의 좌표값을 **(~0, ~0, ~1)**로 바꾸세요. 양은 플레이어로부터 **-Z**방향으로 한칸 떨어진 곳에서 소환돼요.

### ~ tutorialhint
``` blocks
player.onTravelled(WALK, function () {
    mobs.spawn(SHEEP, pos(0, 0, 1))
})
```

## 단계 4
사육장의 울타리를 만들어 볼게요. ``||Player:다음 채팅명령어를 입력하면||``을 가져와 명령어를 **"pen"**으로 바꾸세요.


## 단계 5
 ``||Blocks:블록 채우기||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "pen"||``아래에 넣으세요.
 ``||Blocks:블록 채우기||``의 블록값을 **네더 벽돌 울타리**로 바꾸세요. 그리고 시작좌표를 **(~5, ~0, ~1)**,  끝좌표를 **(~-5, ~4, ~1**)로 바꾸세요.


### ~ tutorialhint
``` blocks
player.onTravelled(WALK, function () {
    mobs.spawn(SHEEP, pos(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    NETHER_BRICK_FENCE,
    pos(5, 0, 1),
    pos(-5, 4, 1),
    FillOperation.Replace
    )
})
```

## 단계 6
옆쪽 벽을 만들어 볼게요. 남쪽 벽을 만들고 있는 ``||Blocks:블록 채우기||``를 마우스 오른쪽 버튼으로 클릭하고 두 번 복사하세요. 이 복사된 코드는 옆쪽 벽이 될 거에요.


## 단계 7
옆쪽 벽의 재료를 바꿀게요. 한쪽은 **아카시아나무 울타리**, 다른 한쪽은 **자작나무 울타리**로 해볼게요.

## 단계 8
**아카시아나무 울타리**의 좌표를 **(~5, ~0, ~1)** 및 **(~-5, ~4, ~20)**로 바꾸고 **자작나무 울타리**의 좌표는 **(~5, ~0, ~1)** 및 **(~5, ~4, ~20**)로 바꾸세요.

### ~ tutorialhint
``` blocks 
player.onTravelled(WALK, function () {
    mobs.spawn(SHEEP, pos(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    NETHER_BRICK_FENCE,
    pos(5, 0, 1),
    pos(-5, 4, 1),
    FillOperation.Replace
    )
    blocks.fill(
    BIRCH_FENCE,
    pos(-5, 0, 1),
    pos(-5, 4, 20),
    FillOperation.Replace
    )
    blocks.fill(
    ACACIA_FENCE,
    pos(5, 0, 1),
    pos(5, 4, 20),
    FillOperation.Replace
    )
})
```
## 단계 9
북쪽의 울타리를 만들어 사육장을 완성해볼게요. **Z좌표**는 남쪽 울타리에서 정확히 **20** 블록 떨어져 있어야 해요. 왜냐하면 옆 벽의 길이가 그 정도이기 때문이지요. 마인크래프트에서 코드를 실행해 보고 원하는 만큼 사육장을 만들어 보세요!


### ~ tutorialhint
``` blocks
player.onChat("pen", function () {
    blocks.fill(
    NETHER_BRICK_FENCE,
    positions.create(5, 0, -1),
    positions.create(-5, 4, -1),
    FillOperation.Replace
    )
    blocks.fill(
    ACACIA_FENCE,
    positions.create(-5, 0, -1),
    positions.create(-5, 4, 20),
    FillOperation.Replace
    )
    blocks.fill(
    BIRCH_FENCE,
    positions.create(5, 0, -1),
    positions.create(5, 4, 20),
    FillOperation.Replace
    )
    blocks.fill(
    NETHER_BRICK_FENCE,
    positions.create(5, 0, 20),
    positions.create(-5, 4, 20),
    FillOperation.Replace
    )
})
```
