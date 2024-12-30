### @explicitHints 1

# 활동: 동물원 만들기

## 단계 1
``||Loops:시작하면 실행||`` 을 가져오세요. 이름이 **animalarray**인 새로운 변수를 만들어 주세요. 
동물이 들어갈 배열을 만들어 볼게요. ``||Variables:변숫값 저장||``을 가져와 ``||Loops:시작하면 실행||``아래에 넣으세요.
``||Variables:변숫값 저장||``의 변수가 **animalarray**인지 확인하세요.

## 단계 2
``||Arrays:빈배열||``을 가져와 ``||Variables:"animalarray"에 저장||``의 변숫값에 넣으세요.


## 단계 3
배열에 동물을 추가할게요. ``||Arrays:빈배열||``의 **(+)**을 눌러 8개 빈칸을 만들어 주세요. 배열의 길이가 **8**이에요.


## 단계 4
``||Mobs:동물||``을 가져와 배열에 넣으세요. ``||Mobs:동물||``을 복사하거나 다시 가져와서 모든 배열의 빈칸에 넣으세요.


## 단계 5
``||Mobs:동물||``을 눌러 동물을 골라보세요. 8종류의 동물이 나오는 동물원을 만들거에요. 하지만 어떤 동물은 다른 동물을 잡아먹기도 하니 주의해야해요. 예를 들면, 오셀롯과 닭은 잘 어울리지 않아요. 당신이 원하는 계획에 따라 동물원을 꾸며보는 것이죠. ``||Mobs:동물||``의 드롭다운 메뉴를 눌러 동물을 선택하세요.



## 단계 6
이제 동물 울타리를 만들어 볼게요.  이제 동물 배열을 설정했으므로 동물원의 울타리를 만드는 작업이 필요해요. ``||Builder:빌더||``카테고리에 있는 명령블록을 활용해볼게요. **빌더**는 보이지 않는 커서처럼 매우 빠르게 경로를 따라 블록을 배치할 수 있어요. 남동쪽 모서리 점으로 이동하도록 지시하고 보이지 않는 참조점인 **위치마크**를 작성해요. 그런 다음 사각형을 추적하도록 일련의 명령을 내려요. 그러면 빌더가 이 길을 따라 울타리를 만들 수 있을거에요.



## 단계 7
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **pen**으로 바꾸세요.
``||Builder:빌더 텔레포트||``를 ``||Player:다음 채팅명령어를 입력하면: "pen"||``아래에 넣으세요.


## 단계 8
울타리를 놓을 자리를 찾으세요. 플레이어의 위치 기준으로 빌더가 울타리 북동쪽 모서리에서 시작하도록 할게요. 빌더가 이동할 좌표를 동쪽으로 **5** 블록, 북쪽으로 **5** 블록을 지정해요. 
``||Builder:빌더 텔레포트||``의 좌표를 **(~5, ~0, ~-5)**로 바꾸세요. 


## 단계 9
빌더가 올바른 방향을 향하고 있는지 확인하여 플레이어 주변의 울타리를 그려요. 빌더가 올바른 방향을 향해야 위치마커를 지정할 수 있어요.
``||Builder:빌더가 바라보기||``를 가져와 ``||Builder:빌더 텔레포트||`` 아래에 넣으세요.


## 단계 10
``||Builder:빌더 위치마크 생성||``을 가져와 ``||Builder:빌더가 바라보기||`` 아래에 넣으세요.
울타리의 바깥 선을 그리는 거에요. 우리는 간단히 빌더가 사각형 모양을 그리도록 할게요.


## 단계 11
``||Loops:반복(repeat)||``을 가져와 ``||Builder:빌더 위치마크 생성||``아래에 넣으세요. 사각형은 **4개**의 변을 가지고 있기 때문에 **4번** 반복하도록 해요.


## 단계 12
``||Builder:빌더 이동 방향||``을 가져와 ``||Loops:반복(repeat)||``아래에 넣으세요.
빌더 이동 거리를 **10**으로 바꾸어 울타리의 길이가 **10칸**이 되도록 해요.



## 단계 13
 ``||Builder:빌더 돌기||``를 가져와 ``||Builder:빌더 이동 방향||``아래에 넣으세요.


## 단계 14
마지막 단계는 빌더가 사각형 길을 따라 울타리를 놓는 거에요.
``||Builder:빌더 위치마크부터 이동한 경로에 블록 놓기||``를 가져와 ``||Loops:반복(repeat)||`` 밖에 넣으세요. 블록은 **참나무 울타리**를 선택하세요.


### ~ tutorialhint
``` blocks
player.onChat("pen", function () {
    builder.teleportTo(pos(5, 0, -5))
    builder.face(WEST)
    builder.mark()
    for (let index = 0; index < 4; index++) {
        builder.move(FORWARD, 10)
        builder.turn(LEFT_TURN)
    }
    builder.tracePath(OAK_FENCE)
})

```

## 단계 15
이제 동물들을 초대할까요? 재미있는 부분이에요. 배열은 동물들로 가득 차 있고, 울타리는 이미 만들어졌죠. 이제 동물을 풀어줄 시간이에요!


## 단계 16
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **zoo**으로 바꾸세요.
``||Loops:반복(foreach)||``를 가져와 ``||Player:다음 채팅명령어를 입력하면: "zoo"||``아래에 넣으세요.


## 단계 17
``||Loops:반복(foreach)||``의 두 번째  칸 **list**을 눌러 **animalarray**를 선택하세요.


## 단계 18
``||Mobs:소환||``을 가져와 ``||Loops:반복(foreach)||``안에 넣으세요.


## 단계 19
``||Variables:변수 animalarray ||``를 가져와 ``||Mobs:소환||``의 동물에 대신에 넣으세요.
동물이 소환되는 좌표는  **(~3, ~0, ~0)**로 바꾸어 플레이어 앞에서 보이도록 해요.


## 단계 20
동물들이 혼자 나오지 말고 짝을 이루어 나오면 좋을 것 같아요. 방금 작성한 ``||Mobs:소환||``을 복사해서 아래에 추가하세요. 아니면 반복문을 넣어서 더 많이 만들어도 좋아요.


### ~ tutorialhint
``` blocks
player.onChat("zoo", function () {
    let animalarray: number[] = []
    for (let value of animalarray) {
        mobs.spawn(value, pos(3, 0, 0))
        mobs.spawn(value, pos(3, 0, 0))
    }
})
```

## 단계 21
마인크래프트로 돌아가서 채팅창에 "zoo" 명령을 입력하고 동물들이 나타나는 것을 보세요!


### ~ tutorialhint
``` blocks
let animalarray: number[] = []
player.onChat("pen", function () {
    builder.teleportTo(pos(5, 0, -5))
    builder.face(WEST)
    builder.mark()
    for (let i = 0; i < 4; i++) {
        builder.move(FORWARD, 10)
        builder.turn(TurnDirection.Left)
    }
    builder.tracePath(OAK_FENCE)
})
player.onChat("zoo", function () {
    for (let value of animalarray) {
        mobs.spawn(value, pos(3, 0, 0))
        mobs.spawn(value, pos(3, 0, 0))
    }
})
animalarray = [PIG, RABBIT, OCELOT,HORSE, DONKEY, MULE, LLAMA, POLAR_BEAR]
```
