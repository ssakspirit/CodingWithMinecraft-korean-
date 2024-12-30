### @explicitHints 1

# 활동: 좀비피그맨

## 단계 1
함수를 만들어 볼게요. **고급**카테고리-``||Functions:함수||``카테고리에서 함수만들기를 눌러 새로운 함수를 만드세요. 함수의 이름은 **zombiepig**하세요.

## 단계 2
같은 방법으로 함수 두 개를 더 만들어 줄게요. 이름은 각각**atmosphere**, **setup**으로 바꾸세요.


## 단계 3
``||Player:다음 채팅명령어를 입력하면||``을 가져와 채팅명령어를 **play**로 바꾸세요.

## 단계 4
``||Functions:호출 setup||``, ``||Functions:호출 atmosphere||``, ``||Functions:호출 zombiepig||``를 가져와 ``||Player:다음 채팅명령어를 입력하면:"play"||``아래에 순서대로 넣으세요.


### ~ tutorialhint
``` blocks
function zombiepig()  {

}
function atmosphere()  {

}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
function setup()  {

}
```

## 단계 5
좀비피그맨을 만들어 볼게요. ``||Mobs:소환||``을 가져와 ``||Functions:zombie pig||``아래에 넣으세요. ``||Mobs:소환||``의 동물을 **돼지**로 바꾸세요. 그리고 돼지가 플레이어 기준으로 북쪽으로 5칸에 생기도록 할게요. 새로운 ``||Mobs:소환||``을 가져와 넣은 다음 ``||Mobs:마법 발사||``를 가져와 **동물** 대신에 넣으세요. 그리고 마법 발사를 불 붙은 TNT에서 **라이트닝 볼트**로 바꾸세요.


## 단계 6
돼지가 소환되는 좌표를 **(~0, ~0, ~-5)**로 입력하세요. 돼지가 소환되는 위치에 라이트닝 볼트를 발사하여 돼지가 좀비피그맨으로 바뀌도록 할거에요. 따라서 ``||Mobs:마법 발사||``의 좌표도 **(~0, ~0, ~-5)**로 해주세요.


### ~ tutorialhint
``` blocks
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
function setup()  {

}
function atmosphere()  {

}
```

## 단계 7
세부 설정을 마저 해볼게요. 이 게임이 자동으로 작동하는 것이 좋을 것 같아요. 채팅명령어 play를 입력하고 나서 모든 설정이 완료되고 좀비피그맨과 전투를 시작하게 돼요. 첫 번째 문제는 난이도예요. 좀비피그맨은 난이도 평화로움에서는 나타나지 않아요.


## 단계 8
 ``||Gameplay:난이도 설정하기||``를 가져와 ``||Functions:setup||``아래에 넣으세요.
 ``||Gameplay:난이도 설정하기||``의 난이도를 평화로움이 아닌 **쉬움**으로 해주세요.


## 단계 9
다음은 게임모드를 바꿔줘야 해요. 서바이벌 모드에서만 좀비피그맨과 전투를 할 수 있어요. 여러분이 좀비피그맨을 때리면 바로 반격하기 시작할거에요.
``||Gameplay:게임 모드 변경||``을 가져와 ``||Functions:setup||``안에 넣으세요.
``||Gameplay:게임 모드 변경||``의 모드가 서바이벌인지 확인하세요. 대상은 **자기 자신@s**으로 바꾸세요.


## 단계 10
만약 플레이어가 아무런 무기도 없이 전투를 한다면 힘들 것 같아요. 게임을 재밌게 진행하기 위해서는 그에 맞는 무기를 받는 것이 좋겠어요. ``||Mobs:블록이나 아이템 주기||``를 가져와 ``||Functions:setup||``아래에 넣으세요.


## 단계 11
``||Blocks:아이템||``을 가져와 ``||Mobs:블록이나 아이템 주기||``의 잔디블록 대신에 넣고 받을 아이템으로 바꾸세요. 예를 들면 다이아몬드 칼을 받을 수도 있겠지요. 받을 대상은 **자기 자신@s**으로 바꾸세요.


### ~ tutorialhint
``` blocks
function atmosphere()  {

}
function setup() {
    gameplay.setDifficulty(EASY)
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    blocks.item(DIAMOND_SWORD),
    1
    )
}
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

## 단계 12
이제 게임을 테스트할 수 있어요. 채팅명령어 **play**를 입력하면 미니게임이 시작돼요.


## 단계 13
시간을 조정해볼게요. 이 미니게임의 한 가지 팁은 바로 하루의 시간을 조절하여 시각 효과를 추가하는 것이에요. 이렇게 하면 좀비피그맨과 어울리는 배경이 될 것 같아요.
``||Gameplay:시간 설정||``을 가져와 추가해보세요.


## 단계 14
마인크래프트의 하루는 실제 시간으로 20분이에요. 20분은 24,000번의 틱(tic)이에요. 즉 1틱은 1/20초이지요. ``||Gameplay:시간 설정||``을 자정으로 설정하면 현재 게임 내 시각을 자정으로 설정할 수 있어요.  ``||Gameplay:시간 설정||``으로 쉽게 게임 내 시각을 바꿀 수 있어요. 


## 단계 15
``||Gameplay:시간 설정||``을 가져와 ``||Functions:atmosphere||``아래에 넣으세요.
``||Gameplay:시간 설정||``의 시간을 **자정**으로 바꾸세요.


### ~ tutorialhint
``` blocks
function atmosphere() {
    gameplay.timeSet(gameplay.time(MIDNIGHT))
}
function setup() {
    gameplay.setDifficulty(EASY)
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    blocks.item(DIAMOND_SWORD),
    1
    )
}
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

## 단계 16
혹시 시간이 바뀌지 않나요? 그렇다면 게임 설정에서 **항상 낮** 옵션이 켜져있는지 확인해보세요.
추가로 좀비피그맨을 소환하는 것도 좋아요. 좀비피그맨을 없애면 다른 좀비피그맨이 소환되도록 해볼게요. 
``||Mobs:몹이 죽었다면 실행||``을 가져와 ``||Functions:Pigman||``에 넣으면 될 것 같아요. 


## 단계 17
``||Mobs:몹이 죽었다면 실행||``을 가져오세요.
``||Mobs:몬스터||``를 가져와 ``||Mobs:몹이 죽었다면 실행||``의 몹에 넣으세요. 그리고 몹의 종류를 **좀비 피그맨**으로 바꾸세요.


## 단계 18
``||Functions:호출 zombiepig||``을 가져와 ``||Mobs:몹이 죽었다면 실행||``에 넣으세요.

### ~ tutorialhint
``` blocks
function setup() {
    gameplay.setDifficulty(EASY)
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    blocks.item(DIAMOND_SWORD),
    1
    )
}
mobs.onMobKilled(mobs.monster(PIG_ZOMBIE), function () {
    zombiepig()
})
function atmosphere() {
    gameplay.timeSet(gameplay.time(MIDNIGHT))
}
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

