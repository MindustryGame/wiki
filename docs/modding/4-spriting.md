# Spriting

### Spriting is an essential part of mindustry modding, without it everything you've made in either in JSON or Script won't be visible
It is highly recomended that you have an image editting software that supports transparency.

This includes but not limited to : 
  - Aseprite 
  - Piskel
  - GIMP
  - Paint 3D

## Size
The smallest block size you could make is `32×32` size , which is a 1×1 block, making bigger block means increasing the sprite size by additional `32` , so a 2×2 block is `64×64` and so on, this applies to both turrets and blocks.
- `1×1` : `32×32`
- `2×2` : `64×64`
- `3×3` : `96×96`
- `4×4` : `128×128`
- `5×5` : `160×160`

However you are not limited to those options, the game will still load sprites bigger or smaller than the block you've assigned, which can result in a unique looking sprite or a complete heresy.

## Storing Sprites
Sprites can simply be dropped in the `sprites/` subdirectory. The content parser will look through it recursively, so you can organize them how ever you feel. 

The game will look for sprites relative to it's own name. `content/blocks/test-turret.json` has the name `test-turret` and similarly `sprites/test-turret.png` has the name `test turret`, so it'll be used by this content.

Some sprites will be slightly modified by the game. Both turrets and unit will have a black border added to them, so you must account for that while making your sprites, leaving transparent space around turrets

## Suffixes
The game also have the capability to look for multiple sprites for a single block.

For turrets, depending on its type, the game could look for the suffix `<name>-heat` and it means that it'll look for `test-turret-heat.png`.

For blocks and crafters/smelters this could include `<name>-top` , `<name>-liquid`, etc. which will be documented in their own section

