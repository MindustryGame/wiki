# Spriting

Spriting is an essential part of Mindustry modding, without it anything you've made would just shows up as an "oh no" image.

Spriting style in Mindustry is very simple yet very strict and restrictive, what you can get away with other games would look out of place in Mindustry.

You can find all the vanilla sprites [here](https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites).

## Spriting Software

It is highly recommended that you use spriting software that supports transparency and exporting image in `.PNG` format. Below there's recommendation for such.

### **Desktop**
  1. **[Aseprite](https://www.aseprite.org/)**
       - The gold standard, has a bit of learning curve, but very simple once you get used to it. 
       - It is a **paid** software, but you can get it for free if you **[compile the source code on your own](https://github.com/aseprite/aseprite/blob/main/INSTALL.md#compiling)**.
       - Has many feature useful for mindustry spriting such as:
         - Mirroring
         - Pallete Control
         - Animation
         - Layering (Can also export individual layer)
  
  2. **[LibreSprite](https://libresprite.github.io/#!/)**
      - A copy of the Aseprite respository, not as up to date or as powerful as the original one, though you wouldn't need it for spriting in mindustry style anyway.
  
  3. **[Piskel](https://www.piskelapp.com/)**
      - A very simple pixel art software, not as powerful as Aseprite or LibreSprite, but it is sufficient enough. There's the online version & an offline downloadable version. Both version has the same feature.
      - Lacks the ability to export individual layer

  4. **[Paint.NET](https://www.getpaint.net/)**
      - Very basic painting software, not to be confused with Paint 3D, `Paint.NET` is a usable but not as convinient as the above mentioned.
      - `Paint.NET` lacks basic feature used for spriting in mindustry style, though some of these missing features you can get them with the use of plugins that you can install manually.
      - That said, it is not recommended to use this for the sake of convinience, if you can download `Paint.NET` pretty darn sure you can download Piskel and LibreSprite that is a specialized Pixel Art software.

### **Mobile**
// TODO


## Size
The smallest block size you could make is `32px × 32px` size, which is a 1×1 block, making bigger block means increasing the sprite size by additional `32px`, so a 2×2 block is `64×64` and so on, this applies to both turrets and blocks.
- `1×1` : `32px × 32px`
- `2×2` : `64px × 64px`
- `3×3` : `96px × 96px`
- `4×4` : `128px × 128px`
- `5×5` : `160px × 160px`

However you are not limited to those options, the game will still load sprites bigger or smaller than the block you've assigned it for, which can result in a unique looking sprite or an atrocity.

## Storing Sprites
Sprites can simply be dropped in the `sprites/` subdirectory. The content parser will look through it recursively. 

Images are packed into an "atlas" for efficient for rendering. The first directory in sprites/, e.g. `sprites/blocks`, determines the page in this atlas that sprites are put in. Putting a block's sprite in the units page is likely to cause lots of lag; thus, you should try to organize things similarly to how the vanilla game does.
> Anuke

The game will look for sprites relative to its own name. `content/blocks/test-turret.json` has the name `test-turret` and similarly `sprites/test-turret.png` has the name `test-turret`, so it'll be used by this content.

To put this simply, the game will look for 3 kinds of sprites, blocks, units, & items, thus the sprites you've made should be placed into their own subfolder.
- Blocks should be stored in `sprites/blocks`
- Units should be stored in `sprites/units`
- Items should be stored in `sprites/items`

Some sprites will be slightly modified by the game. Both turrets and units will have a black border added to them, so you must account for that while making your sprites, leaving empty space around turrets.

Same thing applies with overriding sprites.

### Overriding

Overidding existing sprites is possible, for this, sprites must be placed at `sprites-override/`

## Suffixes
The game also have the capability to look for multiple sprites for a single block.

For turrets, depending on its type, the game could look for the suffix `<name>-heat` and it means that it'll look for `test-turret-heat.png`.

For blocks and crafters/smelters this could include `<name>-top`, `<name>-liquid`, etc. which will be documented in their own section.

For more details, you can read the source code for each respective block class for what sprite that they can load. Usually located in `load()` method within the class.

## Color Pallete

Just like every game out there, Mindustry has its own color palette. For beginners, it is highly recommended to stick to these colors selection for your sprites or it may look out of place even become heretical and may inflict great disturbance upon the #spriting discord channel.

Block Color Pallete:

<img src="/wiki/images/spriting/pal-mindustry.png">

Environment Color Pallete

<img src="/wiki/images/spriting/pal-mindustry-evn.png">

Assuming you have properly acquired a proper spriting software, just download that image and use it as a pallete.

## Style
Mindustry has simple yet strict art style, what may works for other game, would just looks out of place in Mindustry due to this nature, and for that reason rules and guidelines has been established to help modder to sprite in a way that the result will fit inside the game.

### Shading
Mindustry is a 2D game, so to add depth such as elevation and depression we need to do a trick called 'Shading', despite the actual asset is a 2D image, make it such a way that it would look 3D in-game.

Depending on where the light is shined, **elevations** are marked with **lighter tone**, **flat area** with the **mid-tone**, **depression** with the **darker tone**, picture something in its 3D form, and then draw it in 2D is usually a general way to sprite something in Mindustry


**1. Blocks Shading**

![Surge Smelter](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/alloy-smelter.png)

We will use the Surge Smelter as an example in this part. 

With blocks, lights came from **top right corner** to bottom left corner. So, the closer it is to the light source, the lighter the tone will be and with a diagonal mid-tone seperating it.

Smelter in general has 3 types of color type, in this case 
  - Base Color, which have 3 tone: 
	- ![](https://via.placeholder.com/15/B0BAC0/000000?text=+) `B0BAC0` 
	- ![](https://via.placeholder.com/15/989AA4/000000?text=+) `989AA4` 
	- ![](https://via.placeholder.com/15/6E7080/000000?text=+) `6E7080` 
  - Decal Color, which also have 3 tone:
	- ![](https://via.placeholder.com/15/feb380/000000?text=+) `FEB380` 
	- ![](https://via.placeholder.com/15/ea8878/000000?text=+) `EA8878` 
	- ![](https://via.placeholder.com/15/bc5452/000000?text=+) `BC5452` 
  - Bottom Color
	- ![](https://via.placeholder.com/15/4a4b53/000000?text=+) `4a4b53` 

**Base Color** represents the main color of the block, this color is usually limited to light gray and dark gray. This will look the same across all blocks. 

**Decal Color** represents the blocks **role** or **purpose**, and a way to differentiate it with each others. To pick what decal color to use for your own blocks, you should think about what purpose does your block has. For example:

**Pastanium Compressor**

![Plast-Comp](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/plastanium-compressor.png) 

Plastanium Compressor has a green decal, this green decal is the exact same as the plastanium, and thus you can get the general idea that this block has a connection around plastanium.

**Bottom Color** represents the insides of the block, the insides are not usually gets shined by the lights, so a dark color is chosen here. This could be used to represents the bottom of a block that has a chimney, like Surge Smelter for example.

**2. Turret Shading**

With Turret shading, lights came from the **right side** of the turret. 

![ripple](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/ripple.png?raw=true)

We will use the '**Ripple**' as an example for this part.

Turrets in general has 2 to 3 color type with 2 tone for each:
- Base Color
  - ![](https://via.placeholder.com/15/7b7b7b/000000?text=+) `7B7B7B` 
  - ![](https://via.placeholder.com/15/4d4e58/000000?text=+) `4D4E58` 
- Decal Color
  - ![](https://via.placeholder.com/15/feb380/000000?text=+) `FEB380` 
  - ![](https://via.placeholder.com/15/ea8878/000000?text=+) `EA8878` 
- [Optional] Barrel Hole Color
  - ![](https://via.placeholder.com/15/2c2d38/000000?text=+) `2C2D38` 

**Base Color** or Body Color, self explanatory, it is the main color of the turret. This can range from the classic copper brown, white, or dark grey.
  - Copper Brown
    - ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/duo.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/scorch.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/hail.png?raw=true)
    - Usually represents low tiered turret, such as **Duo**, **Scorch**, **Hail**, etc.	
      - ![](https://via.placeholder.com/15/c9a58f/000000?text=+) `C9A58F` 
      - ![](https://via.placeholder.com/15/8f665b/000000?text=+) `8F665B` 
  - White
    - ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/arc.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/lancer.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/defense/parallax.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/defense/segment.png?raw=true)
    - Usually represents turret that uses power instead of items to shoot, such as **Arc**, **Lancer**, **Paralax**, **Segment**.
      - ![](https://via.placeholder.com/15/f4f4f4/000000?text=+) `F4F4F4` 
      - ![](https://via.placeholder.com/15/c1c3d4/000000?text=+) `C1C3D4`
  - Dark Gray
    -  ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/swarmer.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/cyclone.png?raw=true) ![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/meltdown.png?raw=true)
    - In most cases, dark gray represents mid to high tiered turret.
      - ![](https://via.placeholder.com/15/7b7b7b/000000?text=+) `7B7B7B` 
      - ![](https://via.placeholder.com/15/4d4e58/000000?text=+) `4D4E58` 

**Barrel Hole** is an optional detail for turrets that represents the barrel hole of your turret, this is usually are used for artillery turrets or missile launchers. This mostly are optional.

![](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/swarmer.png?raw=true) ![ripple](https://github.com/Anuken/Mindustry/blob/master/core/assets-raw/sprites/blocks/turrets/ripple.png?raw=true)

  - ![](https://via.placeholder.com/15/2c2d38/000000?text=+) `2C2D38` 