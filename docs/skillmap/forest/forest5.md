# Head's Up


## Welcome @showdialog

Computer science is more important to firefighting than ever before. 
Let's add a heads-up-display (HUD) to help the pilot get information from their fire database in real-time. 

![A HUD can help keep you informed](/static/skillmap/forest/forest5.gif "Look what we're about to do!")



## 2. Remember 

**🎮 Try your game 🎮**

---

Can you remember which lines of code create each action?



## 3. Look Up

A HUD will help the pilot see how many fires are burning at any moment.

---

► From the ``||hud:HUD||`` category, grab the ``||hud: show fire HUD <Yes>||`` 
block and add it to **the end** of the ``||loops: on start||`` container.



```blocks
namespace SpriteKind {
    export const Water = SpriteKind.create()
    export const Fire = SpriteKind.create()
    export const Burnt = SpriteKind.create()
}

game.set_health_of_trees(7)
game.set_strength_of_wind(3)
game.set_dryness_of_grass(3)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`Fire Plane Right`, SpriteKind.Player)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)

for (let index = 0; index < 4; index++) {
    newFire = sprites.create(assets.image`fire`, SpriteKind.Fire)
    tiles.placeOnRandomTile(newFire, assets.tile`trees`)
}
//@highlight
hud.fire_hud(true)

```


## 4. Test 

**🎮 Test your game 🎮**

---

Is it any easier when you know there are still fires left?



## 5. Fire Danger

Anticipate how quickly fires will spread with the Fire Danger HUD.

---

► Add ``||hud: show danger level HUD <Yes>||`` 
to **the end** of the ``||loops: on start||`` container so you know how 
quickly your fires are likely to spread.


```blocks
namespace SpriteKind {
    export const Water = SpriteKind.create()
    export const Fire = SpriteKind.create()
    export const Burnt = SpriteKind.create()
}

game.set_health_of_trees(7)
game.set_strength_of_wind(3)
game.set_dryness_of_grass(3)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`Fire Plane Right`, SpriteKind.Player)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)

for (let index = 0; index < 4; index++) {
    newFire = sprites.create(assets.image`fire`, SpriteKind.Fire)
    tiles.placeOnRandomTile(newFire, assets.tile`trees`)
}
hud.fire_hud(true)
//@highlight
hud.danger_hud(true)
```

## 6. Healthy Forests

The crew needs to know how engulfed the forest is. Add another hud
to share information on how much of the forest is still healthy.

---

► Grab the the ``||hud: show forest HUD <Yes>||`` 
block and add it to **the end** of the ``||loops: on start||`` container to 
show how much of the forest remains.


```blocks
namespace SpriteKind {
    export const Water = SpriteKind.create()
    export const Fire = SpriteKind.create()
    export const Burnt = SpriteKind.create()
}

game.set_health_of_trees(7)
game.set_strength_of_wind(3)
game.set_dryness_of_grass(3)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`Fire Plane Right`, SpriteKind.Player)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)

for (let index = 0; index < 4; index++) {
    newFire = sprites.create(assets.image`fire`, SpriteKind.Fire)
    tiles.placeOnRandomTile(newFire, assets.tile`trees`)
}
hud.fire_hud(true)
hud.danger_hud(true)
//@highlight
hud.forest_hud(true)
```

## 7. Test Again 

**🎮 Test your game again 🎮**

---

Now you can see how quickly you're making progress. 
But the colors of the forest meter feel a little off. 
You can fix those in the next step.




## 8. Customize

Take a look at the rest of the blocks in the HUD category. Use as many as you want
to customize your game screen. 



```blocks

namespace SpriteKind {
    export const Water = SpriteKind.create()
    export const Fire = SpriteKind.create()
    export const Burnt = SpriteKind.create()
}

game.set_health_of_trees(7)
game.set_strength_of_wind(3)
game.set_dryness_of_grass(3)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`Fire Plane Right`, SpriteKind.Player)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)

for (let index = 0; index < 4; index++) {
    newFire = sprites.create(assets.image`fire`, SpriteKind.Fire)
    tiles.placeOnRandomTile(newFire, assets.tile`trees`)
}
hud.fire_hud(true)
hud.forest_hud(true)
hud.danger_hud(true)
hud.forest_hud_healthy(3)
hud.forest_hud_burned(4)
hud.forest_hud_label ("Forest Remaining")
hud.fire_hud_label ("Hot:")
```


## 9. Play 

**🎮 Time to play your game! 🎮**

---

Is the fire spreading too quickly?  
Try reducing the wind or the dryness of the grass.  

What happens when you bump the numbers all the way up to 10 or all the way down to 0? 




## Finale

👏 **You've done it!** 👏   

---

Congratulations on your game!  When you're done playing, you can click "Finish" 
and head back out to the skillmap to share it with friends or save it in your gallery.





