### @explicitHints 1

# 활동: 나침반 만들기

## 단계 1
새로운 채팅명령어를 만들어 주세요. ``||Player:다음 채팅명령어를 입력하면||`` 을 가져와 채팅명령어를 **"compassrose"**로 바꾸세요.

### ~ tutorialhint
``` blocks
player.onChat("compassrose", function () {
})

```

## 단계 2 
다음, ``||Blocks:블록 채우기||``를 가져와 ``||Player:다음 채팅명령어를 입력하면||``아래에 넣으세요. 
나침반의 축이 되는 ``||Blocks:블록 채우기||``의 블록값을 **잔디블록**에서 여러분이 원하는 블록으로 바꾸세요. 이 예제에서는 **회색 양털**로 바꿀게요.

## 단계 3
``||Blocks:블록 채우기||`` **시작좌표**에는 **(~-10 ~-1 ~0)**, **끝좌표**에는 **(~10 ~-1 ~0)**을 입력하세요.
이렇게 X축으로 21칸의 선모양을 만들어요. 이 축은 플레이어의 한칸 아래 생기고 축의 한 가운데에 플레이어가 위치하게 돼요. 

### ~ tutorialhint
``` blocks
    player.onChat("compassrose", function () {
        blocks.fill(
        GRAY_WOOL,
        pos(-10, -1, 0),
        pos(10, -1, 0),
        FillOperation.Replace
        )
})
```
## 단계 4
동쪽과 서쪽 방향을 표시할게요. ``||Blocks:글자쓰기||``는 동서남북 네 가지 방향에 따라 원하는 블록으로 글자를 써주는 명령블록이에요.

## 단계 5
``||Blocks:글자쓰기||``를 가져와 ``||Blocks:블록 채우기||`` 아래에 넣고 **W**를 입력하세요. 그리고 방향은 **서쪽(-X)**으로 하세요. 같은 방법으로 ``||Blocks:글자쓰기||``를 한번 더 가져와 이번에는 **E**를 입력하고 방향은 **동쪽(+X)**으로 하세요.


## 단계 6
``||Blocks:글자쓰기||``의 블록값을 정해주세요. 이 예제에서는 **서쪽(-X)**은 **연두색 양털**, **동쪽(+X)**은 **노란색 양털**로 할게요.


## 단계 7
``||Blocks:글자쓰기||``의 좌푯값을 정해줄게요. **서쪽(-X)**은 **(~-11 ~0 ~0)**, **동쪽(+X)**은 **(~11 ~0 ~0)**로 바꾸세요.


### ~ tutorialhint
``` blocks
    player.onChat("compassrose", function () {
        blocks.fill(
        GRAY_WOOL,
        pos(-10, 0, 0),
        pos(10, 0, 0),
        FillOperation.Replace
        )
        blocks.print(
        "W",
        LIME_WOOL,
        pos(-11, 0, 0),
        WEST
        )
        blocks.print(
        "E",
        YELLOW_WOOL,
        pos(11, 0, 0),
        WEST
        )
})
```

## 단계 8
똑같은 방법으로 북쪽과 남쪽을 만들어 볼게요. ``||Blocks: 블록 채우기||``를 가져와 작성중인 코드 아래에 이어서 넣으세요.
나침반의 북쪽, 남쪽 축이 되는 ``||Blocks:블록 채우기||``의 블록값을 **잔디블록**에서 여러분이 원하는 블록으로 바꾸세요. 이 예제에서는 **검은색 양털**로 바꿀게요.


## 단계 9
``||Blocks:블록 채우기||`` **시작좌표**에는 **(~0 ~-1 ~-10)**, **끝좌표**에는 **(~0 ~-1 ~10)**을 입력하세요.
이렇게 Z축 방향으로 선모양을 만들어요.


## 단계 10
``||Blocks:글자쓰기||``를 두 번 가져와 ``||Blocks:블록 채우기||`` 아래에 이어서 넣으세요.

## 단계 11
북쪽과 남쪽 방향을 표시하는 첫 번째 ``||Blocks:글자쓰기||``에는 **"N"** , 두 번째에는 **"S"** 를 입력하세요.

## 단계 12
``||Blocks:글자쓰기||``의 블록값을 정해주세요. 이 예제에서는 **북쪽(-Z)**은 **파란색 양털**, **남쪽(+Z)**은 **빨간색 양털**로 할게요.

## 단계 13
``||Blocks:글자쓰기||``의 좌푯값을 정해줄게요. **북쪽(-Z)**은 **(~0 ~0 ~-11)**, **남쪽(+Z)**은 **(~0 ~0 ~11)**로 바꾸세요.

### ~ tutorialhint
    ``` blocks
        player.onChat("compassrose", function () {
            blocks.fill(
            GRAY_WOOL,
            pos(-10, -1, 0),
            pos(10, -1, 0),
            FillOperation.Replace
            )
            blocks.print(
            "W",
            LIME_WOOL,
            pos(-11, 0, 0),
            WEST
            )
            blocks.print(
            "E",
            YELLOW_WOOL,
            pos(11, 0, 0),
            WEST
            )
            blocks.fill(
            GRAY_WOOL,
            pos(0, -1, -10),
            pos(0, -1, 10),
            FillOperation.Replace
            )
            blocks.print(
            "N",
            BLUE_WOOL,
            pos(0, 0, -11),
            WEST
            )
            blocks.print(
            "S",
            RED_WOOL,
            pos(0, 0, 11),
            WEST
            )
})
```
