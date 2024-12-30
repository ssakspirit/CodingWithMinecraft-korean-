### @explicitHints 1
# 활동: 치킨 스톰

## 단계 1
``||Player:다음 채팅명령어를 입력하면||``의 채팅명령어를 **"chickens"**로 바꾸세요.

## 단계 2
``||Loops:반복(repeat)||``을 가져와 ``||Player:다음 채팅명령어를 입력하면:"chickens"||``아래에 넣으세요.


## 단계 3
``||Mobs:소환||``을 가져와 ``||Loops:반복(repeat)||``안에 넣으세요.


## 단계 4
``||Mobs:소환||``의 **Y**좌푯값을 **10**으로 바꾸세요. 닭은 플레이어 10칸 위에서 소환이 될거에요.

### ~ tutorialhint
``` blocks
player.onChat("chickens", function () {
    for (let index = 0; index < 4; index++) {
        mobs.spawn(CHICKEN, pos(0, 10, 0))
    }
})
```

## 단계 5
마인크래프트에 돌어가서 **T**를 눌러 채팅창을 열고 채팅창에 **chickens**를 입력하세요. 닭들이 비처럼 내려오지요?


## 단계 6
``||Player:다음 채팅명령어를 입력하면:"chickens"||``옆에 **+**눌러 변수 **num1**를 추가하세요.
``||Variables:변수||``에서 ``||Variables:변수 num1||``을 가져와 ``||Loops:반복(repeat)||``의 반복 횟수에  **4**대신 넣으세요.
이제 채팅창에 **chickens 15**를 입력하면 **num1** 변수는 **15**가 되고 닭이 15마리 소환될거에요.

### ~ tutorialhint
``` blocks
player.onChat("chickens", function (num1) {
    for (let i = 0; i < num1; i++) {
        mobs.spawn(CHICKEN, pos(0, 10, 0))
    }
})
```
