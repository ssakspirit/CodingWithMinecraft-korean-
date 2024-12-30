### @explicitHints 1

# 노래하는 앵무새

## 단계 1
블록이 깨지면 코드가 실행되도록 할게요. ``||Blocks: 블록||``카테고리에 ``|| Blocks: 블록이 깨지면 실행||``을 가져오세요.


### ~ tutorialhint
```blocks
blocks.onBlockBroken(GRASS, function () {
	
})
```

## 단계 2
``|| Blocks: 블록이 깨지면 실행||``의 잔디블록을 눌러 드롭다운 메뉴를 확인하고 **케이크**로 바꾸세요.

        
## 단계 3
동물을 소환할게요. ``||Mobs:몹||``카테고리에 ``||Mobs:소환||``을 가져와  ``|| Blocks: 블록이 깨지면 실행||``아래에 넣으세요.


### ~ tutorialhint     

```blocks
blocks.onBlockBroken(CAKE, function () {
    mobs.spawn(PARROT, pos(0, 0, 0))
})
```

## 단계 4
앵무새가 소환되도록 할게요. ``||Mobs:소환||``의 드롭다운 메뉴를 확인하고 **앵무새**를 선택하세요. 그리고 소환되는 **Y**좌표값을 **1**로 바꾸세요.



## 단계 5
더 많은 앵무새를 소환할게요. ``||Loops:반복||``카테고리에 ``||Loops:반복(repeat)||``를 가져와 ``||Mobs:소환||``의 바깥에 넣으세요. 그리고 ``||Loops:반복(repeat)||``의 반복 횟수를 **24회**로 바꾸세요.

### ~ tutorialhint
```blocks
blocks.onBlockBroken(CAKE, function () {
    for (let index = 0; index < 24; index++) {
        mobs.spawn(PARROT, pos(0, 1, 0))
    }
})
```

## 단계 6
마인크래프트 게임으로 돌아가세요. 이 코드를 실행하려면 먼저 케이크를 설치해야 해요. 플레이어 인벤토리에 케이크를 추가하고(E키를 눌러 인벤토리를 열기) 핫바에서 케이크를 선택한 다음(마우스 휠 또는 숫자 키 사용) 마우스 오른족 버튼을 클릭하여 케이크를 설치하세요. 그리고 왼쪽 마우스 클릭을 하여 케이크를 부수세요. 그러면 앵무새 떼가 나타나게 됩니다.


