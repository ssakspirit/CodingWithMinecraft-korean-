### @explicitHints 1

# 활동: 황금길

## 단계 1 
플레이어가 걷을 때 코드를 실행하도록 할게요. ``||Player:플레이어가 걷고 있으면 실행||``을  가져오세요.

### ~ tutorialhint
``` blocks
         player.onTravelled(WALK, function () {
	
})
```

## 단계 2 
``||Blocks: 블록놓기||``를 가져와 ``||Player:플레이어가 걷고 있으면 실행||``아래에 끼워 넣으세요. 

### ~ tutorialhint      
``` blocks
         player.onTravelled(WALK, function () {
   		 blocks.place(GRASS, pos(0, 0, 0))
})
```

## 단계 3
이제 꽃을 심는 명령으로 바꿔 볼게요. ``||Blocks: 블록놓기||``의 잔디블록을 눌러 드롭다운 메뉴를 확인하고 **민들레**(노란꽃)를 선택하세요.

### ~ tutorialhint
        ```blocks
         player.onTravelled(WALK, function () {
    blocks.place(YELLOW_FLOWER, pos(0, 0, 0))
})
        ```

## 단계 4 
마인크래프트로 돌아가 1~2초 정도 걷기를 해보세요. 그리고 돌아서서 여러분이 만든 꽃길을 보세요. 


## 단계 5: 황금으로 도전!

이번에는 꽃 대신 황금블록을 놓는 것으로 바꿔볼게요. ``||Player: 플레이어가 걷고 있으면 실행||``아래 ``||Blocks: 블록놓기||``의 **민들레**를 **황금블록**으로 바꾸세요.

### ~ tutorialhint
``` blocks
player.onTravelled(TravelMethod.Walk, function () {
blocks.place(GOLD_BLOCK, pos(0, 0, 0))
})
```

## 단계 6
마인크래프트로 돌아가 똑같이 걸어보면서 어떻게 만들어지는지 확인해보세요. 황금 블록이 놓여지고 있지만 우리가 원하는 황금길의 모습은 아닌 것 같아요. 어떻게 하면 황금블록을 바닥에 설치할 수 있을까요?

## 단계 7  
좌표를 나타내는 (X, Y, Z) 세 가지 값 중에서 가운데 Y좌표는 높이를 의미해요. 따라서 Y좌표를 수정해요. **Y**좌표를  **-1**로 바꿔 황금블록이 한 칸 아래 설치되도록 해요.

### ~ tutorialhint
``` blocks
player.onTravelled(TravelMethod.Walk, function () {
blocks.place(GOLD_BLOCK, pos(0, -1, 0))
})
```

## 단계 8 
마인크래프트로 돌아가 실행 결과를 확인해보세요. 좌표를 수정해서 조금 더 넓은 벽돌길을 만들어 보거나 **다른 블록을 추가**해서 다양한 모습의 길을 표현해보세요.

### ~ tutorialhint
``` blocks
player.onTravelled(TravelMethod.Walk, function () {
blocks.fill(
GOLD_BLOCK,
pos(-1, -1, -1),
pos(1, -1, 1),
FillOperation.Replace
)
})
```

