### @explicitHints 1
# 활동: 글자 쓰기

## 단계 1
``||Loops:시작하면 실행||``을 가져오세요.
``||Variables:변수||``에서 새로운 변수 **word1**, **word2**를 만드세요. 그리고 ``||Variables:변숫값 저장||``을 가져와 ``||Loops:시작하면 실행||``안에 넣으세요.


## 단계 2
**고급** 카테고리를 눌러 ``||Text:문자열||``카테고리에 있는 ``||Text:"  "||``을 가져와 ``||Variables:변숫값 저장||``의 **0** 대신 넣으세요.


## 단계 3
``||Variables:변숫값 저장||``의 드롭다운 메뉴를 눌러 변수 이름을 **word1**로 바꾸세요.
``||Variables:word1에 "  "저장||``을 마우스 오른쪽 클릭하여 복사하세요. 그리고 ``||Loops:시작하면 실행||``아래에 넣으세요.


## 단계 4
두번째 ``||Variables:word1에 "  "저장||``의 드롭다운 메뉴를 눌러 **word1**을 **word2**로 바꾸세요.


### ~ tutorialhint
``` blocks
let word2 = ""
let word1 = ""
word1 = ""
word2 = ""
```

## 단계 5
재밌는 글자 두 가지를 써볼게요. 비어있는 변수값 **word1**과 **word2**에 **" "**대신에 원하는 글자를 써보세요.
이 예제에서는 ``||Variables:변수 word1||``에는 **rail**,  ``||Variables:변수 word2||``에는 **road** 값을 넣었어요.


### ~ tutorialhint
``` blocks
let word2 = ""
let word1 = ""
word1 = "rail"
word2 = "road"
```

## 단계 6
word1을 출력해볼게요. ``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **mix**로 약속하세요.
``||Blocks:글자 쓰기||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "mix"||``안에 넣으세요.


## 단계 7
``||Variables:변수 word1||``을 ``||Blocks:글자 쓰기||``의 글자 **HELLO** 대신에 넣으세요.
사용 블록은 잔디블록에서 **레드스톤 광석**으로 바꾸세요.



### ~ tutorialhint
``` blocks
let word2 = ""
let word1 = ""
player.onChat("mix", function () {
    blocks.print(
    word1,
    REDSTONE_ORE,
    pos(0, 0, 0),
    WEST
    )
})
word1 = "rail"
word2 = "road"
```

##  단계 8
이제 word2를 해볼게요. ``||Blocks:글자 쓰기||``를 복사하여 바로 아래에 넣으세요.
이 복사한 코드가 **word2**를 출력할 수 있도록 ``||Variables:변수 word1||``에서 ``||Variables:변수 word2||``로 바꾸세요.
그리고 사용 블록은 잔디블록에서 **레드스톤 램프**로 바꾸세요.


## 단계 9
약간의 추가 설정과 테스트가 필요해요. 두 개의 글자가 충분한 공간을 두고 출력이 되어야해요. 또한 이 글자가 **남북쪽 축**을 따라서 남쪽으로 써져야 하기 때문에 ``||Blocks:글자 쓰기||``의 방향을 **남쪽(+Z)**로 바꾸세요. 두 번째 ``||Blocks:글자 쓰기||``에서도 똑같이 바꿔주세요.

### ~ tutorialhint
```blocks
let word2 = ""
let word1 = ""
player.onChat("mix", function () {
    blocks.print(
    word1,
    REDSTONE_ORE,
    pos(0, 0, 0),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    pos(0, 0, 0),    
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```

## 단계 10
이제 두 개의 글자가 잘 출력될 수 있을 거에요. 하지만 약간의 문제가 있어요. 이 글자가 만들어지는 좌표를 아직 정해주지 않았어요.


## 단계 11
이것을 고치기 위해서 플레이어의 월드좌표를 저장하도록 해요. ``||Variables:변수||``카테고리에서 **변수 만들기**를 눌러 새로운 변수를 만들고 이름을 **Starting_World_Position**로 약속하세요.

``||Variables:변숫값 저장||``을 가져와 ``||Player:다음 채팅명령어를 입력하면: mix||``의 가장 위에 넣으세요.
 그리고 드롭다운 메뉴를 눌러 변숫값을 **Starting_World_Position**로 바꾸세요.


## 단계 12
``||Player:플레이어 절대좌표||``를 가져와 ``||Variables:set Starting_World_Position에 0 저장||``의 **0**대신 넣으세요.


### ~ tutorialhint
``` blocks
let word2 = ""
let Starting_World_Position: Position = null
let word1 = ""
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    REDSTONE_ORE,
    pos(0, 30, 0),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    pos(0, 20, 0),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```

## 단계 13
이제 블록이 출력되는 위치를 고쳐볼게요. ``||Positions:좌표 더하기||``를 두 번 가져와 ``||Blocks:글자 쓰기||``의 위치에 각각 넣으세요. ``||Variables:변수 Starting_World_Position||``를 두 번 가져와 ``||Positions:좌표 더하기||``의 처음 값에 각각 넣으세요. 그리고 **word1**가 출력되는 Y좌표를 **30**, **word1**가 출력되는 Y좌표는 **20**을 더해주도록 해요.


### ~ tutorialhint
``` blocks
let word2 = ""
let Starting_World_Position: Position = null
let word1 = ""
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    REDSTONE_ORE,
    positions.add(
    Starting_World_Position,
    pos(0, 30, 0)
    ),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    positions.add(
    Starting_World_Position,
    pos(0, 20, 0)
    ),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```

## 단계 14
이제 두 글자를 함께 출력하도록 해볼게요. 위에서 사용한 ``||Blocks:글자 쓰기||`` 중 하나를 복사해서 가져와 작성중인 코드 아래 이어 넣으세요. 
사용 블록은 **레드스톤 블록**으로 바꾸세요.



## 단계 15
새로운 ``||Blocks:글자 쓰기||``의 위치에서 더 하는 **Y**좌표값은 **5**로 바꾸세요.


## 단계 16
``||Text:연결한 문자열||``을 가져와  ``||Blocks:글자 쓰기||``의 출력될 글자에 넣으세요. 그리고 ``||Variables:변수 word1||``과 ``||Variables:변수 word2||``를 가져와 순서대로 ``||Text:연결한 문자열||``의 각 칸에 넣으세요.


### ~ tutorialhint
``` blocks
let word2 = ""
let word1 = ""
let Starting_World_Position: Position = null
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    REDSTONE_ORE,
    positions.add(
    Starting_World_Position,
    pos(0, 30, 0)
    ),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    positions.add(
    Starting_World_Position,
    pos(0, 20, 0)
    ),
    SOUTH
    )
    blocks.print(
    word1 + word2,
    REDSTONE_BLOCK,
    positions.add(
    Starting_World_Position,
    pos(0, 5, 0)
    ),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```