```package
pxt-tilemaps=github:microsoft/pxt-tilemaps/
pxt-text=github:microsoft/arcade-text
arcade-premium-life=github:jwunderl/arcade-premium-life/
pxt-characterAnimations=github:microsoft/arcade-character-animations/
pxt-data=github:microsoft/arcade-sprite-data/
pxt-story=github:microsoft/arcade-storytelling/
arcade-sprite-util=github:jwunderl/arcade-sprite-util/
pxt-status-bar=github:jwunderl/pxt-status-bar
```

```template
namespace SpriteKind {
    export const Water = SpriteKind.create()
    export const Fire = SpriteKind.create()
    export const Burnt = SpriteKind.create()
}

controller.A.onEvent(ControllerButtonEvent.Repeated, function () {
    sprites.spray(mySprite, assets.image`water`)
})

game.set_health_of_trees(7)
game.set_strength_of_wind(3)
game.set_dryness_of_grass(3)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`Fire Plane Right`, SpriteKind.Player)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)

for (let index = 0; index < 4; index++) {
    newFire = sprites.create(assets.image`fire`, SpriteKind.Fire)
    tiles.placeOnRandomTile(newFire, assets.tile`trees`)
}

sprites.onCreated(SpriteKind.Fire, function (sprite) {
    sprite.startEffect(effects.fire)
    sprites.set_flame_strength(sprite, 10)
})

sprites.onOverlap(SpriteKind.Water, SpriteKind.Fire, function (sprite, otherSprite) {
    sprite.destroy()
    sprites.change_flame_strength_by(otherSprite, -1)
})

sprites.onOverlap(SpriteKind.Fire, SpriteKind.Fire, function (sprite, otherSprite) {
    sprite.destroy()
})

scene.onOverlapTile(SpriteKind.Fire, assets.tile`smoulder`, function (sprite, location) {
    sprite.destroy()
})

sprites.onDestroyed(SpriteKind.Fire, function (sprite) {
    tiles.setTileAt(tiles.locationOfSprite(sprite), assets.tile`smoulder`)
})

game.onUpdate(function () {
    sprites.random_spread(img`
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . 4 . . . . . 
. . . . 2 . . . . 4 4 . . . . . 
. . . . 2 4 . . 4 5 4 . . . . . 
. . . . . 2 4 d 5 5 4 . . . . . 
. . . . . 2 5 5 5 5 4 . . . . . 
. . . . . . 2 5 5 5 5 4 . . . . 
. . . . . . 2 5 4 2 4 4 . . . . 
. . . . . . 4 4 . . 2 4 4 . . . 
. . . . . 4 4 . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
. . . . . . . . . . . . . . . . 
`)
})

```

```ghost
hud.fire_hud(true)
hud.danger_hud(true)
hud.forest_hud(true)
hud.forest_hud_healthy(3)
hud.forest_hud_burned(4)
hud.forest_hud_label ("Healthy Forest:")
hud.danger_hud_label ("Fire Danger:")
hud.fire_hud_label ("Nope:")
```


