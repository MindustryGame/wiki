# Spriting

### Spriting is an essential part of mindustry modding, without it everything you've made in JSON, HJSON, or Script [JS] won't be visible
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

However you are not limited to those options, the game will still load sprites bigger or smaller than the block you've assigned it for, which can result in a unique looking sprite or an atrocity.

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
- **Type 1** : 
  - ![#B0BAC0](https://via.placeholder.com/15/B0BAC0/000000?text=+) `#B0BAC0` Light | ![#989AA4](https://via.placeholder.com/15/989AA4/000000?text=+) `#989AA4` Shading | ![#6E7080](https://via.placeholder.com/15/6E7080/000000?text=+) `#6E7080` Dark
- **Type 2** : 
  - ![#989AA4](https://via.placeholder.com/15/989AA4/000000?text=+) `#989AA4` Light | ![#6E7080](https://via.placeholder.com/15/6E7080/000000?text=+) `#6E7080` Shading | ![#4A4B53](https://via.placeholder.com/15/4A4B53/000000?text=+) `#4A4B53` Dark
- **Deep / Bottom** : 
  - ![#2F2D39](https://via.placeholder.com/15/2F2D39/000000?text=+) `#2F2D39`
  
### Turrets
- **Brown** : 
  - ![#C9A58F](https://via.placeholder.com/15/C9A58F/000000?text=+) `#C9A58F` Light | ![#8F665B](https://via.placeholder.com/15/8F665B/000000?text=+) `#8F665B` Dark
- **White** : 
  - ![#F4F4F4](https://via.placeholder.com/15/F4F4F4/000000?text=+) `#F4F4F4` Light | ![#C1C3D4](https://via.placeholder.com/15/C1C3D4/000000?text=+) `#C1C3D4` Dark
- **Dark**  : 
  - ![#7B7B7B](https://via.placeholder.com/15/7B7B7B/000000?text=+) `#7B7B7B` Light | ![#4D4E58](https://via.placeholder.com/15/4D4E58/000000?text=+) `#4D4E58` Dark
 
### Decals
- Blue
  - ![#C0ECFF](https://via.placeholder.com/15/C0ECFF/000000?text=+) `#C0ECFF` Light | ![#87CEEB](https://via.placeholder.com/15/87CEEB/000000?text=+) `#87CEEB` Medium | 
 ![#6586B0](https://via.placeholder.com/15/6586B0/000000?text=+) `#6586B0` Dark
  - ![#87A3FF](https://via.placeholder.com/15/87A3FF/000000?text=+) `#87A3FF` Light | ![#6F7FE8](https://via.placeholder.com/15/6F7FE8/000000?text=+) `#6F7FE8` Medium | 
 ![#5757C2](https://via.placeholder.com/15/5757C2/000000?text=+) `#5757C2` Dark
  - ![#A4B8FA](https://via.placeholder.com/15/A4B8FA/000000?text=+) `#A4B8FA` Light | ![#919FE7](https://via.placeholder.com/15/919FE7/000000?text=+) `#919FE7` Medium | ![#7575C8](https://via.placeholder.com/15/7575C8/000000?text=+) `#7575C8` Dark
- Gray
  - ![#646567](https://via.placeholder.com/15/646567/000000?text=+) `#646567` Light | ![#515151](https://via.placeholder.com/15/515151/000000?text=+) `#515151` Medium | 
 ![#3C3837](https://via.placeholder.com/15/3C3837/000000?text=+) `#3C3837` Dark
- Green
  - ![#EDF3A9](https://via.placeholder.com/15/EDF3A9/000000?text=+) `#EDF3A9` Light | ![#CBD97F](https://via.placeholder.com/15/CBD97F/000000?text=+) `#CBD97F` Medium | 
 ![#9CB664](https://via.placeholder.com/15/9CB664/000000?text=+) `#9CB664` Dark
  - ![#84F491](https://via.placeholder.com/15/84F491/000000?text=+) `#84F491` Light | ![#7BD69D](https://via.placeholder.com/15/7BD69D/000000?text=+) `#7BD69D` Medium | 
 ![#62AE7F](https://via.placeholder.com/15/62AE7F/000000?text=+) `#62AE7F` Dark
- Orange | Red
  - ![#FEB380](https://via.placeholder.com/15/FEB380/000000?text=+) `#FEB380` Light | ![#EA8878](https://via.placeholder.com/15/EA8878/000000?text=+) `#EA8878` Medium | 
 ![#BC5452](https://via.placeholder.com/15/BC5452/000000?text=+) `#BC5452` Dark
  - ![#FFF3D6](https://via.placeholder.com/15/FFF3D6/000000?text=+) `#FFF3D6` Light | ![#FFD59E](https://via.placeholder.com/15/FFD59E/000000?text=+) `#FFD59E` Medium | 
 ![#F19583](https://via.placeholder.com/15/F19583/000000?text=+) `#F19583` Dark
- Purple
  - ![#AB99D3](https://via.placeholder.com/15/AB99D3/000000?text=+) `#AB99D3` Light | ![#8C7FA9](https://via.placeholder.com/15/8C7FA9/000000?text=+) `#8C7FA9` Medium | 
 ![#6F687E](https://via.placeholder.com/15/6F687E/000000?text=+) `#6F687E` Dark 
  - ![#BF92F9](https://via.placeholder.com/15/BF92F9/000000?text=+) `#BF92F9` Light | ![#8A73C6](https://via.placeholder.com/15/8A73C6/000000?text=+) `#8A73C6` Medium | 
 ![#665C9F](https://via.placeholder.com/15/665C9F/000000?text=+) `#665C9F` Dark
- White
  - ![#FFFFFF](https://via.placeholder.com/15/FFFFFF/000000?text=+) `#FFFFFF` Light | ![#EBEEF5](https://via.placeholder.com/15/EBEEF5/000000?text=+) `#EBEEF5` Medium | 
 ![#D0D0E0](https://via.placeholder.com/15/D0D0E0/000000?text=+) `#D0D0E0` Dark
- Yellow
  - ![#F3E979](https://via.placeholder.com/15/F3E979/000000?text=+) `#F3E979` Light | ![#E8D174](https://via.placeholder.com/15/E8D174/000000?text=+) `#E8D174` Medium | 
 ![#D99F6B](https://via.placeholder.com/15/D99F6B/000000?text=+) `#D99F6B` Dark
