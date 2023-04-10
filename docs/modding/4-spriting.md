# Spriting

Spriting is a crucial aspect of Mindustry modding, as any custom creations would appear as "oh-no" sprite without it. However, the spriting style in Mindustry is intentionally simple and restrictive, which may differ from other games. Deviations from this style may result in graphics that appear out of place within the game.

As such, it is important to ensure that any custom creations align with the established spriting style of Mindustry to maintain consistency and visual appeal. By adhering to this style, the game remains true to its aesthetic and continues to provide an engaging experience for players.

You can find all the vanilla sprites [here](https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites).

Keep in mind however, this spriting guide is designed to help beginners understand the art style, while allowing experienced modders to exercise their creativity within the established framework. While these guidelines are not rigid rules, they serve as a useful starting point for maintaining the cohesive aesthetic of the game.

Following these guidelines ensures that the game remains consistent and your mod, visually appealing or at the very least acceptable. At the same time, experienced modders have the flexibility to deviate from these guidelines, while still staying true to the game's art style.

**Please be aware that using other modders' sprites without their permission is strictly prohibited. While you may use them as a source of inspiration or reference, you must obtain explicit permission before incorporating them into your own mods.**

**Any justification that disregards the need for permission, such as claiming that the mod is open-source and therefore free to use, will not be acknowledged or tolerated. Failure to adhere to this policy may result in your mod being blacklisted from the mod browser**

**Finally, it is important to avoid creating openly offensive or explicit sprites. It is best to keep your designs appropriate and suitable for all players.**

## **Spriting Software**
It is highly recommended that you use spriting software that supports transparency and exporting images in `.PNG` format. Below is a list of recommended software.

