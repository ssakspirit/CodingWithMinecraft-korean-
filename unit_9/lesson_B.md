### @explicitHints 1
# 활동: 미로 만들기

## 단계 1
이 활동에는 시작코드가 준비되어 있어요. 

```template
let dirs: number[] = []
let index2 = 0
let index = 0
let right = 0
let left = 0
let forward = 0
let temp = 0
let moves: string[] = []
let tempArray: number[] = []
player.onChat("maze", function () {
    blocks.fill(
    blocks.block(Block.Stone),
    positions.create(-5, 0, -5),
    positions.create(5, 0, 5),
    FillOperation.Replace
    )
    agent.teleportToPlayer()
    blocks.place(blocks.block(Block.Air), positions.create(0, 0, 0))
    agent.setAssist(AgentAssist.DestroyObstacles, false)
    player.teleport(positions.create(0, 5, 0))
    player.say("let's dig that maze!")
    dig()
})
function shuffle() {
    tempArray = [forward, left, right]
    for (let i = 0; i < 3; i++) {
        index = Math.randomRange(0, 2)
        index2 = Math.randomRange(0, 2)
        temp = tempArray[index]
        tempArray[index] = tempArray[index2]
        tempArray[index2] = temp
    }
    for (let k = 0; k <= 3 - 1; k++) {
        dirs.push(tempArray[k])
    }
}
function dig() {
    player.say("dig deeper")
    shuffle()
    for (let i = 0; i < 3; i++) {
        player.say("try " + moves[dirs[dirs.length - 1]])
        // turn towards the new direction
        if (dirs[dirs.length - 1] == left) {
            agent.turn(TurnDirection.Left)
        } else if (dirs[dirs.length - 1] == right) {
            agent.turn(TurnDirection.Right)
        }
        // is this a wall?
        if (agent.detect(AgentDetection.Block, SixDirection.Forward)) {
            // dig once
            agent.destroy(SixDirection.Forward)
            agent.move(SixDirection.Forward, 1)
            // did we dig through a wall?
            if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
                player.say("oops, that was a wall")
                // move back and put the wall back
                agent.move(SixDirection.Back, 1)
                agent.place(SixDirection.Forward)
            } else {
                // yay! keep digging
                agent.destroy(SixDirection.Forward)
                agent.move(SixDirection.Forward, 1)
                // did we reach the end of the maze?
                if (!(agent.detect(AgentDetection.Block, SixDirection.Forward))) {
                    // go back and place wall
                    player.say("oops, too far")
                    agent.move(SixDirection.Back, 1)
                    agent.place(SixDirection.Forward)
                    agent.move(SixDirection.Back, 1)
                } else {
                    dig()
                    // start roll back
                    agent.move(SixDirection.Back, 2)
                }
            }
        }
        // turn back to the original direction
        if (dirs[dirs.length - 1] == left) {
            agent.turn(TurnDirection.Right)
        } else if (dirs[dirs.length - 1] == right) {
            agent.turn(TurnDirection.Left)
        }
        temp = dirs.pop()
    }
}
moves = ["forward", "left", "right"]
temp = 1
forward = 0
left = 1
right = 2
```

## 단계 2
에이전트는 미로에 뚫린 구멍을 메우기 위한 재료가 필요해요. 에이전트가 진행하면서 "학습"하고 있기 때문에, 실수로 미로 벽을 깨뜨릴 수도 있지만 나중에는 그 과정이 필요하다는 것을 알게 될거에요. 그리고 에이전트는 실수로 만든 구멍을 다시 메워요. 에이전트에게 그 구멍을 메울 블록을 줄 수 있어요. 에이전트의 왼쪽 상단 인벤토리 슬롯에 **참나무 목재**를 넣으세요.



## 단계 3
이 코드를 실행해 봅시다! 코드가 실행되는지 확인하려면 대화 창에 "maze" 명령을 입력하세요. 그리고 스페이스 바를 두 번 누르고 위로 날아올라 그 과정을 확인해보세요.


## 단계 4
출발점과 종착점을 만들어 주어야 하는데 이를 위해서는 에이전트가 미로를 성공적으로 완료한 지점을 알아야 해요. 

다음 활동에서는 에이전트가 미로를 성공적으로 탐색할 수 있도록 코드를 만들거에요. 다음 활동을 준비하려면 미로의 시작 영역과 끝 영역을 준비해야 해요.


## 단계 5
플레이어에게 다이아몬드 곡괭이와 레드스톤 블록을 주어야 해요. 곡괭이는 출발점과 종착점의 블록을 파괴하기 위해 필요하고 레드스톤 블록은 출발점과 종착점을 표시하는 역할을 해요.
채팅창을 열어 다음 명령어를 입력해서 아이템을 얻으세요.

**/give @s diamond_pickaxe**  
**/give @s redstone_block**

## 단계 6
이제 출발점과 종착점을 만들기만 하면 돼요. 아마도 서로 미로의 반대편 끝에 있을 거에요.


## 단계 7
시작점과 종착점의 블록을 파괴하세요. 그리고 그 아래에 레드스톤 블록을 놓으세요.


## 단계 8
다음 활동인 미로 탈출하기에서는 에이전트 아래에 레드스톤 블록이 있는 것을 발견하면 에이전트를 멈추게 할 것입니다. 이렇게 하면 모든 미로 활동은 완성입니다!

