### @explicitHints 1

# 활동: 순간 이동

## 단계 1
``||Loops:시작하면 실행||``을 가져오세요. 

## 단계 2
 이름이 **warp_array**인 새로운 변수를 만들어주세요. 
``||Variables:변숫값 저장||``을 가져와 ``||Loops:시작하면 실행||``아래에 넣으세요.
``||Variables:변숫값 저장||``의 변수가 **warp_array**인지 확인하세요.



## 단계 3
``||Arrays:빈배열||``을 가져와 ``||Variables:"warp_array"에 저장||``의 변숫값에 넣으세요.


### ~ tutorialhint
``` blocks
let warp_array: number[] = []
warp_array = []
```

## 단계 4
"delete" 명령을 만들어볼게요. 
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **delete**로 바꾸세요.


## 단계 5
``||Loops:시작하면 실행||``안에 ``||Variables: "warp_array"에 빈배열 저장||``을 복사해서 ``||Player:다음 채팅명령어를 입력하면: "delete"||``아래에 넣으세요.


## 단계 6
``||Player:채팅창에 말하기||``를 가져와 방금 복사한``||Variables: "warp_array"에 빈배열 저장||``아래에 넣으세요
메시지는 **"Array deleted"**와 같이 입력하세요.

### ~ tutorialhint
``` blocks
let warp_array: number[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
warp_array = []
```
## 단계 7
"save" 명령을 만들어볼게요. 
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **save**로 바꾸세요.


## 단계 8
 ``||Arrays:list 마지막 위치에 추가||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "save"||``아래에 넣으세요.
``||Variables:변수 warp_array||``에 들어갈 좌표를 저장하려고 해요. ``||Arrays:list 마지막 위치에 추가||``의 첫 번째 칸에 드롭다운메뉴를 눌러 **warp_array**로 바꾸세요.
그리고 ``||Player:플레이어 월드좌표||``를 가져와 ``||Arrays:list 마지막 위치에 추가||``의 두 번째 빈칸에 넣으세요.


### ~ tutorialhint
``` blocks
let warp_array: Position[] = []
warp_array.push(player.position())
```

## 단계 9
``||Player:채팅창에 말하기||``를 가져와 ``||Arrays:warp_array 마지막 위치에 플레이어 절대좌표 추가||``아래에 넣으세요.
메시지는 **"position added"**와 같이 입력하세요.


### ~ tutorialhint
``` blocks
let warp_array: Position[] = [] 
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function () {
    warp_array.push(player.position())
    player.say("position added")
})
warp_array = []
```

## 단계 10
"warp" 명령을 만들어볼게요. 플레이어가 순간 이동할 장소를 번호로 입력하도록 할거에요. 예를 들어 "warp 1" 또는 "warp 2"로 입력하는 것이죠. 이 장소 번호는 배열에 저장된 위치좌표를 의미하는 것이에요.
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **warp**로 바꾸세요.


## 단계 11
``||Player:다음 채팅명령어를 입력하면: "warp"||``의 **(+)**을 눌러 변수를 추가하세요. 기본값은 **num1**이고 이것은 숫자 변숫값이에요. 이 번호가 플레이어가 순간 이동할 위치의 번호가 되는 것이에요. 배열에서 값이 저장되는 위치를 색인 또는 키라고 합니다. 채팅명령어 **warp**와 함께 입력하는 변수 **num1** 값을 통해 인덱스를 전달해요. 그러면 배열에 저장된 위치 정보를 가져올 수 있죠.


## 단계 12
세 번째 저장된 위치로 워프하려면 채팅창에 **warp 3**을 입력하세요. 배열의 세 번째 위치로 이동하여 좌표를 가져와요.
변수 **num1**은 좀더 의미있는 이름으로 바꾸는 것이 좋을 것 같아요. ``||Player:다음 채팅명령어를 입력하면: "warp"||``에 있는 변수 **num1**를 눌러 드롭다운메뉴를 열고 **변수 이름 바꾸기**를 눌러 **Warp_LocationNum**로 이름을 바꾸세요.



## 단계 13
``||Player:다음 좌표로 텔레포트||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "warp"||``아래에 넣으세요.

## 단계 14
이제 배열에 저장된 정보를 가져와 텔레포트할 좌표로 보내기만 하면 돼요. ``||Arrays:리스트에서 0번째 위치의 값||``을 가져와 ``||Player:다음 좌표로 텔레포트||``의 좌표에 넣으세요.


### ~ tutorialhint
``` blocks
let warp_array: Position[] = []
player.teleport(warp_array[0])
```

## 단계 15
``||Arrays:리스트에서 0번째 위치의 값||``의 **리스트**드롭다운메뉴를 열어 변수 **warp_array**로 바꾸세요.
``||Variables:변수 Warp_LocationNum||``를 가져와 ``||Arrays:warp_array에서 0번째 위치의 값||``의 **0** 대신에 넣으세요.


### ~ tutorialhint
``` blocks
let warp_array: Position[] = []
player.onChat("warp", function (Warp_LocationNum) {
    player.teleport(warp_array[Warp_LocationNum])
})
```
## 단계 16
이제 채팅명령어와 함께 숫자값을 입력하면 배열된 저장된 위치를 파악해요. 그런 다음 배열에 저장된 위치로 순간 이동해요.

### ~ tutorialhint
``` blocks
let warp_array: Position[] = []
player.onChat("delete", function () {
    warp_array = []
    player.say("Array deleted")
})
player.onChat("save", function () {
    warp_array.push(player.position())
    player.say("position added")
})
player.onChat("warp", function (Warp_LocationNum) {
    player.teleport(warp_array[Warp_LocationNum - 1])
})
warp_array = []
```