### **Desktop**

  1. **[Aseprite](https://www.aseprite.org/)**
      - The gold standard. Has a bit of a learning curve, but it is very simple once you get used to it. It is **paid** software, but you can **[compile the source code on your own](https://github.com/aseprite/aseprite/blob/main/INSTALL.md#compiling)**. Please buy a license to support its developers.
      - Has many features useful for Mindustry spriting such as:
         - Mirroring
         - Pallete Control
         - Animation
         - Layering (Can also export individual layers)
  
  2. **[LibreSprite](https://libresprite.github.io/#!/)**
      - A fork of the Aseprite repository and offers a similar set of features and functionality. Although not as up-to-date or powerful as Aseprite, Libresprite is a great option for those who want to create sprites in the Mindustry style without having to pay for the software.

  3. **[Piskel](https://www.piskelapp.com/)**
      - A pixel art software that may not be as feature-rich as Aseprite or LibreSprite, but it still gets the job done. It is available both online and as a downloadable version, and is more than enough for creating Mindustry-style sprites. 
      - Does not have the capability to export individual layers.

  4. **[Pixilart](https://www.pixilart.com/)**
      - AnPixilart is an online pixel art software that offers more features than Piskel, although it lacks a mirror tool. If you are more familiar with Pixilart, it may be a better choice over Piskel. 
      - Bloated for spriting in Mindustry style

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

The game will modify some sprites. Turrets and units will have a `3-4px` gray border added to them, so you must account for that while making your sprites, leaving space around turrets. Default outline radius and colour can be customized by changing the `outlineRadius` / `outlineColor` fields in the `Block` and `UnitType` classes.

### Overriding

Overriding existing sprites is possible; for this, sprites must be placed at `sprites-override/`.

## **Suffixes**
The game also can look for multiple sprites for a single block.

For turrets, the game could look for the suffix `<name>-heat`(`test-turret-heat.png`).

For blocks and crafters/smelters, the game may look for `<name>-top`, and `<name>-liquid`, which will be documented in their section.

You can read the source code for each respective block class for what sprites they can load for more details. See the lines with `@Load`.
For sprites in mods, check each `load()` method within the block class, if there is one.

## **Colour Pallete**

Like many games, Mindustry has a specific colour palette that should be followed when creating custom sprites. As a beginner, it is highly recommended adhering to these colours to ensure that your sprites doesn't look out of place within the game itself.

Using colours outside of this palette without proper experience or knowledge may result in sprites that appear out of place or, at worst, heretical. It can also cause significant disturbance in the #spriting Discord channel in the Mindustry Discord server.

Block Colour Pallete:

![](https://raw.githubusercontent.com/Eschatologue/wiki/master/docs/images/modding/spriting/pal-mindustry.png)

Environment Colour Pallete

![](https://raw.githubusercontent.com/Eschatologue/wiki/master/docs/images/modding/spriting/pal-mindustry-evn.png)

Assuming you have correctly acquired proper spriting software, you should be able to download these images and use them as a colour palette.

## **Styles and Shading**

The art style of Mindustry is deliberately simple yet restrictive. To ensure that all custom sprites maintain a cohesive look and feel within the game, guidelines have been established to assist modders in creating sprites that will seamlessly integrate with the game environment.

To create depth and a three-dimensional appearance within the confines of a 2D game, Mindustry utilizes a shading technique. Specifically, **elevations** are marked with a **lighter tone**, **flat** areas with a **midtone**, and **depressions** with a **darker tone**.

To effectively apply this shading technique, it is recommended to envision the object in 3D and then translate it into a 2D sprite. This can help ensure that the sprite blends seamlessly with the overall aesthetic of Mindustry.

It's important to note that the established spriting guidelines for Mindustry are just that - guidelines. However, it's recommended that beginners adhere to these guidelines until they have successfully created a sprite or at the very least understood the Mindustry sprites styles, as bending the rules without experience can result in less than desirable outcomes.

---

### **Block Shading**
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/surge-smelter.png)

We will use the Surge Smelter as an example.

With blocks, the light source is near the **top right** corner, and the shadows are in the **bottom left**. Pixels in the top right, which are close to the light source, should be light coloured. Likewise, pixels in the bottom right should be dark. It works best to have a diagonal line through the middle separating them from **top left** to **bottom right**.

Most blocks have 3 colour types:

  - Base colour, which has 3 shades: 
    
    - ![](https://via.placeholder.com/15/B0BAC0/?text=+) `#B0BAC0` | Light Tone
    - ![](https://via.placeholder.com/15/989AA4/?text=+) `#989AA4` | Midtone
    - ![](https://via.placeholder.com/15/6E7080/?text=+) `#6E7080` | Dark Tone
  
  - Decal colour, which also has 3 shades:
    
    - ![](https://via.placeholder.com/15/f7e97e/?text=+) `#F7E97E` | Light Tone 
    - ![](https://via.placeholder.com/15/e3ae6f/?text=+) `#E3AE6f` | Midtone 
    - ![](https://via.placeholder.com/15/d57c65/?text=+) `#D57C65` | Dark Tone
   
  - Bottom colour
    
    - ![](https://via.placeholder.com/15/4a4b53/?text=+) `#4A4B53`

**Base colour** represents the primary colour of the block. It is recommmended to only use shades of gray for crafters, as all vanilla crafters do.

**Decal colour** is the accent colour on your block. It represents the block's **role** or **purpose** and a way to differentiate them from each other. To pick what decal colour to use for your blocks, you should think about your block's purpose. For example:

**Plastanium Compressor**

![Plast-Comp](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/production/plastanium-compressor.png) 

Plastanium Compressor has a green decal. This green decal is the same colour as plastanium. Therefore, just by looking at it you can tell this block has a connection with plastanium.

**Bottom colour** represents the insides of the block, where no light reaches, so it should be very dark. This could represent the bottom of a block with a chimney, like the Surge Smelter, for example.

Please note that different blocks require different amounts of layers depending on their type; for example, a wall would need only 1 layer, which is the sprite itself, while blocks like a reconstructor would need up to 4. It also depends on how many `drawers` you use for the block itself.

---

### **Turret Shading**

With Turret shading, the light source is on the **right**, and the shadows are on the **left**.

![ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

We will use the '**Ripple**' as an example for this part.

Turrets in general has 2 to 3 colour type with 2 tone for each:

- Base colour

  - ![](https://via.placeholder.com/15/7b7b7b/?text=+) `#7B7B7B` | Light Tone 
  - ![](https://via.placeholder.com/15/4d4e58/?text=+) `#4D4E58` | Dark Tone 
  
- Decal colour
  
  - ![](https://via.placeholder.com/15/feb380/?text=+) `#FEB380` | Light Tone 
  - ![](https://via.placeholder.com/15/ea8878/?text=+) `#EA8878` | Dark Tone 
  

- [Optional] Barrel Hole Colour
  
  - ![](https://via.placeholder.com/15/2c2d38/?text=+) `#2C2D38` 

**Body Colour** is the primary colour of the turret. This can range from classic copper brown, white, or dark grey.

  - Copper Brown
  
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/duo.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/scorch.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/hail.png)
    - Usually represents a low tier turret, such as **Duo**, **Scorch**, **Hail**, etc. 
      
      - ![](https://via.placeholder.com/15/c9a58f/?text=+) `#C9A58F` 
      - ![](https://via.placeholder.com/15/8f665b/?text=+) `#8F665B` 
  
  - White
    
    - ![Arc](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/arc.png) ![Lancer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/lancer.png) ![Parallax](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/defense/parallax.png) ![Segment](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/defense/segment.png)
    - Usually represents turret that uses power instead of items to shoot, such as **Arc**, **Lancer**, **Paralax**, **Segment**.
  
      - ![](https://via.placeholder.com/15/f4f4f4/?text=+) `#F4F4F4` 
      - ![](https://via.placeholder.com/15/c1c3d4/?text=+) `#C1C3D4`
  
  - Dark Gray
    
    - ![Swarmer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/swarmer.png) ![Cyclone](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/cyclone.png) ![Meltdown](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/meltdown.png)
    - In most cases, dark grey represents mid to high tier turret.
      
      - ![](https://via.placeholder.com/15/7b7b7b/?text=+) `#7B7B7B` 
      - ![](https://via.placeholder.com/15/4d4e58/?text=+) `#4D4E58`  
      

**Decal colour** in the turret is the same as regular block; it is an accent colour and can represent the turret's role, purpose, or archetype. For example, if you are trying to group your turrets into different classes, you can differentiate them by decal colour.

**Barrel Hole** is an optional colour for turrets that represents the barrel hole of your turret; this is usually used for artillery turrets or missile launchers.

![Swarmer](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/swarmer.png) 
![Ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

  - ![](https://via.placeholder.com/15/2c2d38/?text=+) `#2C2D38` 

### **Resources Spriting & Shading**

Resources are items and liquids in Mindustry that can be obtained from the ground, walls, or buildings. **The 45-degree increment rule is loosely applied in their sprite design**. Shading can come from top corners, top to bottom, right to left, or left to right.

Resource sprites should have 2 or 3 shades of one colour and look 3D to avoid looking flat.

Examples:

Items 

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-copper.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-plastanium.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-coal.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-surge-alloy.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-scrap.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-pyratite.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-tungsten.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-carbide.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-fissile-matter.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/item-beryllium.png)

Liquids

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-cryofluid.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-oil.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-gallium.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-neoplasm.png)

Gasses

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-hydrogen.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-nitrogen.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-ozone.png)
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/items/liquid-cyanogen.png)


### **Unit Spriting & Shading**

When it comes to unit sprites, it's important to keep in mind that they can have a wide range of shapes, from narrow tips to wide bases, or even with holes in the middle. However, it's generally best to avoid too many sharp or straight lines for the main body of your unit, as this can make it look too boxy and less interesting.

To create a more dynamic and visually appealing unit, consider incorporating curves or angled lines, and don't be afraid to experiment with different shapes and proportions. Remember that the shading on your unit should also reflect its shape, with lighter tones representing elevated areas, mid-tones representing flat surfaces, and darker tones representing depressions.

Overall, the key to creating great unit sprites is to strike a balance between functionality and aesthetics. While it's important to ensure that your units are recognizable and easy to distinguish in-game, it's equally important to make them visually appealing for players to look at.

#### **Unit Base Colour**

<p align="center">
  <img width="500" height="397" src="https://raw.githubusercontent.com/Eschatologue/wiki/master/docs/images/modding/spriting/spriting-unit-shading.png">
</p>

For this example, we will use the Eclipse, which is one of the most complex vanilla Serpulo units in Mindustry. When shading the Eclipse (or any other sprite), it is important to gradually decrease the amount of light tone as you move towards the backside of the unit, while increasing the use of midtone and dark tone. This will help create a sense of depth and dimensionality in the sprite.

Parts that get lit by the light will have a lighter tone, while the ones that are not get a darker tone; flat areas are midtone.

<p align="center">
  <img width="400" height="200" src="https://raw.githubusercontent.com/Eschatologue/wiki/master/docs/images/modding/spriting/spriting-unit-shading-illustration.png">
</p>

Above are the rough illustration of units if imagined in 3D.

- Base colour, has 3 tones as usual: 
  
  - Serpulo Units 
  
    - ![](https://via.placeholder.com/15/B0BAC0/?text=+) `#B0BAC0` | Light Tone
    - ![](https://via.placeholder.com/15/989AA4/?text=+) `#989AA4` | Midtone
    - ![](https://via.placeholder.com/15/6E7080/?text=+) `#6E7080` | Dark Tone
  
  - Erekir Units
  
    - ![](https://via.placeholder.com/15/989AA4/?text=+) `#989AA4` | Light Tone
    - ![](https://via.placeholder.com/15/6e7080/?text=+) `#6E7080` | Midtone
    - ![](https://via.placeholder.com/15/4a4b53/?text=+) `#4A4B53` | Dark Tone

#### **Unit Decal Colour**

Unit decal colour only has 2 tones: light and dark. The colour represents the unit's role in-game.
 
- Yellow Colour represents **Core** units, which the Core produces.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/gamma.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/beta.png)
    
    - ![](https://via.placeholder.com/15/ffd37f/?text=+) `#FFD37F` | Light Tone 
    - ![](https://via.placeholder.com/15/d4816b/?text=+) `#D4816B` | Dark Tone 

- Orange Colour represents **Assault** units, which have the role of attacking your opponents.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/horizon.png)
    
    - ![](https://via.placeholder.com/15/ffa665/?text=+) `#FFA665` | Light Tone 
    - ![](https://via.placeholder.com/15/d06b53/?text=+) `#D06B53` | Dark Tone 

- Green Colour represents **Support** units that can build, heal, and shield your units.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/poly.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/retusa.png)

    - ![](https://via.placeholder.com/15/84f491/?text=+) `#84F491` | Light Tone 
    - ![](https://via.placeholder.com/15/62ae7f/?text=+) `#62AE7F` | Dark Tone 

- Purple Colour represents ~~spooder~~ **Specialist** units, which do other things.
  
  - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/crawler.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/arkyid.png)
    
    - ![](https://via.placeholder.com/15/bf92f9/?text=+) `#BF92F9` | Light Tone 
    - ![](https://via.placeholder.com/15/665c9f/?text=+) `#665C9F` | Dark Tone 

You are free to pick whatever colour you would like, as long as it's present on multiple units and fits with the other colours in the palette.

#### **Unit Cell/Team Colour**
Unit Cells are sprites used to differentiate units between teams; they are separate sprites that will be loaded on top of the unit.

![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/fortress-cell.png)

Above is a fortress with its cell. The game will automatically replace the **white**(#FFFFFF) and **tan**(#DCC6C6) colours with shades of team colour. Your cell sprites should only have the two shades below:

  - ![](https://via.placeholder.com/15/ffffff/?text=+) `#FFFFFF` | Light Tone 
  - ![](https://via.placeholder.com/15/dcc6c6/?text=+) `#DCC6C6` | Dark Tone 

Spriting software capable of using layers and exporting them separately is highly recommended because you can sprite the unit itself and the cell on a separate layer within one file.

#### **Unit Weapons**
Unit Weapons follow the same rules as turrets and unit shading; they can be shaded from **top to bottom** or **right to left**.


![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/zenith-missiles.png) 
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/large-artillery.png) 
![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/units/weapons/large-laser-mount.png)

Weapons' rotation is based on the centre of the sprite; if you want to shift the weapon rotation point, you must shift the sprite.


#### **Unit Spriting Stages**

<p align="center">
  <img src="https://raw.githubusercontent.com/Eschatologue/wiki/master/docs/images/modding/spriting/spriting-unit-stepbystep.png">
</p>
 
The process of drawing units can be roughly divided into 5 stages:

1. Scribble down the general shape. Pick a thick brush with a dark tone and paint it, slowly adding lines over each other and forming basic shapes without much precision. Try to make them slightly deformed or curved, and make sure the shape looks nice - you cannot make a good sprite out of a bad shape in most cases, so make sure you are satisfied before you move on.

2. Refine the shape and make it out of lines angled at 45 degrees. You may want to tweak edges, and don't try to follow the doodle you already made too closely.

3. Add decals. This is tricky because decals are hard to get right. I showed 3 examples that work - you should experiment for yourself, however, and see what works best for you. The reason why it's better to add them now is that later you will be able to "build shades" around decals, making it easier to proceed at stage 5. 

4. Roughly mark the lighter and darker parts. Since the light comes from the top, you can and should help yourself and mark what shapes you want to be illuminated the least or the most right away to spare yourself from overthinking about it. Refrain from covering too much space because around 30-40% of the sprite should be the dark shade. Also, note that you should leave the area around decals dark to increase the contrast and make it more appealing to look at.

5. By far the most complex part - "add details". There are not many tricks you can use; you have to get good at this. However, there is one I use: when uncertain about what should you add, add cells there. They can work like extra decals, and you may want to build your shapes around them. Refrain from adding too many details, and use any convenient corner or slab to carve a new shape.

> written by Zhenьkotron#9493, proofread by Geschiedenis#4783, grammar fixed by BalaM314#4781.

Alternatively, in the provided [link](https://youtu.be/wzitO-EESGY), you can find a video on how Anuke, the creator of Mindustry, creates his own sprites

### **Outlines**
It is recommended to leave a space of at least 4 pixels around the edges of turret and unit sprites. This space will allow the game to automatically add outlines to the sprites.

----

### **Evironmental Sprites**

Environmental sprites in Mindustry have a slightly different spriting style compared to other assets in the game. Unlike other sprites, **the 45-degree increment rule does not apply** to environmental sprites. These sprites make up a significant portion of the game's visuals, so it's essential to ensure that the sprites you create look great despite being tiled repeatedly.

#### **Floors**
Floors only have 2 colour tones, and the number of variations is up to you.

  - Vanilla Examples :
    
    - ![basalt1](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/basalt1.png) ![basalt2](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/basalt2.png) ![basalt3](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/basalt3.png)
  
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/beryllic-stone1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/beryllic-stone2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/beryllic-stone3.png)
  
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/magmarock1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/magmarock2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/magmarock3.png)
  
  - Modded Examples :
    
    - ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/classem-stolnene1.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/classem-stolnene2.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/classem-stolnene3.png)
  
    - ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/ebrin-drylon1.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/ebrin-drylon2.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/ebrin-drylon3.png)


> Sprites by Sh1penfire#0868 from [Endless-Rusting](https://github.com/Sh1penfire/Endless-Rusting)
  
#### **Static Walls**
Not to be confused with buildable defenses, environmental walls have **3 color tones**, and just like floors, the number of variations is up to you.

Walls also have an optional 2x2 version, which is randomly mixed in with the 1x1 walls.

  - Vanilla Example :
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/stone-wall1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/stone-wall2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/stone-wall-large.png)

    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/sand-wall1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/sand-wall2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/sand-wall-large.png)

    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ferric-stone-wall1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ferric-stone-wall2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ferric-stone-wall-large.png)
  
    -  ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/arkyic-wall1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/arkyic-wall2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/arkyic-wall-large.png)
  
  - Modded Example :
  
    - ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/classem-wallen1.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/classem-wallen2.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/classem-wallen-large.png)

    - ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/volen-wallen1.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/volen-wallen2.png) ![](https://raw.githubusercontent.com/Eschatologue/Endless-Rusting-for-wikiEX/master/assets/sprites/blocks/environment/volen-wallen-large.png)


> Sprites by Sh1penfire#0868 from [Endless-Rusting](https://github.com/Sh1penfire/Endless-Rusting)

#### **Ores**
Ores can be located either on the floor or walls, and they are essential for players to acquire resources in Mindustry. Players can place drills on the ores or beside them to extract the resources.

It is important to choose the color of the ore to match the resource it represents. For example, thorium ore should have the same color as the thorium item.

  - Floor Ore Example :
    - Copper
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-copper1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-copper2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-copper3.png)

    - Beryllium
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-beryllium1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-beryllium2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-beryllium3.png)

    - Titanium
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-titanium1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-titanium2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-titanium3.png)

    - Tungsten
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-tungsten1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-tungsten2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-tungsten3.png)

  - Wall Ore Example :

    - Beryllium
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-wall-beryllium1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-wall-beryllium2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-wall-beryllium3.png)

    - Tungsten
      - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-wall-tungsten1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-wall-tungsten2.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/environment/ore-wall-tungsten3.png)

      

#### **Props**
Props(or boulders) are player breakable environmental blocks that will occur randomly over a floor, they have their own files, separate from environmental sprites.

  - Examples :

    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/boulder1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/boulder2.png)      
    - ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/sand-boulder1.png) ![](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/props/sand-boulder2.png)

---
