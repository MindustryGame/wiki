# Spriting

Spriting is an essential part of Mindustry modding, without it anything you've made would just show up as an "oh no" image.

The spriting style in Mindustry is very simple yet very strict and restrictive, what you can get away with in other games would look out of place in Mindustry.

You can find all the vanilla sprites [here](https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites).

## **Spriting Software**
It is highly recommended that you use spriting software that supports transparency and exporting images in `.PNG` format. Below there's the recommendation for such.

### **Desktop**
  1. **[Aseprite](https://www.aseprite.org/)**
       - The gold standard, has a bit of a learning curve, but very simple once you get used to it. 
       - It is a **paid** software, but you can get it for free if you **[compile the source code on your own](https://github.com/aseprite/aseprite/blob/main/INSTALL.md#compiling)**.
       - Has many features useful for mindustry spriting such as:
         - Mirroring
         - Pallete Control
         - Animation
         - Layering (Can also export individual layers)
  
  2. **[LibreSprite](https://libresprite.github.io/#!/)**
      - A copy of the Aseprite repository, not as up-to-date or as powerful as the original one, though you wouldn't need it for spriting in mindustry style anyway.
  
  3. **[Piskel](https://www.piskelapp.com/)**
      - A very simple pixel art software, not as powerful as Aseprite or LibreSprite, but it is sufficient enough. There's the online version & an offline downloadable version. Both versions have the same feature.
      - Cannot export individual layer

  4. **[Paint.NET](https://www.getpaint.net/)**
      - Very basic painting software, not to be confused with Paint 3D, `Paint.NET` is usable but not as convenient as the above mentioned.
      - `Paint.NET` lacks basic features used for spriting in mindustry style, though some of these missing features you can get with the use of plugins that you can install manually.
      - That said, it is not recommended to use this for the sake of convenience, if you can download `Paint.NET` pretty darn sure you can download Piskel and LibreSprite which is a specialized Pixel Art software.

### **Mobile**
// TODO


## **Size**
### Blocks 
The smallest block size you could make is `32px × 32px` size, which is a 1×1 block, making bigger block means increasing the sprite size by additional `32px`, so a 2×2 block is `64 × 64` and so on, this applies to both turrets and blocks.
- `1×1` : `32px × 32px`
- `2×2` : `64px × 64px`
- `3×3` : `96px × 96px`
- `4×4` : `128px × 128px`
- `5×5` : `160px × 160px`

However you are not limited to those options, the game will still load sprites bigger or smaller than the block you've assigned it for, which can result in a unique-looking sprite or an atrocity.

### Items, Liquid, Statuses
For these content types, the minimum sprite size is `32px`, you can make a bigger one though the game will just squish it down to `32px`, unfortunately, the game won't enlarge the smaller one, so `32px` is the minimum.

### Units
Unit sprite sizes are more lenient, though try to not go below `48px`. Though the bigger your units are, the more you will have to adjust their `hitSize`.

## **Storing Sprites**
Sprites can simply be dropped in the `sprites/` subdirectory. The content parser will look through it recursively. 

Images are packed into an "atlas" for efficient rendering. The first directory in sprites/, e.g. `sprites/blocks`, determines the page in this atlas that sprites are put in. Putting a block's sprite in the units page is likely to cause lots of lag; thus, you should try to organize things similarly to how the vanilla game does.
> Anuke

The game will look for sprites relative to its name. `content/blocks/test-turret.json` has the name `test-turret` and similarly `sprites/test-turret.png` has the name `test-turret`, so it'll be used by this content.

To put this simply, the game will look for 3 kinds of sprites, blocks, units, & items, thus the sprites you've made should be placed into their subfolder.
- Blocks should be stored in `sprites/blocks`
- Units should be stored in `sprites/units`
- Items should be stored in `sprites/items`

Some sprites will be slightly modified by the game. Both turrets and units will have a black border added to them, so you must account for that while making your sprites, leaving space around turrets.

The same thing applies to overriding sprites.

### Overriding

Overriding existing sprites is possible, for this, sprites must be placed at `sprites-override/`

## **Suffixes**
The game also can look for multiple sprites for a single block.

For turrets, depending on their type, the game could look for the suffix `<name>-heat` and it means that it'll look for `test-turret-heat.png`.

For blocks and crafters/smelters this could include `<name>-top`, `<name>-liquid`, etc. which will be documented in their section.

For more details, you can read the source code for each respective block class for what sprite they can load. Usually located in `load()` method within the class.

## **Color Pallete**

Just like every game out there, Mindustry has its own color palette. For beginners, it is highly recommended to stick to these colors selection for your sprites or it may look out of place even become heretical, and may inflict great disturbance upon the #spriting discord channel.

Block Color Pallete:

![](/docs/images/modding/spriting/pal-mindustry.png)

Environment Color Pallete

![](/docs/images/modding/spriting/pal-mindustry-evn.png)

Assuming you have properly acquired proper spriting software, just download that image and use it as a color pallete.

## **Styles and Shading**

Mindustry has a simple yet strict art style, which may work for other games, would just look out of place in Mindustry due to this nature, and for that reason, rules and guidelines have been established to help modder to sprite in a way that the result will fit inside the game.

Mindustry is a 2D game, so to add depth such as elevation and depression we need to do a trick called 'Shading', despite the actual asset being a 2D image, make it such a way that it would look 3D in-game.

Depending on where the light is shined, **elevations** are marked with **lighter tone**, **flat area** with the **midtone**, **depression** with the **darker tone**, picture something in its 3D form, and then draw it in 2D is usually a general way to sprite something in Mindustry

Keep in mind, that this is mostly a guideline, you can bend this guideline however you'd like, but please try to understand the basics first and gain decent experience before you do that.

### Blocks Shading
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/alloy-smelter.png)

We will use the Surge Smelter as an example in this part. 

With blocks, lights came from **top right corner** to the bottom left corner. So, the closer it is to the light source, the lighter the tone will be and with a diagonal midtone separating it.

Smelter in general has 3 types of color type, in this case 
  - Base Color, which have 3 tone: 
  - ![](https://via.placeholder.com/15/B0BAC0/000000?text=+) `B0BAC0` | Light Tone
  - ![](https://via.placeholder.com/15/989AA4/000000?text=+) `989AA4` | Midtone
  - ![](https://via.placeholder.com/15/6E7080/000000?text=+) `6E7080` | Dark Tone
  - Decal Color, which also have 3 tone:
  - ![](https://via.placeholder.com/15/feb380/000000?text=+) `FEB380` | Lght Tone 
  - ![](https://via.placeholder.com/15/ea8878/000000?text=+) `EA8878` | Midtone 
  - ![](https://via.placeholder.com/15/bc5452/000000?text=+) `BC5452` | Dark Tone 
  - Bottom Color
  - ![](https://via.placeholder.com/15/4a4b53/000000?text=+) `4a4b53` 

**Base Color** represents the main color of the block, this color is usually limited to light gray and dark gray. This will look the same across all blocks. 

**Decal Color** represents the blocks **role** or **purpose**, and a way to differentiate them from each other. To pick what decal color to use for your blocks, you should think about what purpose your block has. For example:

**Pastanium Compressor**

![Plast-Comp](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/plastanium-compressor.png) 

Plastanium Compressor has a green decal, this green decal is the same as the plastanium, and thus you can get the general idea that this block has a connection around plastanium.

**Bottom Color** represents the insides of the block, the insides are not usually gets shined by the lights, so a dark color is chosen here. This could be used to represent the bottom of a block that has a chimney, like Surge Smelter for example.

### Turret Shading

With Turret shading, lights came from the **right to left** of the turret. 

![ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

We will use the '**Ripple**' as an example for this part.

Turrets in general has 2 to 3 color type with 2 tone for each:
- Base Color
  - ![](https://via.placeholder.com/15/7b7b7b/000000?text=+) `7B7B7B` | Light Tone 
  - ![](https://via.placeholder.com/15/4d4e58/000000?text=+) `4D4E58` | Dark Tone 
- Decal Color
  - ![](https://via.placeholder.com/15/feb380/000000?text=+) `FEB380` | Light Tone 
  - ![](https://via.placeholder.com/15/ea8878/000000?text=+) `EA8878` | Dark Tone 
- [Optional] Barrel Hole Color
  - ![](https://via.placeholder.com/15/2c2d38/000000?text=+) `2C2D38` 

**Base Color** or Body-Color, is the main color of the turret. This can range from classic copper brown, white, or dark grey.
  - Copper Brown
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/duo.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/scorch.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/hail.png)
    - Usually represents low tiered turret, such as **Duo**, **Scorch**, **Hail**, etc. 
      - ![](https://via.placeholder.com/15/c9a58f/000000?text=+) `C9A58F` 
      - ![](https://via.placeholder.com/15/8f665b/000000?text=+) `8F665B` 
  - White
    - ![Arc](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/arc.png) ![Lancer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/lancer.png) ![Parallax](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/defense/parallax.png) ![Segment](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/defense/segment.png)
    - Usually represents turret that uses power instead of items to shoot, such as **Arc**, **Lancer**, **Paralax**, **Segment**.
      - ![](https://via.placeholder.com/15/f4f4f4/000000?text=+) `F4F4F4` 
      - ![](https://via.placeholder.com/15/c1c3d4/000000?text=+) `C1C3D4`
  - Dark Gray
    -  ![Swarmer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/swarmer.png) ![Cyclone](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/cyclone.png) ![Meltdown](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/meltdown.png)
    - In most cases, dark gray represents mid to high tiered turret.
      - ![](https://via.placeholder.com/15/7b7b7b/000000?text=+) `7B7B7B` 
      - ![](https://via.placeholder.com/15/4d4e58/000000?text=+) `4D4E58` 

**Decals Color** in the turret is similar to what a decal is to a regular block, it represents the turret role, purpose, or archetype.

**Barrel Hole** is an optional detail for turrets that represents the barrel hole of your turret, this is usually used for artillery turrets or missile launchers.

![Swarmer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/swarmer.png) 
![Ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

  - ![](https://via.placeholder.com/15/2c2d38/000000?text=+) `2C2D38` 

  #### Unconventional Methods
  - **Turret Midtone**
       - Still a relatively new unconditional method is adding Midtones into turret to make it seemingly has a flat surface instead of only light and dark tone
       - One of example is the "Skyhammer" from [Unlimited Armament Works](https://github.com/Eschatologue/Unlimited-Armament-Works)
         - ![](https://raw.githubusercontent.com/Eschatologue/Unlimited-Armament-Works/master/assets/sprites/blocks/turrets/ART/skyhammer.png)

### Resources Shading
Resource shading is quite simple, and can have its light coming from **top corners**, **top to down**, or **right to left**.

For color tones, it should have either 3 or 2 and don't make the sprite looks 2D

Examples:

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-copper.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-plastanium.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-graphite.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-coal.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-surge-alloy.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-scrap.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-pyratite.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-cryofluid.png)

### Unit Shading
Now we arrived at the tricky part of shadings. 

Unit shading can be fairly complex the bigger your units are. In unit shading, lights came from the **top to bottom** or **front to back**. The intensity of lighter tone and darker tone are changing depending on what part you're working with on the unit.

As mentioned above, Light tone represents **elevation**, midtone represents **flat area**, dark tone represents **depression**.

#### **Unit Base Color**

![](/docs/images/modding/spriting/spriting-unit-shading.png)

Please take a look at the image above, we use **Eclipse** for this example. As you continuously work towards the backside, there will be less light tone and more midtone and dark tone.

Parts that get lit by the lights will have a lighter tone, while the ones that are not getting darker tone, flat areas are midtone.

![](/docs/images/modding/spriting/spriting-unit-shading-illustration.png)

Above are the rough illustration of units if imagined in 3D.

- Base Color, has 3 tone: 
  - ![](https://via.placeholder.com/15/B0BAC0/000000?text=+) `B0BAC0` | Light Tone
  - ![](https://via.placeholder.com/15/989AA4/000000?text=+) `989AA4` | Midtone
  - ![](https://via.placeholder.com/15/6E7080/000000?text=+) `6E7080` | Dark Tone

#### **Unit Decal Color**

Unit decal color only consisted of 2 tones, which are light tone and dark tone. They represent the unit's role in-game.
 
- Yellow Color, represents **Core** units, which are produced by the Core.
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/gamma.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/beta.png)
    - ![](https://via.placeholder.com/15/ffd37f/000000?text=+) `FFD37F` | Light Tone 
    - ![](https://via.placeholder.com/15/d4816b/000000?text=+) `D4816B` | Dark Tone 

- Orange Color, represents **Assault** units, which have the role of attacking your opponents.
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/horizon.png)
    - ![](https://via.placeholder.com/15/ffa665/000000?text=+) `FFA665` | Light Tone 
    - ![](https://via.placeholder.com/15/d06b53/000000?text=+) `D06B53` | Dark Tone 

- Green Color, represents **Support** units. Units that can build, heal, shield your units, etc.
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/poly.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/retusa.png)
    - ![](https://via.placeholder.com/15/84f491/000000?text=+) `84F491` | Light Tone 
    - ![](https://via.placeholder.com/15/62ae7f/000000?text=+) `62AE7F` | Dark Tone 

- Purple Color, represents **Specialist** units. Units that have very unique characteristics, and can't be put into the same category as the above.
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/crawler.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/arkyid.png)
    - ![](https://via.placeholder.com/15/bf92f9/000000?text=+) `BF92F9` | Light Tone 
    - ![](https://via.placeholder.com/15/665c9f/000000?text=+) `665C9F` | Dark Tone 

#### **Unit Cell/Team Color**
Unit Cells are sprites that are used to differentiate units between teams, they're separate sprites that will be loaded on top of the unit.

![](/docs/images/modding/spriting/spriting-unit-cell.png)

The Cells are automatically colored depending on what team the units are in.

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress-cell.png)

Above is a fortress with its cell. The cell sprite color should be white and have 2 tones.
  - ![](https://via.placeholder.com/15/ffffff/000000?text=+) `FFFFFF` | Light Tone 
  - ![](https://via.placeholder.com/15/dcc6c6/000000?text=+) `DCC6C6` | Dark Tone 

This is why spriting software that is capable of using layers and exporting them separately is highly recommended. Because you can sprite the unit itself and the cell on a separate layer within 1 file.

#### **Unit Weapons**
Unit Weapons can follow the same rule as both turrets and unit shading, they can be shaded from **top to bottom** or **right to left**.

 ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/large-artillery.png) 
 ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/large-laser-mount.png)

 Weapons rotation are based on the center of the sprite, if you wan't to shift the weapon rotation point, shift the sprite.

### Unit Spriting Stages

![](/docs/images/modding/spriting/spriting-unit-stepbystep.png)
 
The process of drawing units can be roughly divided in 5 stages:

1. Here you just want to scribble down the general shape. Pick a thick brush with dark tone and paint it, slowly adding lines over each other and forming basic shapes without much precision. Try to make them slightly deformed or curved, and make sure the shape looks nice - you cant make a good sprite out of a bad shape in most cases, so make sure you are satisfied before you move on.

2. Refine the shape and transform it in a way where lines are incremental of 45 degrees. You may want to tweak some of them, and dont try to follow the doodle you already made too closely.

3. Add decals. This is a tricky one because decals are hard to get right, I showed 3 examples of what kind work - you should experiment for yourself, however, and see what works best for you. The reason why its better to add them now is because later you will be able to "build shades" around decals, making it easier to proceed at stage 5. 

4. Roughly mark the lighter and darker parts. Since the light comes from top, you can and should help yourself and mark what shapes do you want to be illuminated the least or the most right away to spare yourself from thinking too much about it. Refrain from covering too much space because around 30-40% of the sprite should be the dark shade. Also note that you should leave the area around decals dark to increase the contrast and make it more appealing to look at.

5. By far the hardest part - "add details". There arent many tricks you can use, you just get good at this. However, there is one i use: when uncertain what should you add, add cells there. They can work like extra decals and you may want to build your shapes around them. Refrain from adding too many details, and use any convinient corner or slab to carve a new shape out of it.

> written by Zhenьkotron #9493, proofread by Geschiedenis #4783