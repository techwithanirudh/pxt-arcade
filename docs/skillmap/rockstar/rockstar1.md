# 80's Rockstar Backstage


## Welcome @showdialog

Congratulations!  You've just accepted a job managing Jerry, the last remaining  **80's Rockstar!** 

![Navigate the maze backstage](/static/skillmap/rockstar/rockstar1.gif "Look what we're about to do today!")

We'll walk you through the skills you'll need to help Jerry navigate backstage to collect equipment from the show while avoiding screaming fans!




## 2. Let's Get Started 

**Your scene has already been set!**

---

- :binoculars: Look at your workspace to see that the **background color** and [__*tilemap*__](#tiled "a scene or world created using predefined tiles") 
have already been added to this activity.  

💡 Both blocks have been put inside the ``||loops: on start||`` container so they load as soon as the game starts.



## 3. We need a HERO

**👏  We need Jerry! 👏**

Our moving character is called a [__*sprite*__](#sprote "2-D image that move on the screen"). Let's create a rockstar sprite and get it moving before we do anything else. 

---

- :puzzle: From the ``||sprites:Sprites||`` category, drag ``||variables:set [mySprite] to sprite [ ] of kind [Player]||`` to **the end** of the ``||loops:on start||`` container.

- :mouse pointer: To add Jerry, click the empty grey box, then toggle to **My Assets** and click  **rockstar**.


```blocks
scene.setBackgroundColor(13)
tiles.setTilemap(tilemap`level1`)
// @highlight
let mySprite = sprites.create(assets.image`rockstar`, SpriteKind.Player)
```


## 4. Control the Player

**Time to get the sprite moving**

---

- :puzzle: From ``||controller:Controller||``, drag ``||controller:move [mySprite] with buttons ⊕||``   
to **the end** of the ``||loops:on start||`` container.


```blocks
scene.setBackgroundColor(13)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`rockstar`, SpriteKind.Player)
// @highlight
controller.moveSprite(mySprite)
```


## 5. Try It

**🕹️ Test on the game screen 🕹️ **

---

Jerry appears in the middle of a wall and gets completely lost when moving off screen!  

We'll fix that over the next couple of steps.



## 6. Trapped Backstage 

**The sprite should appear at the stairs behind the stage. **

---

- :puzzle: To start Jerry at the stage door, open ``||scene:Scene||`` and drag ``||scene: place [mySprite] on top of random [ ]||`` to **the end** of the ``||loops:on start||`` container.

- :mouse pointer: Click the checkered tile and select the teal stage door called **stage** from the grid menu.


```blocks
scene.setBackgroundColor(13)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`rockstar`, SpriteKind.Player)
controller.moveSprite(mySprite)
// @highlight
tiles.placeOnRandomTile(mySprite, assets.tile`stage`)

```


## 7. Follow with Camera 


- :puzzle: Next, to keep Jerry in sight, open ``||scene:Scene||`` again and drag 
``||scene:camera follow sprite [mySprite]||`` to **the end** of the ``||loops:on start||`` container.

```blocks
scene.setBackgroundColor(13)
tiles.setTilemap(tilemap`level1`)
let mySprite = sprites.create(assets.image`rockstar`, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.placeOnRandomTile(mySprite, assets.tile`stage`)
// @highlight
scene.cameraFollowSprite(mySprite)

```


## 8. Look Again

**🕹️ Try your maze in the game window 🕹️ **

---

You should be able to see your sprite as you move it around backstage.  Can you make it to the door?




## Finale

🔥 **Well done!** 🔥   

---

Take a look at all of the things to see in the maze, then click **Finish** to head to the next level of the 
skillmap where we'll show you how to add points for each instrument Jerry collects!


```package
pxt-tilemaps=github:microsoft/pxt-tilemaps/
```


```template
scene.setBackgroundColor(13)
tiles.setTilemap(tilemap`level1`)
```

```ghost
scene.onOverlapTile(SpriteKind.Player, assets.tile`instrument3`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`transparency16`)
    info.changeScoreBy(1)
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`instrument2`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`transparency16`)
    info.changeScoreBy(1)
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`instrument1`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`transparency16`)
    info.changeScoreBy(1)
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`door`, function (sprite, location) {
    game.over(true)
})
scene.onOverlapTile(SpriteKind.Player, assets.tile`fan1`, function (sprite, location) {
    tiles.setTileAt(location, assets.tile`transparency16`)
    info.changeScoreBy(-1)
})

let mySprite = sprites.create(assets.image`rockstar`, SpriteKind.Player)
controller.moveSprite(mySprite, 100, 100)
scene.cameraFollowSprite(mySprite)
tiles.placeOnRandomTile(mySprite, sprites.dungeon.stairLarge)
info.startCountdown(60)
info.setScore(0)
```



```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "images.g.jres": "{\n    \"HR6MQZ`+AH8fF_EGjDHy\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAADw////DwAA8P/v7u5NAAD/7//k/v8AAP/ustEe0f8A7+7y3xTR/wDv7kLdFNEPAF/u8t8U0f8AX+Wy0R7R/wD/5f/k/v8AAPD/7+7uTQAAAPD///8PAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"rockstar\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myImages\"\n    }\n}",
  "images.g.ts": "// Auto-generated code. Do not edit.\nnamespace myImages {\n\n    helpers._registerFactory(\"image\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"HR6MQZ`+AH8fF_EGjDHy\":\n            case \"rockstar\":return img`\n. . . . . . . . . . . . . . . . \n. . . . . . . . . . . . . . . . \n. . . . f f f f f f f . . . . . \n. . . f f f e e 5 5 f f . . . . \n. . . f f e e e e 5 5 f . . . . \n. . f f e e e e e e e f f . . . \n. . f f f 2 2 2 2 2 f f f . . . \n. . f e f b f 4 f b f e f . . . \n. . f e 4 1 f d f 1 4 e f . . . \n. . f e e d d d d d e e f . . . \n. . f e e e 4 4 4 e e e f . . . \n. . f e f 1 1 1 1 1 f e f . . . \n. . f d f 1 1 1 1 1 f d f . . . \n. . . 4 f d d d d d f 4 . . . . \n. . . . . f f f f f . . . . . . \n. . . . . f f . f f . . . . . . \n`;\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"animation\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><variables><variable type=\"KIND_SpriteKind\" id=\"9Sqe8HXL4X84wkraZ5db\">Player</variable><variable type=\"KIND_SpriteKind\" id=\"Y6M2.$ok|6Iqk51XBFiL\">Projectile</variable><variable type=\"KIND_SpriteKind\" id=\"erp_Gfm8vZI^rliRJIWl\">Food</variable><variable type=\"KIND_SpriteKind\" id=\"}fU`-w.y:4?;2mojQ!4~\">Enemy</variable><variable id=\"U/V#[xr[UAbg!aWXJbqo\">mySprite</variable><variable id=\"QV6s,a^7Wec/Z6dGV,_]\">list</variable></variables></xml>",
  "main.ts": "\n",
  "pxt.json": "{\n    \"name\": \"80s Rockstar - Assets Only\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"tilemaps\": \"github:microsoft/pxt-tilemaps#v1.11.0\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"images.g.jres\",\n        \"images.g.ts\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.5.56\",\n        \"tag\": \"v1.5.56\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/fb33e381b78eca2163bc40e2b26bdfdc9e7ebd81\",\n        \"target\": \"1.5.56\",\n        \"pxt\": \"7.1.35\"\n    },\n    \"preferredEditor\": \"blocksprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"tile4\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD8//////////zu7u7u7u7+/P7u7v/u/v787u7+u+/u/vzu7r/M++7+/O7uv8z77v787u7+u+/u/vz+7u7/7v7+/O7u7u7u7v78/////////8zMzMzMzMzMzMzMzMzMzAwAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"instrument3\"\n    },\n    \"tile5\": {\n        \"data\": \"hwQQABAAAAAAwBEREQwAAADAETMRDAAAAMARMRMMAAAAwBEzEQwAAADAERERDAAAAMD87s8MAAAAAPDuwQAAAAD///8RDADA8O/v7h7LDM/P7+///xGM/8/s7vEvEWb///zu8SIRhgD//P7u7v9m/8/8/u7+7o//wP/v7v/uD88A////D/8AwA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"fan1\"\n    },\n    \"tile6\": {\n        \"data\": \"hwQQABAAAAAAwBEREQwAAADAETMRDAAAAMARMRMMAAAAwBEzEQwAAADAERERDAAAAAD/RMwMAAAA8P9EwQAAAAD//7wRDADA8L9PRBvLDM/Pv0/u7hGM/8+8S+EuEWb//8xL4SIRhgD//PtEtMxm/8/8+/S/RIj/wP+7/89EDM8A////D8wAwA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"fan2\"\n    },\n    \"tile7\": {\n        \"data\": \"hwQQABAAAAAAwBEREQwAAADAETMRDAAAAMARMRMMAAAAwBEzEQwAAADAERERDAAAAMDM3cwMAAAAAMDdwQAAAAD7/88RDADA0LXf3RvLDM8dtdzu7hGM/x3R2+EuEWb/XVHb4SIRhgBdUcvdvbtm/x1R+9293Yj/EFW13cvdC88AXVXPDLsAwA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"fan3\"\n    },\n    \"tile3\": {\n        \"data\": \"hwQQABAAAAAAAAAA/+8AAAAAAPD/7g4AAAAA8G5E5AAAAADwRkREDgAA8P9GRETkAAD/L0TuROQAAO9GRORO5AAAb0T+Qk7kAABuRP9PROQAAOBE8k5EDgAA/09EJO4AAPDv7kTkAADw/+4A7g4AAO/kDgAAAAAAT+QAAAAAAADvDgAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"instrument2\"\n    },\n    \"tile9\": {\n        \"data\": \"hwQQABAAAAAAAAAAy8wMAAAAALDb280AAAAA+xHbzQAAALD7G73dDAAA+/0fsd0MALD727/R280A+/3fzBHbzbD727/RHbHMsP3fzBEd3c2w3b/RHbHLDADbzBEd3c0AANvRHbHLDAAAsBEd3c0AAACwHbHLDAAAAAAb3c0AAAAAALvLDAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"instrument4\"\n    },\n    \"tile10\": {\n        \"data\": \"hwQQABAAAAAAwMz8////AAC8LLLMzPwAwLss0sy7/AC8u9zdvMzLD7y7u93f37wPvLvL3dv/vA+8u8vdzf2/D8C7y9v93Pv/wLu73L3////Au7vcvf///MC7u8zMzMz8ALy7MzMzM/sAvDuzu7u7DAC8M7u7u8sAADyzu7u7DAAAwMzMzMwAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"camera\"\n    },\n    \"tile2\": {\n        \"data\": \"hwQQABAAAAAAAAAA/+4AAAAAAPDu7g4AAAAA4G4i4gAAAADwJiIiDgDw7/8mzCLiAP/u/yLcLOIA7yIiIrHN4gAuIiISEcziAC4C8BMRIeIA7gDvPhEiDgAA8O4u4+4AAADvDi7iAADw/+4AIuIAAO/kDgDuDgAAT+QAAAAAAADvDgAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"instrument1\"\n    },\n    \"tile12\": {\n        \"data\": \"hwQQABAAAADM/P//zPzM/Mz8zPzMzMz8zMzM/MzMzPzM/Mz8zPzM/Mz8zPzM/Mz8zPzMzMz8zPzM/MzMzPzMzP//zPzM/MzMzPzM/Mz8zPzM/Mz8zPzM/Mz8zPz//8z8zMzM/Mz8zPzMzMz8zPzM/Mz8zPzM/Mz8zPzMzMz8zMzM/MzMzPz/zw==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"wall\"\n    },\n    \"tile13\": {\n        \"data\": \"hwQQABAAAAD//////////x/RHbHbu9u9H7u7sd3P/L3fu7u9/c/8v9+7u73/zMz/37u7vczMzMzfu7u9zMzMzN+7u73MzMzM37u7vczMzMzfu7u9zMzMzN+7u73MzMzM37u7vf/MzP/fu7u9/c/8vx+7u7Hdz/y9H9Edsdu7273//////////w==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"stack\"\n    },\n    \"tile11\": {\n        \"data\": \"hwQQABAAAAC7iIiIiIiIiLGIERZmZmZmEYhhEWZmZmYRiGdmZoiIZxGIERFmaGZnEYhnZmZoZmcRiBERZmhmZxGIcWdmaGZnEYgWEWZoZmcRiGZmZmhmZxGIEXFmaGZnEYhhEWZIaGcRiGZmZlSFZxGIERFmVIVmsYhxFmZGaGa7iIiIiIiIiA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"stage\"\n    },\n    \"tile1\": {\n        \"data\": \"hwQQABAAAAC77u7u7u7u7rHuIiIiIiIiEe4SESEiIiIR7hIjIe7uIxHuIiIiLiIjEe4SMyEuIiMR7iIRIi4iIxHuEjMhLiIjEe4iIiIuIiMR7hIRIS4iIxHuIiIiLiIjEe4SIiJOLiMR7hIR4VTlIxHuEiLiVOUise4iIiJOLiK77u7u7u7u7g==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"exit\"\n    },\n    \"tile8\": {\n        \"data\": \"hwQQABAAAAAAALALsAsAAAAA27u7vQAAAAC7HdG9DgAAsB0RsfvrALDbEd0R+78O2xvR3RHr/uu7Hd3d0dvuv7AR3R2x3ev+sBEREbu/3e67vRG96/LS7du9u9svIi/tsPvv3fsi8g4Avu++LS8iDwDg++7d8uIAAAC+797tDgAAAOD77g4AAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true,\n        \"displayName\": \"instrument0\"\n    },\n    \"level1\": {\n        \"id\": \"level1\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTAxMDAwMTAwMDBhMGEwYTBhMGEwYTBhMGEwYTBhMGEwYTBhMGEwYjBiMGEwMDAwMDAwMDAwMDAwYTAwMDAwMDAwMDAwMDAwMGEwOTAwMGIwYjAwMGEwNTBhMDAwYjAwMGEwMDBiMDAwYTBhMDAwYjBiMDAwYTBhMGEwMDBhMDAwYTAwMGEwMDBhMGEwMDAwMDAwYjBhMDMwYTAwMGEwMDBiMDAwYTAwMGEwYTAwMGEwYTBhMGEwMDBiMDAwYTAwMDAwMDBhMDAwYTBhMDAwMDAwMDAwMDAwMDAwMDBhMDMwYTAwMGEwMDBhMGEwMDA3MGEwYTBhMGEwYjAwMGEwYTBhMDAwYTAwMGEwYTAwMDAwMDBhMDAwNDAwMDAwYTA4MGEwMDBhMDAwYTBhMDAwYTBhMGEwMDBhMGEwYTBhMDAwYjAwMGEwMDBhMGEwMDAwMDAwMDAwMGEwMDAwMDAwMDAwMDAwYTAwMGEwYTAwMGIwYTBhMGEwYjBhMGEwYTBhMGEwNjBhMDAwYTBhMDAwMDAwMDAwYzBhMGIwYjBiMDAwMDAwMGEwMDBhMGEwMDBhMGEwYTBhMGEwYTBhMGEwYTBhMGEwYjAwMGIwYTA2MGEwODAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTBhMGEwYTBhMGEwYTBhMGEwYTBhMGEwYTBhMGEwYTAyMjIyMjIyMjIyMjIyMjIyMjAyMDAwMDIwMDAwMDAwMjAwMDIyMjAyMDAwMjAwMDIwMDIyMjIwMjIyMDIwMjAyMDAyMDAyMjIwMjAwMDIwMjAwMjIyMjIwMDIwMDAyMDIwMDIwMDAwMDAyMDIwMjAyMDAyMjAyMjIyMjAyMjIwMjAwMjAwMDIwMjIwMjAyMDIwMDIyMjAyMjIyMjAwMjAyMDAyMDAwMDAyMDAwMDIwMjAwMjIwMjIyMjIyMjIyMDIwMDIwMDAwMDIwMDAwMjAyMDAyMjIyMjIyMjIyMjIyMDAwMjAyMDAwMDAwMDAwMDAwMjIyMjIyMjIyMjIyMjIwMg==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"myTiles.tile1\",\n            \"sprites.castle.tileGrass2\",\n            \"myTiles.tile2\",\n            \"myTiles.tile4\",\n            \"myTiles.tile5\",\n            \"myTiles.tile6\",\n            \"myTiles.tile7\",\n            \"myTiles.tile8\",\n            \"myTiles.tile11\",\n            \"myTiles.tile12\",\n            \"myTiles.tile13\",\n            \"myTiles.tile9\"\n        ],\n        \"displayName\": \"level1\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile4 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile5 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile6 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile7 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile3 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile9 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile10 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile2 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile12 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile13 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile11 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile1 = image.ofBuffer(hex``);\n    //% fixedInstance jres blockIdentity=images._tile\n    export const tile8 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"level1\":\n            case \"level1\":return tiles.createTilemap(hex`100010000a0a0a0a0a0a0a0a0a0a0a0a0a0a0b0b0a0000000000000a000000000000000a09000b0b000a050a000b000a000b000a0a000b0b000a0a0a000a000a000a000a0a0000000b0a030a000a000b000a000a0a000a0a0a0a000b000a0000000a000a0a00000000000000000a030a000a000a0a00070a0a0a0a0b000a0a0a000a000a0a0000000a000400000a080a000a000a0a000a0a0a000a0a0a0a000b000a000a0a00000000000a0000000000000a000a0a000b0a0a0a0b0a0a0a0a0a060a000a0a000000000c0a0b0b0b0000000a000a0a000a0a0a0a0a0a0a0a0a0a0a0b000b0a060a080000000000000000000000010a0a0a0a0a0a0a0a0a0a0a0a0a0a0a02`, img`\n2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 \n2 . . . . . . 2 . . . . . . . 2 \n. . 2 2 . 2 . 2 . . . 2 . . . 2 \n2 . 2 2 . 2 2 2 . 2 . 2 . 2 . 2 \n2 . . . 2 2 . 2 . 2 . . . 2 . 2 \n2 . 2 2 2 2 . . . 2 . . . 2 . 2 \n2 . . . . . . . . 2 . 2 . 2 . 2 \n2 . . 2 2 2 2 2 . 2 2 2 . 2 . 2 \n2 . . . 2 . 2 . . 2 . 2 . 2 . 2 \n2 . 2 2 2 . 2 2 2 2 . . . 2 . 2 \n2 . . . . . 2 . . . . . . 2 . 2 \n2 . . 2 2 2 2 2 2 2 2 2 . 2 . 2 \n2 . . . . . 2 . . . . . . 2 . 2 \n2 . 2 2 2 2 2 2 2 2 2 2 2 2 . . \n2 . 2 . . . . . . . . . . . . . \n2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 . \n`, [myTiles.transparency16,myTiles.tile1,sprites.castle.tileGrass2,myTiles.tile2,myTiles.tile4,myTiles.tile5,myTiles.tile6,myTiles.tile7,myTiles.tile8,myTiles.tile11,myTiles.tile12,myTiles.tile13,myTiles.tile9], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n            case \"instrument3\":\n            case \"tile4\":return tile4;\n            case \"fan1\":\n            case \"tile5\":return tile5;\n            case \"fan2\":\n            case \"tile6\":return tile6;\n            case \"fan3\":\n            case \"tile7\":return tile7;\n            case \"instrument2\":\n            case \"tile3\":return tile3;\n            case \"instrument4\":\n            case \"tile9\":return tile9;\n            case \"camera\":\n            case \"tile10\":return tile10;\n            case \"instrument1\":\n            case \"tile2\":return tile2;\n            case \"wall\":\n            case \"tile12\":return tile12;\n            case \"stack\":\n            case \"tile13\":return tile13;\n            case \"stage\":\n            case \"tile11\":return tile11;\n            case \"exit\":\n            case \"tile1\":return tile1;\n            case \"instrument0\":\n            case \"tile8\":return tile8;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
```
