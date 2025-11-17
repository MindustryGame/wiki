# Spriting

Spriting is an essential part of Mindustry modding; anything you have made will appear as poorly scaled "oh no" images without it.

The spriting style in Mindustry is simple yet very restrictive; what you can get away with in other games looks out of place in Mindustry.

You can find all the vanilla sprites [here](https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites).

**Please note that using other modders' sprites without their permission is not allowed, although you may use them for inspiration or reference.**

**Reasoning such as "The mod is open-source, I can do whatever I want with it," or something similar will not be acknowledged or tolerated and your mod will be blacklisted from the mod browser.**

## **Spriting Software**
It is highly recommended that you use spriting software that supports transparency and exporting images in `.PNG` format. Below is a list of recommended software.

### **Desktop**

  1. **[Aseprite](https://www.aseprite.org/)**
    - The gold standard. Has a bit of a learning curve, but it is very simple once you get used to it. 
    - It is **paid** software, but you can **[compile the source code on your own](https://github.com/aseprite/aseprite/blob/main/INSTALL.md#compiling)**. Please buy a license to support its developers.
      - Has many features useful for Mindustry spriting such as:
         - Mirroring
         - Pallete Control
         - Animation
         - Layering (Can also export individual layers)
  
  2. **[LibreSprite](https://libresprite.github.io/#!/)**
      - A fork of the Aseprite repository, not as up-to-date or as powerful as Aseprite, but it should work for spriting in Mindustry style.
  
  3. **[Piskel](https://www.piskelapp.com/)**
      - A straightforward pixel art software that is not as powerful as Aseprite or LibreSprite, but it is sufficient. There is an online version & an offline downloadable version, both with the same features.
      - Cannot export individual layers

  4. **[Pixilart](https://www.pixilart.com/)**
      - An online spriting tool that has more features than Piskel though it lacks a mirror tool. If you're more familiar with pixilart, use this over piskel.
      - Pretty bloated for spriting in Mindustry style.

  5. **[Paint.NET](https://www.getpaint.net/)**
      - Very basic painting software, not to be confused with Paint 3D, Paint&#46;NET is usable but not as convenient as the above mentioned.
      - Paint&#46;NET lacks basic features needed for spriting in mindustry style. You can get some of these missing features with plugins.
      - That said, it is not recommended to use this for the sake of convenience. If you can download Paint&#46;NET, you can probably download Piskel or LibreSprite instead, which are meant for pixel art.

### **Mobile**
1. **[Novix Pixel Editor](https://play.google.com/store/apps/details?id=io.anuke.novix)**
     - Old and reliable, made and abandoned by Anuke, it is simple, has no ads, though a bit old, it is still reliable as a spriting tool for mobile users, also supports the mirror tool.
     - Occasionally breaks if spriting a larger sprite.
  
2.  **[Pixel Studio](https://play.google.com/store/apps/details?id=com.PixelStudio)**
    - One of the most popular pixel art software.
    - Has most of the features you need and it can also link with its PC version.
    - Has ads

3. **[Ibispaint X](https://play.google.com/store/apps/details?id=jp.ne.ibis.ibispaintx.app)**
    - Not meant for spriting, and requires some setting changes before use.
    - Supports various tools like octal mirrors, bloom, and gradients, as well as fundamental features like region select and layers.
    - Can be used to sprite complex sprites with ease, but could be bloated for simple sprites. 
    - Also has ads

## **Size**
### Blocks 
The smallest block sprite you can make is `32px × 32px`, which is a 1×1 block. Making bigger blocks means increasing the sprite size by an additional `32px`, so a 2×2 block is `64 × 64`, and so on. This applies to both turrets and blocks.

- `1×1` : `32px × 32px`
- `2×2` : `64px × 64px`
- `3×3` : `96px × 96px`
- `4×4` : `128px × 128px`
- `5×5` : `160px × 160px`

You are not limited to these sizes; the game will still load sprites bigger or smaller than the recommended sprite, which can result in a unique-looking sprite, or an atrocity.

### Items, Liquid, Statuses
For these content types, the minimum sprite size is `32px`; you can use larger images, but the game will squish them down to `32px`. The game will not enlarge smaller images, so `32px` is the minimum.

### Units
Unit sprite sizes are more lenient than others, though try not to go below `48px`. The bigger your units are, the more you will have to adjust their `hitSize`(hitbox size).

## **Storing Sprites**
Sprites can be dropped in the `sprites/` subdirectory of your mod if it is hJSON, or `src/assets/sprites/` if it is a Java mod. The content parser will look through it recursively. 

Images are packed into an "atlas" for efficient rendering. The first directory in sprites/, e.g., `sprites/blocks`, determines the page in this atlas that sprites are put in. Putting a block's sprite in the units folder is likely to cause lots of lag; thus, you should try to organize things similarly to how the vanilla game does.

The game will look for sprites for content based on its name. `content/blocks/test-turret.json` has the name `test-turret`, and similarly, `sprites/test-turret.png` has the name `test-turret`, so it will be used by this content.
- Blocks should be stored in `sprites/blocks`
- Units should be stored in `sprites/units`
- Items should be stored in `sprites/items`

The game will modify some sprites. Turrets and units will have a `3-4px` gray border added to them, so you must account for that while making your sprites, leaving space around turrets. Default outline radius and color can be customized by changing the `outlineRadius` / `outlineColor` fields in the `Block` and `UnitType` classes.

### Overriding

Overriding existing sprites is possible; for this, sprites must be placed at `sprites-override/`.

## **Suffixes**
The game also can look for multiple sprites for a single block.

For turrets, the game could look for the suffix `<name>-heat`(`test-turret-heat.png`).

For blocks and crafters/smelters, the game may look for `<name>-top`, and `<name>-liquid`, which will be documented in their section.

You can read the source code for each respective block class for what sprites they can load for more details. See the lines with `@Load`.
For sprites in mods, check each `load()` method within the block class, if there is one.

## **Color Pallete**

Just like every game out there, Mindustry has its color palette. For beginners, it is highly recommended to stick to these specific colors for your sprites, or it may look out of place at best and even become heretical at worst. It may inflict great disturbance upon the #spriting Discord channel.

Block Color Pallete:

<img src="/wiki/images/modding/spriting/pal-mindustry.png">

Environment Color Pallete

<img src="/wiki/images/modding/spriting/pal-mindustry-evn.png">

Assuming you have correctly acquired proper spriting software, you should be able to download these images and use them as a color palette.

## **Styles and Shading**

Mindustry has a simple yet restrictive art style. What may work for other games will look out of place in Mindustry. Because of this, guidelines have been established to help modders to create sprites that will fit in the game.

Mindustry is a 2D game, so to add depth such as elevation and depression, we need to do a trick called 'shading'. Despite the actual asset being a 2D image, this trick makes it look 3D in-game.

Depending on where the light is shined, **elevations** are marked with **lighter tone**, **flat areas** with the **midtone**, and **depressions** with the **darker tone**. Picturing something in its 3D form and then drawing it in 2D is usually a good way to sprite something in Mindustry.

This is only a guideline, however if you bend it without having made successful Mindustry sprites first, you will most likely create an abomination, and the #spriting channel will not be happy.

---

### **Block Shading**
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/surge-smelter.png)

We will use the Surge Smelter as an example.

With blocks, the light source is near the **top right** corner, and the shadows are in the **bottom left**. Pixels in the top right, which are close to the light source, should be light colored. Likewise, pixels in the bottom right should be dark. It works best to have a diagonal line through the middle separating them.

Most blocks have 3 color types:

  - Base color, which has 3 shades: 
    
    - ![](https://via.placeholder.com/15/B0BAC0/000000?text=+) `B0BAC0` | Light Tone
    - ![](https://via.placeholder.com/15/989AA4/000000?text=+) `989AA4` | Midtone
    - ![](https://via.placeholder.com/15/6E7080/000000?text=+) `6E7080` | Dark Tone
  
  - Decal color, which also has 3 shades:
    
    - ![](https://via.placeholder.com/15/feb380/000000?text=+) `FEB380` | Lght Tone 
    - ![](https://via.placeholder.com/15/ea8878/000000?text=+) `EA8878` | Midtone 
    - ![](https://via.placeholder.com/15/bc5452/000000?text=+) `BC5452` | Dark Tone
   
  - Bottom color
    
    - ![](https://via.placeholder.com/15/4a4b53/000000?text=+) `4a4b53`

**Base Color** represents the primary color of the block. It is recommmended to only use shades of gray for crafters, as all vanilla crafters do.

**Decal Color** is the accent color on your block. It represents the block's **role** or **purpose** and a way to differentiate them from each other. To pick what decal color to use for your blocks, you should think about your block's purpose. For example:

**Plastanium Compressor**

![Plast-Comp](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/plastanium-compressor.png) 

Plastanium Compressor has a green decal. This green decal is the same color as plastanium. Therefore, just by looking at it you can tell this block has a connection with plastanium.

**Bottom Color** represents the insides of the block, where no light reaches, so it should be very dark. This could represent the bottom of a block with a chimney, like the Surge Smelter, for example.

Please note that different blocks require different amounts of layers depending on their type; for example, a wall would need only 1 layer, which is the sprite itself, while blocks like a reconstructor would need up to 4. See [#suffixes](#suffixes).

Modded Examples:

  - Unit Bunker by Flin#8261 from [DiverseTech](https://github.com/FlinTyX/DiverseTech)
  
    - <img src="/wiki/images/modding/spriting/sprite-examples/flintyx-unit-bunker.png" draggable="false">
  
  - Surge Mixer by Geschiedenis #4783 from [Unlimited Armament Works](https://github.com/Eschatologue/Unlimited-Armament-Works)
    
    - ![](https://raw.githubusercontent.com/Eschatologue/Unlimited-Armament-Works/master/assets/sprites/blocks/production/surge-mixer.png)


---

### **Turret Shading**

With Turret shading, the light source is on the **right side**, and the shadows are on the **left**.

![ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

We will use the '**Ripple**' as an example for this part.

Turrets in general has 2 to 3 color type with 2 tone for each:

- Base color

  - ![](https://via.placeholder.com/15/7b7b7b/000000?text=+) `7B7B7B` | Light Tone 
  - ![](https://via.placeholder.com/15/4d4e58/000000?text=+) `4D4E58` | Dark Tone 
  
- Decal color
  
  - ![](https://via.placeholder.com/15/feb380/000000?text=+) `FEB380` | Light Tone 
  - ![](https://via.placeholder.com/15/ea8878/000000?text=+) `EA8878` | Dark Tone 
  
- [Optional] Barrel Hole Color
  
  - ![](https://via.placeholder.com/15/2c2d38/000000?text=+) `2C2D38` 

**Base Color** or Body-Color, is the primary color of the turret. This can be classic copper brown, white, dark grey, or a custom color(from the palette!).

  - Copper Brown
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/duo.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/scorch.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/hail.png)
    - Usually represents a low tier turret, such as **Duo**, **Scorch**, **Hail**, etc. 
      
      - ![](https://via.placeholder.com/15/c9a58f/000000?text=+) `C9A58F` 
      - ![](https://via.placeholder.com/15/8f665b/000000?text=+) `8F665B` 
  
  - White
    
    - ![Arc](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/arc.png) ![Lancer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/lancer.png) ![Parallax](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/defense/parallax.png) ![Segment](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/defense/segment.png)
    - Usually represents turret that uses power instead of items to shoot, such as **Arc**, **Lancer**, **Paralax**, **Segment**.
  
      - ![](https://via.placeholder.com/15/f4f4f4/000000?text=+) `F4F4F4` 
      - ![](https://via.placeholder.com/15/c1c3d4/000000?text=+) `C1C3D4`
  
  - Dark Gray
    
    - ![Swarmer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/swarmer.png) ![Cyclone](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/cyclone.png) ![Meltdown](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/meltdown.png)
    - In most cases, dark grey represents mid to high tier turret.
      
      - ![](https://via.placeholder.com/15/7b7b7b/000000?text=+) `7B7B7B` 
      - ![](https://via.placeholder.com/15/4d4e58/000000?text=+) `4D4E58` 

**Decal color** in the turret is the same as regular block; it is an accent color and can represent the turret's role, purpose, or archetype. For example, if you are trying to group your turrets into different classes, you can differentiate them by decal color.

**Barrel Hole** is an optional color for turrets that represents the barrel hole of your turret; this is usually used for artillery turrets or missile launchers.

![Swarmer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/swarmer.png) 
![Ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

  - ![](https://via.placeholder.com/15/2c2d38/000000?text=+) `2C2D38` 

#### Unconventional Methods

  - **Turret Midtone**
    
    - Still a relatively new unconventional method is adding midtones into turret sprites to make it seem to have a flat surface, instead of only light and dark tones.
    
    - One example of this is the "Skyhammer" from [Unlimited Armament Works](https://github.com/Eschatologue/Unlimited-Armament-Works)
      
      - ![Skyhammer](https://github.com/Eschatologue/Unlimited-Armament-Works/blob/master/assets/sprites/blocks/turrets/artillery/skyhammer/skyhammer-preview.png?raw=true)

---

### **Resources Shading**
Resource shading is quite simple and can have its light coming from **top corners**, **top to down**, or **right to left**.

Resource sprites should only use 2 or 3 shades of one color. Make sure the sprite looks 3d and not flat, as then it will stick out like a paper thumb.

Examples:

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-copper.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-plastanium.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-graphite.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-coal.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-surge-alloy.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-scrap.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-pyratite.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-cryofluid.png)

### **Unit Shading**
Units are generally the hardest to shade.

Unit shading can get pretty complex for bigger units. In unit shading, light comes from the **top to bottom** or **front to back**. The intensity of lighter tone and darker tone changes depending on what part you are working with on the unit.

For units, light tone represents **elevation**, midtone represents **flat area**, and dark tone represents **depression**.

#### **Unit Base Color**

<img src="/wiki/images/modding/spriting/spriting-unit-shading.png" draggable="false">

The Eclipse is used for this example as it is the most complicated vanilla unit. As you continuously work towards the backside, there will be less light tone and more midtone and dark tone.

Parts that get lit by the light will have a lighter tone, while the ones that are not get a darker tone; flat areas are midtone.

<img src="/wiki/images/modding/spriting/spriting-unit-shading-illustration.png" draggable="false">

Above are the rough illustration of units if imagined in 3D.

- Base color, has 3 tones as usual: 
  
  - ![](https://via.placeholder.com/15/B0BAC0/000000?text=+) `B0BAC0` | Light Tone
  - ![](https://via.placeholder.com/15/989AA4/000000?text=+) `989AA4` | Midtone
  - ![](https://via.placeholder.com/15/6E7080/000000?text=+) `6E7080` | Dark Tone

#### **Unit Decal Color**

Unit decal color only has 2 tones: light and dark. The color represents the unit's role in-game.
 
- Yellow Color represents **Core** units, which the Core produces.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/gamma.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/beta.png)
    
    - ![](https://via.placeholder.com/15/ffd37f/000000?text=+) `FFD37F` | Light Tone 
    - ![](https://via.placeholder.com/15/d4816b/000000?text=+) `D4816B` | Dark Tone 

- Orange Color represents **Assault** units, which have the role of attacking your opponents.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/horizon.png)
    
    - ![](https://via.placeholder.com/15/ffa665/000000?text=+) `FFA665` | Light Tone 
    - ![](https://via.placeholder.com/15/d06b53/000000?text=+) `D06B53` | Dark Tone 

- Green Color represents **Support** units that can build, heal, and shield your units.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/poly.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/retusa.png)

    - ![](https://via.placeholder.com/15/84f491/000000?text=+) `84F491` | Light Tone 
    - ![](https://via.placeholder.com/15/62ae7f/000000?text=+) `62AE7F` | Dark Tone 

- Purple Color represents ~~spooder~~ **Specialist** units, which do other things.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/crawler.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/arkyid.png)
    
    - ![](https://via.placeholder.com/15/bf92f9/000000?text=+) `BF92F9` | Light Tone 
    - ![](https://via.placeholder.com/15/665c9f/000000?text=+) `665C9F` | Dark Tone 

You are free to pick whatever color you would like, as long as it's present on multiple units and fits with the other colors in the palette.

#### **Unit Cell/Team Color**
Unit Cells are sprites used to differentiate units between teams; they are separate sprites that will be loaded on top of the unit.

<img src="/wiki/images/modding/spriting/spriting-unit-cell.png" draggable="false">

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress-cell.png)

Above is a fortress with its cell. The game will automatically replace the **white**(#FFFFF) and **tan**(#DCC6C6) colors with shades of team color. Your cell sprites should only have the two shades below:

  - ![](https://via.placeholder.com/15/ffffff/000000?text=+) `FFFFFF` | Light Tone 
  - ![](https://via.placeholder.com/15/dcc6c6/000000?text=+) `DCC6C6` | Dark Tone 

Spriting software capable of using layers and exporting them separately is highly recommended because you can sprite the unit itself and the cell on a separate layer within one file.

#### **Unit Weapons**
Unit Weapons follow the same rules as turrets and unit shading; they can be shaded from **top to bottom** or **right to left**.


![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/zenith-missiles.png) 
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/large-artillery.png) 
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/large-laser-mount.png)

Weapons' rotation is based on the centre of the sprite; if you want to shift the weapon rotation point, you must shift the sprite.


#### **Unit Spriting Stages**

<img src="/wiki/images/modding/spriting/spriting-unit-stepbystep.png" draggable="false">
 
The process of drawing units can be roughly divided into 5 stages:

1. Scribble down the general shape. Pick a thick brush with a dark tone and paint it, slowly adding lines over each other and forming basic shapes without much precision. Try to make them slightly deformed or curved, and make sure the shape looks nice - you cannot make a good sprite out of a bad shape in most cases, so make sure you are satisfied before you move on.

2. Refine the shape and make it out of lines angled at 45 degrees. You may want to tweak edges, and don't try to follow the doodle you already made too closely.

3. Add decals. This is tricky because decals are hard to get right. I showed 3 examples that work - you should experiment for yourself, however, and see what works best for you. The reason why it's better to add them now is that later you will be able to "build shades" around decals, making it easier to proceed at stage 5. 

4. Roughly mark the lighter and darker parts. Since the light comes from the top, you can and should help yourself and mark what shapes you want to be illuminated the least or the most right away to spare yourself from overthinking about it. Refrain from covering too much space because around 30-40% of the sprite should be the dark shade. Also, note that you should leave the area around decals dark to increase the contrast and make it more appealing to look at.

5. By far the most complex part - "add details". There are not many tricks you can use; you have to get good at this. However, there is one I use: when uncertain about what should you add, add cells there. They can work like extra decals, and you may want to build your shapes around them. Refrain from adding too many details, and use any convenient corner or slab to carve a new shape.

> written by Zhenьkotron#9493, proofread by Geschiedenis#4783, grammar fixed by BalaM314#4781.

### **Outlines**
Leave 4 pixels of space around the edges of turret sprites and unit sprites, as the game will use that space to automatically add outlines.

---

### **Evironmental Sprites**
Environmental sprites are a bit different from the rest of the Mindustry spriting style, which is that the **45° increment rule doesn't apply**.

Environmental sprites will make up most, if not the majority, of a Mindustry game, so it should be in your best interest that the sprite you've made is subtle enough and looks great despite being tiled over and over again.

#### **Floors**
Floors only have 2 color tones, and the number of variations is up to you.

  - Vanilla Examples :
    
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/basalt1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/basalt2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/basalt3.png)
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/dirt1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/dirt2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/dirt3.png)
  
  - Modded Examples :
    
    - ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/classem-stolnene1.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/classem-stolnene2.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/classem-stolnene3.png) 
    - ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/ebrin-drylon1.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/ebrin-drylon2.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/ebrin-drylon3.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/ebrin-drylon4.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/ebrin-drylon5.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/ebrin-drylon6.png) 

> Sprites by Sh1penfire#0868 from [Endless-Rusting](https://github.com/Sh1penfire/Endless-Rusting)
  
#### **Static Walls**
Not to be confused with buildable defenses, environmental walls have **3 color tones**, and just like floors, the number of variations is up to you.

Walls also have an optional 2x2 version, which is randomly mixed in with the 1x1 walls.

  - Vanilla Example :
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/dacite-wall1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/dacite-wall2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/dacite-wall-large.png)
  - Modded Example :
    - ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/classem-wallen1.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/classem-wallen2.png)

> Sprites by Sh1penfire#0868 from [Endless-Rusting](https://github.com/Sh1penfire/Endless-Rusting)

#### **Ores**
Ores are overlaid on top of floors, so they should look decent across all floor textures they will likely be placed on.

  - Vanilla Examples :
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-thorium1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-thorium2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-thorium3.png)
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-scrap1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-scrap2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-scrap3.png)
  - Modded Examples : 
    - ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/melonaleum1.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/melonaleum2.png) 
    - ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/taconite1.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/taconite2.png) ![](https://raw.githubusercontent.com/Sh1penfire/Endless-Rusting/master/assets/sprites/blocks/environment/taconite3.png)  

> Sprites by Sh1penfire from [Endless-Rusting](https://github.com/Sh1penfire/Endless-Rusting)

#### **Props**
Props(or boulders) are player breakable environmental blocks that will occur randomly over a floor, they have their own files, separate from environmental sprites.

  - Examples :

    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/boulder1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/boulder2.png)      
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/sand-boulder1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/sand-boulder2.png)


#### **Trees**

<img src="/wiki/images/modding/spriting/spriting-props-white-tree-screenshot.png" draggable="false">

Trees are drawn above most types of blocks, units can also pass through them, and they only act as additional foliage for maps.

Keep in mind that trees in particular have shadow sprites, you have to make these manually.

  - Examples :
  
    - <img src="/wiki/images/modding/spriting/spriting-props-white-tree.png" draggable="false">
  
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/white-tree-shadow.png)

---
