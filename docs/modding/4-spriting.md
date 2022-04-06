# Spriting

 Spriting is an essential part of mindustry modding, without it everything you've made in JSON, HJSON, Script [JS] or Java won't be visible and would just show "Oh No" error sprite.

It is highly recomended that you have pixel art software that supports transparency.

This includes but not limited to: 

### **Desktop**
  1. **[Aseprite](https://www.aseprite.org/)**
       - The gold standard, has a bit of learning curve, but very simple once you get used to it. 
       - It is a **paid** software, but you can get it for free if you **compile the source code on your own**.
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

Images are packed into an "atlas" for efficient for rendering. The first directory in sprites/, e.g. sprites/blocks, determines the page in this atlas that sprites are put in. Putting a block's sprite in the units page is likely to cause lots of lag; thus, you should try to organize things similarly to how the vanilla game does.
> Anuke

The game will look for sprites relative to its own name. `content/blocks/test-turret.json` has the name `test-turret` and similarly `sprites/test-turret.png` has the name `test-turret`, so it'll be used by this content.

To put this simply, the game will look for 3 kinds of sprites, blocks, units, & items, thus the sprites you've made should be placed into their own subfolder.
- Blocks should be stored in `sprites/blocks`
- Units should be stored in `sprites/units`
- Items should be stored in `sprites/items`

Some sprites will be slightly modified by the game. Both turrets and units will have a black border added to them, so you must account for that while making your sprites, leaving empty space around turrets.

Same thing applies with overriding sprites.

### Overriding

Overidding existing sprites is possible, for this sprites must be placed at `sprites-override/`

## Suffixes
The game also have the capability to look for multiple sprites for a single block.

For turrets, depending on its type, the game could look for the suffix `<name>-heat` and it means that it'll look for `test-turret-heat.png`.

For blocks and crafters/smelters this could include `<name>-top`, `<name>-liquid`, etc. which will be documented in their own section.

For more details, you can read the source code for each respective block class for what sprite that they can load. Usually located in `load()` method within the class.

## Color Pallete

Just like every game out there, Mindustry has its own color palette. For beginners, it is highly recommended to stick to these colors selection for your sprites or it may look out of place even become heretical and may inflict great disturbance upon the #spriting discord channel.

You can get it here: 

<img src="/wiki/images/spriting/pal-mindustry.png">