```customts

  let spreadOptions: number[] = []

  let windSpeed = 5
  let tinder = 4
  let dryGrass = 5
  let spreadTimeBase = 2000
  let hoseDirection = 270
  let facing = 0
  let changeRate = 7
  let burnedColor = 2
  let healthyColor = 3

let statusbar = statusbars.create(82, 4, StatusBarKind.Health)
statusbar.top = 12
statusbar.left = 4
statusbar.max = tiles.tilemapRows() * tiles.tilemapColumns()
statusbar.value = tiles.tilemapRows() * tiles.tilemapColumns()
statusbar.setColor(healthyColor, burnedColor)
let statusLabel = textsprite.create("Healthy Forest", 0, 1)
statusLabel.setFlag(SpriteFlag.RelativeToCamera, true)
statusLabel.top = 2
statusLabel.left = 4
let fireLabel = textsprite.create("Fires:")
fireLabel.right = 145
fireLabel.top = 2
fireLabel.setMaxFontHeight(4)
fireLabel.setFlag(SpriteFlag.RelativeToCamera, true)
let hudBG = sprites.create(img`
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    cccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccccc
    `, SpriteKind.Player)
hudBG.bottom = 120
hudBG.z = 2000
let statusbar2 = statusbars.create(8, 8, StatusBarKind.Magic)
statusbar2.setLabel("Fire Danger:")
statusbar2.setColor(7, 2)
statusbar2.positionDirection(CollisionDirection.Bottom)
statusbar2.z = 2001
statusLabel.setFlag(SpriteFlag.Invisible, true)
statusbar.setFlag(SpriteFlag.Invisible, true)
fireLabel.setFlag(SpriteFlag.Invisible, true)
info.showScore(false)
statusbar2.setFlag(SpriteFlag.Invisible, true)
hudBG.setFlag(SpriteFlag.Invisible, true)



game.onUpdate(function () {
    statusbar.max = tiles.tilemapRows() * tiles.tilemapColumns()
    statusbar.value = tiles.tilemapRows() * tiles.tilemapColumns() - tiles.getTilesByType(assets.tile`smoulder`).length
    spreadTimeBase = 4500 - (250 * windSpeed + 250 * dryGrass - 100 * tinder)
        if (spreadTimeBase >= 4000) {
        statusbar2.setColor(7, 2)
        } else if (spreadTimeBase >= 3000) {
            statusbar2.setColor(5, 2)
        } else if (spreadTimeBase >= 2000) {
            statusbar2.setColor(4, 2)
        } else {
            statusbar2.setColor(2, 2)
        }
    if (sprites.allOfKind(SpriteKind.Fire).length <= 0) {
        hud.fire_hud(false)
        info.setScore(statusbar.value / statusbar.max * 100)
        game.splash("You saved " + convertToText(info.score()) + "% of the forest!")
        game.over(true)
    } else {
        info.setScore(sprites.allOfKind(SpriteKind.Fire).length)
    }
})



namespace animation {
    /*
     * Loops the passed frames on the sprite at the given interval whenever
     * the specified rule is true for that sprite.
     *
     * If more than one rule applies, the most specific rule will be used.
     * If multiple rules are equally specific, the currently executing rule
     * is favored (or one is chosen at random).
     *
     * @param sprite    the sprite to animate
     * @param frames    the images that make up that animation
     * @param frame     Interval the amount of time to spend on each frame in milliseconds
     * @param rule      the rule that decides when this animation will play
     */
    //% blockId=arcade_character_loop_frames2
    //% block="animate $sprite loop frames $frames interval (ms) $frameInterval when $rule"
    //% sprite.defl=mySprite
    //% frames.defl=Fire Plane Right
    //% sprite.shadow=variables_get
    //% frames.shadow=animation_editor
    //% frameInterval.shadow=timePicker
    //% rule.shadow=arcade_character_make_rule
    //% weight=100
    //% blockGap=8
    //% help=github:arcade-character-animations/docs/loop-character-animation
    export function loopFrames2(sprite: Sprite, frames: Image[], frameInterval: number, rule: number) {
        characterAnimations.loopFrames(sprite, frames, frameInterval, rule);
    }
}


namespace game {

    /*
     * Set the strength of your wind.
     * Higher numbers spread fire faster.
     */
    //% block="set strength of wind to $num"
    //% num.defl=3
    export function set_strength_of_wind (num: number) {
        windSpeed = num
    }

    /*
     * Set the health of your trees.
     * Lower numbers spread fire faster.
     */
    //% block="set health of trees to $num"
    //% num.defl=7
    export function set_health_of_trees (num: number) {
        tinder = num
    }

    /*
     * Set how dry your grass is.
     * Higher numbers spread fire faster.
     */
    //% block="set dryness of grass to $num"
    //% num.defl=3
    export function set_dryness_of_grass (num: number) {
        dryGrass = num
    }
}

//% color="#09282d" icon="\uf1e5"
//% block="HUD"
namespace hud {    

    /*
     * Show or hide the current number of burning fires.
     */
    //% block="show fire HUD $answer"
    //% answer.shadow="toggleYesNo"
    //% answer.defl=true
    export function fire_hud (answer: boolean) {

        if (answer) {
            fireLabel.setFlag(SpriteFlag.Invisible, false)
            info.showScore(true)
        } else {
            fireLabel.setFlag(SpriteFlag.Invisible, true)
            info.showScore(false)
        }

    }

    /*
     * Show or hide how much of the forest has burned.
     */
   //% block="show forest HUD $answer"
    //% answer.shadow="toggleYesNo"
    //% answer.defl=true
    export function forest_hud (answer: boolean) {

        if (answer) {
            statusLabel.setFlag(SpriteFlag.Invisible, false)
            statusbar.setFlag(SpriteFlag.Invisible, false)
        
        } else {
            statusLabel.setFlag(SpriteFlag.Invisible, true)
            statusbar.setFlag(SpriteFlag.Invisible, true)
        }

    }


    /*
     * Show or hide the fire danger level.
     */
   //% block="show danger level HUD $answer"
    //% answer.shadow="toggleYesNo"
    //% answer.defl=true
    export function danger_hud (answer: boolean) {

        if (answer) {
            hudBG.setFlag(SpriteFlag.Invisible, false)
            statusbar2.setFlag(SpriteFlag.Invisible, false)
        
        } else {
            hudBG.setFlag(SpriteFlag.Invisible, true)
            statusbar2.setFlag(SpriteFlag.Invisible, true)
        }

    }



    /*
    * Set the color for remaining live forest
    */
    //% block="set color of healthy forest meter to $color"
    //% color.shadow="colorindexpicker"
    //% color.defl=2
    export function forest_hud_healthy (color: number) {
        healthyColor = color
        statusbar.setColor(healthyColor, burnedColor)
    }

    /*
    * Set the color for burned forest
    */
    //% block="set color of burned forest meter to $color"
    //% color.shadow="colorindexpicker"
    //% color.defl=3
    export function forest_hud_burned (color: number) {
        burnedColor = color
        statusbar.setColor(healthyColor, burnedColor)
    }


    /*
     * Set the label for the forest HUD
     */
    //% block="set forest HUD label to $name"
    //% name.defl="Healthy Forest"
    export function forest_hud_label (name: string) {
        statusLabel.setText(name)
    }


    /*
     * Set the label for the fire-counting HUD
     */
    //% block="set fire HUD label to $name"
    //% name.defl="Fires:"
    export function fire_hud_label (name: string) {
        fireLabel.setText(name)
    }


    /*
     * Set the label for the fire danger HUD
     */
    //% block="set danger HUD label to $name"
    //% name.defl="Fire Danger Levels"
    export function danger_hud_label (name: string) {
        statusbar2.setLabel(name)
    }
    

}

namespace sprites {

    /*
     * Set the number of "lives" for your sprite.
     */
    //% block="set strength of $thisSprite=variables_get(mySprite) to $num"
    //% num.defl=10
    export function set_flame_strength (thisSprite: Sprite, num: number) {
        sprites.setDataNumber(thisSprite, "life", num)
        sprites.setDataNumber(thisSprite, "spreadTime",  spreadTimeBase + 1000)
    }

    /*
     * Add or remove "lives" from your sprite.
     */
    //% block="change strength of $thisSprite=variables_get(mySprite) by $num"
    //% num.defl=-1
    export function change_flame_strength_by (thisSprite: Sprite, num: number) {
        sprites.changeDataNumberBy(thisSprite, "life", num)
        for (let value of sprites.allOfKind(SpriteKind.Fire)) {
          if (sprites.readDataNumber(value, "life") <= 0) {
              effects.clearParticles(value)
              value.destroy()
          }
        }
    }

    /*
     * Choose a sprite to "spray" an image (in sprite form.)
     */
    //% block="spray from $thisSprite=variables_get(mySprite) using $img=screen_image_picker"
    //% img.defl=water
    export function spray (thisSprite: Sprite, img: Image) {

     if (controller.up.isPressed()) {
            if (controller.left.isPressed()) {
                facing = 225
            } else if (controller.right.isPressed()) {
                facing = 315
            } else if (controller.down.isPressed()) {
                
            } else {
                facing = 270
            }
        } else if (controller.left.isPressed()) {
            if (controller.right.isPressed()) {
                
            } else if (controller.down.isPressed()) {
                facing = 135
            } else {
                facing = 180
            }
        } else if (controller.right.isPressed()) {
            if (controller.down.isPressed()) {
                facing = 45
            } else {
                facing = 0
            }
        } else if (controller.down.isPressed()) {
            facing = 90
        }
  
        if (Math.abs(facing - hoseDirection) < 180) {
        if (facing < hoseDirection) {
            hoseDirection += 0 - changeRate
        } else {
            hoseDirection += changeRate
        }
        } else{
            if (facing < hoseDirection) {
                hoseDirection += changeRate
            } else {
                hoseDirection += 0 - changeRate
            }
            if (hoseDirection < 0) {
                hoseDirection += 360
            } else if (hoseDirection > 360) {
                hoseDirection += -360
            }
            hoseDirection = hoseDirection % 360
        }
        let waterProj = sprites.createProjectileFromSprite(img, thisSprite,  150 * Math.cos(spriteutils.degreesToRadians(hoseDirection)), 150 * Math.sin(spriteutils.degreesToRadians(hoseDirection)))
        waterProj.setKind(SpriteKind.Water)
  }

    /*
     * Spread current fires according to wind speed, 
     * dryness of grass, and health of trees.
     */
    //% block="random spread $myImage=screen_image_picker"
    export function random_spread (myImage: Image) {

    for (let value of sprites.allOfKind(SpriteKind.Fire)) {
            if (sprites.readDataNumber(value, "life") <= 0) {
                effects.clearParticles(value)
                value.destroy()
            }

            let list2 = [-32,-16,0,16,32,16,-16]
            if (game.runtime() > sprites.readDataNumber(value, "spreadTime")) {
                sprites.setDataNumber(value, "spreadTime", game.runtime() + randint(spreadTimeBase, spreadTimeBase + 1000))
                let newFire = sprites.create(myImage, SpriteKind.Fire)
                newFire.setPosition(value.x + list2._pickRandom(), value.y)
                sprites.setDataNumber(newFire, "spreadTime", game.runtime() + randint(spreadTimeBase, spreadTimeBase + 1000))
                if (Math.percentChance(50)) {
                    newFire.y += list2._pickRandom()
                }
                if (tiles.tileIsWall(tiles.locationOfSprite(newFire))) {
                    newFire.setPosition(value.x, value.y)
                }
            }
        }
     }

}
```


