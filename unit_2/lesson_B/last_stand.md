### @explicitHints 1

# 마지막 전투

## 단계 1
몹이 죽으면 코드가 실행되도록 할게요. ``||Mobs:몹||``카테고리에 ``||Mobs:몹이 죽었다면 실행||``을 가져오세요.

### ~ tutorialhint
```blocks
mobs.onMobKilled(CHICKEN, function () {
})
```

## 단계 2
몹의 처음 값은 **동물 닭**이기 때문에 **몬스터 좀비**로 바꿔줄게요. ``||Mobs:몹||``카테고리에 ``||Mobs:몬스터||``을 가져와 동물 닭이 있는 곳에 넣으세요.  ``||Mobs:몬스터||``의 처음 값은 **좀비**에요.

## 단계 3
좀비가 죽으면 새로운 좀비를 소환할게요. ``||Mobs:몹||``카테고리에 ``||Mobs:소환||``을 가져와 ``||Mobs:몹이 죽었다면 실행||`` 아래에 넣으세요.

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
mobs.spawn(CHICKEN, pos(0, 0, 0))
})
```

## 단계 4
소환하는 몹을 좀비로 바꿔줄게요. 단계2에서 했던 것처럼 ``||Mobs:몹||``카테고리에 ``||Mobs:몬스터||``를 가져와 동물 닭이 있는 곳에 넣으세요.  ``||Mobs:몬스터||``의 처음 값은 **좀비**에요.


### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
mobs.spawn(mobs.monster(ZOMBIE), pos(0, 0, 0))
})
```

## 단계 5
좀비 한 마리보다 두 마리가 더 낫지 않을까요? 좀비 한 마리를 처지하면 두 마리가 나오도록 해볼게요. ``||Loops:반복||``카테고리에 ``||Loops:반복(repeat)||``를 가져와 ``||Mobs:소환||``의 바깥에 넣으세요. 즉 ``||Loops:반복(repeat)||``안에 ``||Mobs:소환||``이 있어야 해요. 그리고 ``||Loops:반복(repeat)||``의 반복 횟수를 2회로 바꾸세요.

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 2; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), pos(0, 0, 0))
    }
})
```

## 단계 6
좀비가 어디서 소환되면 좋을까요? 어디서 나타나는 지 예측할 수 없도록 무작위 위치에서 소환되도록 해요. ``||Positions:위치||``카테고리에 ``||Positions:랜덤 위치 선택||``을 가져와 ``||Mobs:소환||``의 **좌표값(~0 ~0 ~0)**에 넣으세요.

## 단계 7
좀비가 소환될 임의의 위치 범위를 설정해요. ``||Positions:랜덤 위치 선택||``의 시작좌표를 **(~10 ~0 ~10)**, 끝좌표를 **(~-10 ~0 ~-10)**로 입력하세요.

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let i = 0; i < 2; i++) {
        mobs.spawn(mobs.monster(ZOMBIE), randpos(
            pos(10, 0, 10),
            pos(-10, 0, -10)
        ))
    }
})
```

## 단계 8

마인크래프트로 돌아가 실행해보세요.