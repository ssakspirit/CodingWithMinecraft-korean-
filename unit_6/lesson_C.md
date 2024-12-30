### @explicitHints 1
# 활동: 햄버거

## 단계 1
함수를 만들어 볼게요. ``||Functions:함수||``카테고리에서 함수만들기를 눌러 새로운 함수를 만드세요. 함수의 이름은 **bottomBun**로 바꾸세요.


## 단계 2
같은 방법으로 함수 네 개를 더 만들어 줄게요. 이름은 각각**meat, lettuce, tomato, topBun**으로 바꾸세요.


## 단계 3
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **burger**로 바꾸세요.


## 단계 4
``||Player:다음 채팅명령어를 입력하면: "burger"||`` 아래에 앞에서 생성한 함수를 호출하여 다음 순서대로 넣어주세요. ``||Functions:호출 bottomBun||``, ``||Functions:호출 meat||``, ``||Functions:호출 lettuce||`` , ``||Functions:호출 tomato||``, ``||Functions:호출 topBun||``

**주의점**: 함수를 호출하는 순서는 중요해요.

### ~ tutorialhint
```blocks
function lettuce()  {

}
function bottomBun()  {

}
function topBun()  {

}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function meat()  {

}
function tomato()  {

}
```

## 단계 5
햄버거의 아래쪽 빵을 만들어볼게요. 
``||Blocks:블록 채우기||``를 가져와 ``||Functions:bottomBun||``아래에 넣으세요. 블록은 드롭다운메뉴에서 **참나무 목재**로 바꾸세요. 


## 단계 6
``||Blocks:블록 채우기||``의 시작좌표는 **(~3, ~0, ~3)** 끝좌표를 **(~8, ~0, ~8)**로 입력하세요.

### ~ tutorialhint
```blocks
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {

}
function tomato() {

}
```

## 단계 7
이제 햄버거 패티를 만들어 볼게요. ``||Blocks:블록 채우기||``를 가져와 ``||Functions:meat||``아래에 넣으세요. 블록은 드롭다운메뉴에서 **갈색 테라코타**로 바꾸세요. 그리고 ``||Blocks:블록 채우기||``의 시작좌표 **(~4, ~1, ~4)** 끝좌표를 **(~7, ~1, ~7)**로 입력하세요.


### ~ tutorialhint
```blocks
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {

}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {
    blocks.fill(
    BROWN_TERRACOTTA,
    pos(4, 1, 4),
    pos(7, 1, 7),
    FillOperation.Replace
    )
}
function tomato() {

}
```
## 단계 8
이제 상추를 만들 차례예요. ``||Blocks:블록 채우기||``를 가져와 ``||Functions:lettuce||``아래에 넣으세요. 블록은 드롭다운메뉴에서 **연두색 콘크리트**로 바꾸세요. 그리고 ``||Blocks:블록 채우기||``의 시작좌표 **(~4, ~2, ~4)** 끝좌표를 **(~7, ~2, ~7)**로 입력하세요.


### ~ tutorialhint
```blocks
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
     blocks.fill(
    LIME_CONCRETE,
    pos(4, 2, 4),
    pos(7, 2, 7),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {
    blocks.fill(
    BROWN_TERRACOTTA,
    pos(4, 1, 4),
    pos(7, 1, 7),
    FillOperation.Replace
    )
}
function tomato() {

}
```

## 단계 9
잘게 잘린 토마토를 넣어볼게요. ``||Blocks:블록 채우기||``를 가져와 ``||Functions:tomato||``아래에 넣으세요. 블록은 드롭다운메뉴에서 **빨간색 콘크리트**로 바꾸세요. 그리고 ``||Blocks:블록 채우기||``의 시작좌표 **(~4, ~3, ~4)** 끝좌표를 **(~7, ~3, ~7)**로 입력하세요.




### ~ tutorialhint
```blocks
function tomato() {
    blocks.fill(
    RED_CONCRETE,
    pos(4, 3, 4),
    pos(7, 3, 7),
    FillOperation.Replace
    )
}
tomato()
```

## 단계 10
가장 위에 있는 햄버거빵을 만들어 볼게요. 진짜 햄버거 모양과 비슷하게 만들려면 이 함수는 두 개의 층으로 만드는 것이 좋아요. ``||Blocks:블록 채우기||``를 두 번 가져와 ``||Functions:topBun||``아래에 넣으세요. 블록은 드롭다운메뉴에서 **참나무 목재**로 둘 다 바꾸세요. 



## 단계 11
첫번째 ``||Blocks:블록 채우기||``의 시작좌표 **(~3, ~4, ~3)** 끝좌표를 **(~8, ~4, ~8)**로 입력하세요.


## 단계 12
두번째 ``||Blocks:블록 채우기||``의 시작좌표 **(~4, ~5, ~4)** 끝좌표를 **(~7, ~5, ~7)**로 입력하세요.


### ~ tutorialhint
``` blocks
function topBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 4, 3),
    pos(8, 4, 8),
    FillOperation.Replace
    )
    blocks.fill(
    PLANKS_OAK,
    pos(4, 5, 4),
    pos(7, 5, 7),
    FillOperation.Replace
    )
}
topBun()
```

## 단계 13
코드를 모두 작성했어요. 이제 햄버거를 만들어 봅시다!


### ~ tutorialhint
```blocks
function meat() {
    blocks.fill(
    BROWN_TERRACOTTA,
    pos(4, 1, 4),
    pos(7, 1, 7),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 4, 3),
    pos(8, 4, 8),
    FillOperation.Replace
    )
    blocks.fill(
    PLANKS_OAK,
    pos(4, 5, 4),
    pos(7, 5, 7),
    FillOperation.Replace
    )
}
function tomato() {
    blocks.fill(
    RED_CONCRETE,
    pos(4, 3, 4),
    pos(7, 3, 7),
    FillOperation.Replace
    )
}
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
    blocks.fill(
    LIME_CONCRETE,
    pos(4, 2, 4),
    pos(7, 2, 7),
    FillOperation.Replace
    )
}
```
