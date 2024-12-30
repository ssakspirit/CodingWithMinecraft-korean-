### @explicitHints 1

# 활동: 나이 맞추기

## 단계 1
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **age**로 바꾸세요.
``||Player:다음 채팅명령어를 입력하면:"age"||``의 **(+)**버튼을 눌러 **num1**변수를 추가하세요.
**num1**을 눌러 드롭다운 메뉴를 열고 변수이름 바꾸기를 누르세요. 변수 이름 **num1**을 **FriendsAge**로 바꾸세요. 
이렇게 하면 코드를 더 쉽게 읽을 수 있어요. 변수를 만들 때는 항상 의미있는 이름을 사용하는 것이 좋아요.


### ~ tutorialhint
``` blocks
player.onChat("age", function(FriendsAge) {

})
```

## 단계 2
조건문을 작성해볼게요. ``||Logic:만약이면실행(if then else)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면:"age"||``아래에 넣으세요.
그리고 조건문의 **(+)**을 눌러 한 가지 경우를 더 만들어 모두 세 가지 경우가 될 수 있도록 하세요.


## 단계 3
조건식을 만들어 볼게요. ``||Logic:0 < 0||``을 가져와 ``||Logic:만약이면 실행(if then)||``의 조건식 **true**대신에 넣으세요.


## 단계 4
``||Logic:0 = 0||``을 가져와 ``||Logic:아니면서 만약(else if)||``의 조건식에 넣으세요.


### ~ tutorialhint
``` blocks
player.onChat("age", function (FriendsAge) {
    if (0 < 0) {
    } else if (0 == 0) {
    } else {
    }
})
```

## 단계 5
변수를 비교해볼게요. ``||Variables:변수 FriendsAge||``를 두 번 가져와 단계4에서 작성한 조건식의 첫 번재 칸에 각각 넣으세요.
그리고 각 조건식의 두 번째 칸에는 여러분의 나이를 넣으세요. 이 예제에서는 **12**로 할게요.



### ~ tutorialhint
``` blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {

    } else if (FriendsAge == 12) {

    } else {

    }
})
```

## 단계 6
각 경우에 글자를 출력하도록 할게요. ``||Blocks:글자 쓰기||``를 세 번 가져와 각 조건식 아래에 넣으세요. 또는 복사를 해도 좋아요.

### ~ tutorialhint
``` blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {
        blocks.print(
        "HELLO",
        GRASS,
        pos(0, 0, 0),
        WEST
        )
    } else if (FriendsAge == 12) {
        blocks.print(
        "HELLO",
        GRASS,
        pos(0, 0, 0),
        WEST
        )
    } else {
        blocks.print(
        "HELLO",
        GRASS,
        pos(0, 0, 0),
        WEST
        )
    }
})
```

## 단계 7
각 경우에 맞는 다른 메시지를 출력하도록 할게요. 여러분보다 나이가 어린 경우, 같은 경우, 많은 경우 세 가지예요.
``||Blocks:글자 쓰기||``의 출력되는 메시지를 넣는 칸에 여러분들이 원하는 메시지를 써주세요.


## 단계 8
각 경우의 ``||Blocks:글자 쓰기||``에서 사용 블록을 정해주세요.
모든 ``||Blocks:글자 쓰기||``의 위치는 **Y**좌표값 10으로 바꿔주세요. 플레이어 위로 10칸에 글자가 써지게 돼요. 



### ~ tutorialhint
``` blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {
        blocks.print(
        "Baby",
        SMOOTH_SANDSTONE,
        pos(0, 10, 0),
        WEST
        )
    } else if (FriendsAge == 12) {
        blocks.print(
        "Coincidence?",
        ORANGE_TERRACOTTA,
        pos(0, 10, 0),
        WEST
        )
    } else {
        blocks.print(
        "Grandpa",
        STONECUTTER,
        pos(0, 10, 0),
        WEST
        )
    }
})
```

## 단계 9
이제 게임을 즐길 차례예요! 이 활동을 하려면 짝을 만들어 해보세요. 마인크래프트 게임에서 't'를 입력하여 채팅창을 열고 짝에게 자신의 나이를 맞춰보라고 물어보세요.
그리고 짝의 대답을 'age 대답'으로 입력하세요. 여기서 대답은 짝이 생각한 나의 나이예요. 이제 마인크래프트에서 만들어진 메시지를 친구에게 보여주세요!



