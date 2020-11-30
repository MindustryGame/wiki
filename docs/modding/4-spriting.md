# Spriting

### Spriting is an essential part of mindustry modding, without it everything you've made in either in JSON, HJSON, or Script won't be visible
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

### Overriding

Overidding existing sprites is possible, for this sprites must be put on `sprites-override/`

## Suffixes
The game also have the capability to look for multiple sprites for a single block.

For turrets, depending on its type, the game could look for the suffix `<name>-heat` and it means that it'll look for `test-turret-heat.png`.

For blocks and crafters/smelters this could include `<name>-top` , `<name>-liquid`, etc. which will be documented in their own section

## Color Pallete

Just like every game out there, Mindustry has its own color palette, it is highly recommended to stick to these colors selection for your sprites or it may look out of place even become heretical and may inflict great disturbance in #spriting channel.

### Blocks
- **Type - 1**
  - ![#B0BAC0](https://via.placeholder.com/15/B0BAC0/000000?text=+) `#B0BAC0` Light
  - ![#989AA4](https://via.placeholder.com/15/989AA4/000000?text=+) `#989AA4` Shading
  - ![#6E7080](https://via.placeholder.com/15/6E7080/000000?text=+) `#6E7080` Dark

- **Type - 2**
  - ![#989AA4](https://via.placeholder.com/15/989AA4/000000?text=+) `#989AA4` Light
  - ![#6E7080](https://via.placeholder.com/15/6E7080/000000?text=+) `#6E7080` Shading
  - ![#4A4B53](https://via.placeholder.com/15/4A4B53/000000?text=+) `#4A4B53` Dark

- **Deep / Bottom** 
  - ![#2F2D39](https://via.placeholder.com/15/2F2D39/000000?text=+) `#2F2D39`
  
### Turrets
- Brown (Low Tier)
  - ![#C9A58F](https://via.placeholder.com/15/C9A58F/000000?text=+) `#C9A58F` Light
  - ![#8F665B](https://via.placeholder.com/15/8F665B/000000?text=+) `#8F665B` Dark
- White (Energy/Power Based Turrets)
  - ![#F4F4F4](https://via.placeholder.com/15/F4F4F4/000000?text=+) `#F4F4F4` Light
  - ![#C1C3D4](https://via.placeholder.com/15/C1C3D4/000000?text=+) `#C1C3D4` Dark
- Dark (High Tier)
  - ![#7B7B7B](https://via.placeholder.com/15/7B7B7B/000000?text=+) `#7B7B7B` Light
  - ![#4D4E58](https://via.placeholder.com/15/4D4E58/000000?text=+) `#4D4E58` Dark
  
[More will be added in the future]