```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "images.g.jres": "{\n    \"a5zAhGKtmEx`ww9FE(zZ\": {\n        \"data\": \"hwQEAAQAAACQCQAAmZkAAJmZAACQCQAA\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"water\"\n    },\n    \"image3\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAIAIAAAAAAAAAJAIABAAAAABAJUIEAAAAANBVRQAAAAAAVFUEAAAAAEBVVQIAAAAARERUJAAAAAAAAEBEAAAAAAAAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"fire\"\n    },\n    \"image2\": {\n        \"data\": \"hwQYAAwAAAAAAPAPAAAAAAAAgA8AAAAA8P+PDwAAAACAuIsPsPsAAACIiw+/+AAAAICI+7v4AAAAAIi7u/gAAAAAuLu7+AAAAAC4u4v5AAAA8Li7iA8AAADwuIv4AAAAAI+4i/8PAAAAj7u7+wwAAPCLu7v4AAAAv/u7ufgPAAC/+7u5+AwAAL/7u734AAAAv/+7vfgAAACfj7+9+AAAAP8AH7v4AAAAAAC/uw8AAAAAAL+LDwAAAAAA8PsAAAAAAADwDwAAAAA=\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"Fire Plane Right\"\n    },\n    \"image7\": {\n        \"data\": \"hwQYAAwAAAAAAPAPAAAAAAAA8PsAAAAAAAC/iw8AAAAAAL+7DwAAAP8AH7v4AAAAn4+/vfgAAAC//7u9+AAAAL/7u734AAAAv/u7ufgMAAC/+7u5+A8AAPCLu7v4AAAAAI+7u/sMAAAAj7iL/w8AAADwuIv4AAAAAPC4u4gPAAAAALi7i/kAAAAAuLu7+AAAAACIu7v4AAAAgIj7u/gAAACIiw+/+AAAgLiLD7D7AADw/48PAAAAAAAAgA8AAAAAAADwDwAAAAA=\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"Fire Plane Left\"\n    },\n    \"anim1\": {\n        \"namespace\": \"myAnimations\",\n        \"id\": \"anim1\",\n        \"mimeType\": \"application/mkcd-animation\",\n        \"data\": \"YmMwMjE4MDAxMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDBmZmZmZmYwMDAwMDAwMDAwMDAwMDAwMDA5ZmJiYmIwZjAwMDAwMDAwZjgwMDAwMDBmMGJmYmJmYjBmMDAwMDgwZjgwMDAwMDA4MGZmZmY4OGY4MGYwMDg4ZmIwMDAwZmZmZmJiYmJiYjg4ODg4OGI4ZmIwMGZmYmJiMWJiYmJiYmJiYmI4Yjg4ODhmOGJmYmJkYmRkOTliYmJiYmJiYmZiZmZmZmYwYjhiYmJiYmJiYjg4YmJiYjBmMDAwMDAwZmY4ODg4ODhiODhmYjhiYmZiMDAwMDAwMDBmZmZmZmZmZmZmODhiYmJiMGIwMDAwMDAwMDAwZmNjMDBmOWY4ODg4MGIwMDAwMDAwMDAwMDAwMDAwZjBmZmZmMGYwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDBmZmZmZmYwMDAwMDAwMDAwZjgwMDAwMDA5ZmJiYmJmZjAwMDAwMDgwZjgwMDAwMDA4MGZmZmZmZjBmMDAwMDg4ZmIwMDAwZmZmZmJiYmJiYmZmODg4OGI4ZmIwMGZmYmJkYjk5OTliYmJiYmI4Yjg4ODhmOGJmYmJiYmJiYmJiYmJiYmJiYmZiZmZmZmYwYjhiYmJiYmJiYjg4YjhiYmZiMDAwMDAwZmY4ODg4ODhiODhmODhiYmJiMGIwMDAwMDBmZmZmZmZmZmZmOWY4ODg4MGIwMDAwMDAwMDAwZmNjMDBmZjBmZmZmMGYwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==\",\n        \"displayName\": \"Fire Plane Left Animation\"\n    },\n    \"anim2\": {\n        \"namespace\": \"myAnimations\",\n        \"id\": \"anim2\",\n        \"mimeType\": \"application/mkcd-animation\",\n        \"data\": \"YmMwMjE4MDAxMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwZmZmZmZmMDAwMDAwOGYwMDAwMDAwMGYwYmJiYmY5MDAwMDAwOGYwODAwMDBmMGJmYmJmYjBmMDAwMDAwYmY4ODAwZjA4Zjg4ZmZmZjA4MDAwMDAwYmY4Yjg4ODg4OGJiYmJiYmZmZmYwMDhmODg4OGI4YmJiYmJiYmJiYjFiYmJmZmZmZmZiZmJiYmJiYmJiOTlkZGJkYmJmYjAwMDBmMGJiYmI4OGJiYmJiYmJiOGIwZjAwMDBiZmJiOGJmODhiODg4ODg4ZmYwMDAwYjBiYmJiODhmZmZmZmZmZmZmMDAwMDAwYjA4ODg4ZjlmMDBjY2YwMDAwMDAwMDAwZjBmZmZmMGYwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwOGYwMDAwMDAwMDAwZmZmZmZmMDAwMDAwOGYwODAwMDAwMGZmYmJiYmY5MDAwMDAwYmY4ODAwMDBmMGZmZmZmZjA4MDAwMDAwYmY4Yjg4ODhmZmJiYmJiYmZmZmYwMDhmODg4OGI4YmJiYmJiOTk5OWJkYmJmZmZmZmZiZmJiYmJiYmJiYmJiYmJiYmJmYjAwMDBiZmJiOGI4OGJiYmJiYmJiOGIwZjAwYjBiYmJiODhmODhiODg4ODg4ZmYwMDAwYjA4ODg4ZjlmZmZmZmZmZmZmMDAwMDAwZjBmZmZmMGZmMDBjY2YwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==\",\n        \"displayName\": \"Fire Plane Right Animation\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myImages\"\n    }\n}",
  "images.g.ts": "// Auto-generated code. Do not edit.\nnamespace myImages {\n\n    helpers._registerFactory(\"image\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"a5zAhGKtmEx`ww9FE(zZ\":\n            case \"water\":return img`\n. 9 9 . \n9 9 9 9 \n9 9 9 9 \n. 9 9 . \n`;\n            case \"image3\":\n            case \"fire\":return img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . 4 . . . . . \n. . . . 2 . . . . 4 4 . . . . . \n. . . . 2 4 . . 4 5 4 . . . . . \n. . . . . 2 4 d 5 5 4 . . . . . \n. . . . . 2 5 5 5 5 4 . . . . . \n. . . . . . 2 5 5 5 5 4 . . . . \n. . . . . . 2 5 4 2 4 4 . . . . \n. . . . . . 4 4 . . 2 4 4 . . . \n. . . . . 4 4 . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n`;\n            case \"image2\":\n            case \"Fire Plane Right\":return img`\n. . . . . . . . . . . . . . f f f f f f . . . . \n. . f 8 . . . . . . . . . f b b b b 9 f . . . . \n. . f 8 8 . . . . . . f f b b b b f f . . . . . \n. . f b 8 8 . . . f f 8 8 8 f f f f 8 . . . . . \n. . f b b 8 8 8 8 8 8 8 b b b b b b f f f f . . \nf 8 8 8 8 8 8 b b b b b b b b b b b b 1 b b f f \nf f f f f b b b b b b b b b 9 9 d d d b b b b f \n. . . . . f b b b b 8 8 b b b b b b b b b 8 f . \n. . . . f b b b b 8 8 f b 8 8 8 8 8 8 8 f f . . \n. . . b b b b b 8 8 f f f f f f f f f f . . . . \n. . . b 8 8 8 8 9 f . f c . f c . . . . . . . . \n. . . f f f f f f . . . . . . . . . . . . . . . \n`;\n            case \"image7\":\n            case \"Fire Plane Left\":return img`\n. . . . f f f f f f . . . . . . . . . . . . . . \n. . . . f 9 b b b b f . . . . . . . . . 8 f . . \n. . . . . f f b b b b f f . . . . . . 8 8 f . . \n. . . . . 8 f f f f 8 8 8 f f . . . 8 8 b f . . \n. . f f f f b b b b b b 8 8 8 8 8 8 8 b b f . . \nf f b b 1 b b b b b b b b b b b b 8 8 8 8 8 8 f \nf b b b b d d d 9 9 b b b b b b b b b f f f f f \n. f 8 b b b b b b b b b 8 8 b b b b f . . . . . \n. . f f 8 8 8 8 8 8 8 b f 8 8 b b b b f . . . . \n. . . . f f f f f f f f f f 8 8 b b b b b . . . \n. . . . . . . . c f . c f . f 9 8 8 8 8 b . . . \n. . . . . . . . . . . . . . . f f f f f f . . . \n`;\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"animation\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"Fire Plane Left Animation\":\n            case \"anim1\":return [img`\n........................\n........................\n....ffffff..............\n....f9bbbbf.........8f..\n.....ffbbbbff......88f..\n.....8ffff888ff...88bf..\n..ffffbbbbbb8888888bbf..\nffbb1bbbbbbbbbbbb888888f\nfbbbbddd99bbbbbbbbbfffff\n.f8bbbbbbbbb88bbbbf.....\n..ff8888888bf88bbbbf....\n....ffffffffff88bbbbb...\n........cf.cf.f98888b...\n...............ffffff...\n........................\n........................\n`, img`\n........................\n........................\n........................\n....ffffff..........8f..\n....f9bbbbff.......88f..\n.....8fffffff.....88bf..\n..ffffbbbbbbff88888bbf..\nffbbbd9999bbbbbbb888888f\nfbbbbbbbbbbbbbbbbbbfffff\n.f8bbbbbbbbb888bbbbf....\n..ff8888888bf888bbbbb...\n....fffffffffff98888b...\n........cf.cf..ffffff...\n........................\n........................\n........................\n`];\n            case \"Fire Plane Right Animation\":\n            case \"anim2\":return [img`\n........................\n........................\n..............ffffff....\n..f8.........fbbbb9f....\n..f88......ffbbbbff.....\n..fb88...ff888ffff8.....\n..fbb8888888bbbbbbffff..\nf888888bbbbbbbbbbbb1bbff\nfffffbbbbbbbbb99dddbbbbf\n.....fbbbb88bbbbbbbbb8f.\n....fbbbb88fb8888888ff..\n...bbbbb88ffffffffff....\n...b88889f.fc.fc........\n...ffffff...............\n........................\n........................\n`, img`\n........................\n........................\n........................\n..f8..........ffffff....\n..f88.......ffbbbb9f....\n..fb88.....fffffff8.....\n..fbb88888ffbbbbbbffff..\nf888888bbbbbbb9999dbbbff\nfffffbbbbbbbbbbbbbbbbbbf\n....fbbbb888bbbbbbbbb8f.\n...bbbbb888fb8888888ff..\n...b88889fffffffffff....\n...ffffff..fc.fc........\n........................\n........................\n........................\n`];\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><variables><variable type=\"KIND_SpriteKind\" id=\"~zp:h99l$t:puWt^7HpS\">Fire</variable><variable type=\"KIND_SpriteKind\" id=\"b3qt}A6k{Y|Yr^LaRE6Y\">Burnt</variable><variable type=\"KIND_SpriteKind\" id=\"$J.Bxo|M{mi1P+`[A1?4\">Player</variable><variable type=\"KIND_SpriteKind\" id=\"uGq)5bGL26c-(,L_;6CB\">Projectile</variable><variable type=\"KIND_SpriteKind\" id=\"Rvp^^=8OAqmCeIUNc?{b\">Food</variable><variable type=\"KIND_SpriteKind\" id=\"@6hn/DkVnQ8`I`kv[x?{\">Enemy</variable><variable type=\"KIND_SpriteKind\" id=\"|/YN~|~tVm4.!8L*HioT\">Text</variable><variable type=\"KIND_SpriteKind\" id=\"]~dhh95wxb|OZ0;WHf|]\">StatusBar</variable><variable type=\"KIND_StatusBarKind\" id=\"nTxOIz$-~=7EJc(t7T#_\">Health</variable><variable type=\"KIND_StatusBarKind\" id=\"391Why~W9^9lqcoQQG0x\">Energy</variable><variable type=\"KIND_StatusBarKind\" id=\"GBBC+=aw4b7x0!=58!!*\">Magic</variable><variable type=\"KIND_StatusBarKind\" id=\"pJ,Vd?#{4|dO/(g(|A-H\">EnemyHealth</variable><variable id=\"8rA}EiRM2wHj_s|13j}t\">statusbar</variable><variable id=\"VLdeXP[_@1:J9GD!),Ia\">tinder</variable><variable id=\"h][qwl3T*G1}(r7MV7oZ\">mySprite</variable><variable id=\"jrX,vISS7PDA//D]zEB3\">dryGrass</variable><variable id=\"0Ko[yse36[jD#J3@^=53\">windSpeed</variable><variable id=\"fd9l0*ffabpTSLEUUfi:\">value</variable><variable id=\"d%BcCARShMY%=*.GH1gF\">list2</variable><variable id=\"aIS.OGw=J[wCQsP49qIZ\">spreadTimeBase</variable><variable id=\"lyaL+*o.a~O]/aD[uDr9\">newFire</variable><variable id=\"{V$QzFzwP$ImZ+nnTL^e\">facing</variable><variable id=\"-D8I`o1aNA~es3(JYLMk\">changeRate</variable><variable id=\"[?Yd11dvxugieayng`{_\">hoseDirection</variable><variable id=\"X[$g5gKr|jHN.aimnfy9\">projectile</variable><variable id=\"?SUf,tio_PwlgM:;5(A/\">myImage</variable><variable id=\"/LO0y==XA-vfLCV*rx!@\">mySprite2</variable><variable id=\"Yu@%}1H+Gs5NsuvWYM.y\">textSprite</variable><variable id=\"OIoJ`*MPvT]$kbOt{U=N\">textSprite2</variable></variables><comment data=\"0\" x=\"0\" y=\"0\" h=\"120\" w=\"480\">Track the remaining forest using a statusbar. You could initialize this using magic or remove the \"total tilemap rows/columns\" by just telling them what value to enter for the max/value</comment><block type=\"pxt-on-start\" x=\"-350\" y=\"-490\"><statement name=\"HANDLER\"><block type=\"variables_set\"><field name=\"VAR\" id=\"h][qwl3T*G1}(r7MV7oZ\">mySprite</field><value name=\"VALUE\"><shadow xmlns=\"http://www.w3.org/1999/xhtml\" type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`Fire Plane Left`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.image7\"}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value></block></value></block></statement></block></xml>",
  "main.ts": "namespace SpriteKind {\n    export const Fire = SpriteKind.create()\n    export const Burnt = SpriteKind.create()\n}\n/**\n * Track the remaining forest using a statusbar. You could initialize this using magic or remove the \"total tilemap rows/columns\" by just telling them what value to enter for the max/value\n */\nlet mySprite = sprites.create(assets.image`Fire Plane Left`, SpriteKind.Player)\n",
  "pxt.json": "{\n    \"name\": \"Save the Forest Assets Only\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"tilemaps\": \"github:microsoft/pxt-tilemaps#v1.11.0\",\n        \"arcade-sprite-data\": \"github:microsoft/arcade-sprite-data#v0.1.0\",\n        \"arcade-sprite-util\": \"github:jwunderl/arcade-sprite-util#v0.2.4\",\n        \"arcade-story\": \"github:microsoft/arcade-storytelling#v1.0.2\",\n        \"arcade-minimap\": \"github:microsoft/arcade-minimap#v0.6.1\",\n        \"pxt-status-bar\": \"github:jwunderl/pxt-status-bar#v0.4.1\",\n        \"arcade-text\": \"github:microsoft/arcade-text#v1.3.0\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"images.g.jres\",\n        \"images.g.ts\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.5.46\",\n        \"tag\": \"v1.5.46\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/4f3f29bef862bcab766a47e42db2d3ed6b0060b1\",\n        \"target\": \"1.5.46\",\n        \"pxt\": \"7.1.25\"\n    },\n    \"preferredEditor\": \"blocksprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile3\": {\n        \"data\": \"hwQQABAAAABmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZmZg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"wall\"\n    },\n    \"tile2\": {\n        \"data\": \"hwQQABAAAABmZma8zGxmZmZmxsu7bGZmZma268zMbGZmZsXsxrtsZmZmzETCy2xmZmbL7sTMZmZmZcZOzrzMZmZmTOTkvMtmZma8VOTMzGZmZrwuzstsZmZmy07Cy2xmZmZL5MbMbGZmZsblvMxmZmZmxsu8zGZmZmZmzMtmZmZmZma8bGZmZg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"firePit\"\n    },\n    \"tile1\": {\n        \"data\": \"hwQQABAAAABmZmZmZmZmZmZmZoaIZmZmZmaGeHdoZmZmZndmdmdmZmaGdndmZ2ZmZnhmd2d3Zmxmd2d2Z3fGbHZ3Z3Znd+5sZndndmd3xm5meGZ3Z3dmbGaGdndmZ2ZmZmZ4ZnZnZmZmZoZ4d2hmZmZmZoaIZmZmZmZmZmZmZmZmZmZmZmZmZg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"trees\"\n    },\n    \"tile8\": {\n        \"data\": \"hwQQABAAAABm5mZmZmb+bmZmZmZm5u5uZmb/Zmb2u/72Zr9vZr67+2Zm9vtmvfv7Zv///2+8vO/2u+6+/P///mb//+u+7O6+9mZmv+7u7v9mZmb27/7//mbWZu/+/7vvZmb2/m++y/tmZvZvZv67+2ZvZsZm5rv+Zu5vZmbm7v5m5mZmZmbmbg==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"smoulder\"\n    },\n    \"level1\": {\n        \"id\": \"level1\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAxMjAwMTIwMDAzMDMwMzAzMDMwMzAzMDMwMzAzMDMwMzAzMDMwMzAzMDMwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMjAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDMwMzAzMDMwMzAzMDMwMzAzMDMwMzAzMDMwMzAzMDMwMzAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile1\",\n            \"myTiles.tile2\",\n            \"myTiles.tile3\"\n        ],\n        \"displayName\": \"level1\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile3 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile2 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile1 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile8 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"level1\":\n            case \"level1\":return tiles.createTilemap(hex`12001200030303030303030303030303030303030303030101010101010101010101010101010103030101010101010101010101010101010103030102010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030101010101010101010101010101010103030303030303030303030303030303030303`, img`\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n..................\n`, [myTiles.transparency16,myTiles.tile1,myTiles.tile2,myTiles.tile3], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n            case \"wall\":\n            case \"tile3\":return tile3;\n            case \"firePit\":\n            case \"tile2\":return tile2;\n            case \"trees\":\n            case \"tile1\":return tile1;\n            case \"smoulder\":\n            case \"tile8\":return tile8;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
```

