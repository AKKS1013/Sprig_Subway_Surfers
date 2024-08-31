## IDK if this is how you're supposed to do this but this is my Sprig code from the web editor (link is also in README)

```javascript
/*
First time? Check out the tutorial game:
https://sprig.hackclub.com/gallery/getting_started

@title: subway surfers
@author: 
@tags: []
@addedOn: 2024-00-00
*/

const player = "p"
const obstacle_low = "l"
const obstacle_high = "h"

setLegend(
  [ player, bitmap`
................
................
.......000......
.......0.0......
......0..0......
......0...0.0...
....0003.30.0...
....0.0...000...
....0.05550.....
......0...0.....
.....0....0.....
.....0...0......
......000.......
......0.0.......
.....00.00......
................` ],
  [ obstacle_low, bitmap`
  ................
  ................
  ................
  ................
  ................
  ................
  3333333333333333
  3333333333333333
  3333333333333333
  3333333333333333`],
  [ obstacle_high, bitmap`
  5555555555555555
  5555555555555555
  5555555555555555
  5555555555555555
  5555555555555555
  5555555555555555
  5..............5
  5..............5
  5..............5
  5..............5`]
)

setSolids([ player, obstacle_low, obstacle_high ])

let level = 0
const levels = [
  map`
...
...
l.h
.p.`
]

setMap(levels[level])

setPushables({
  [ player ]: []
})

onInput("w", () => {
  getFirst(player).y -= 1
})

onInput("s", () => {
  getFirst(player).y += 1
})

onInput("a", () => {
  getFirst(player).x -= 1
})

onInput("d", () => {
  getFirst(player).x += 1
})

onInput("i", () => {
  if (getTile(getFirst(player).x, getFirst(player).y - 1)[0].type === obstacle_low) {
    getFirst(player).y -= 2
  }
})

onInput("k", () => {
  if (getTile(getFirst(player).x, getFirst(player).y - 1)[0].type === obstacle_high) {
    getFirst(player).y -= 2
  }
})


afterInput(() => {
  
})
```
