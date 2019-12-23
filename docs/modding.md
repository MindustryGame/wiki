
# Table of Contents

1.  [Overview](#Overview)
    1.  [Directory Structure](#Directory%20Structure)
    2.  [Hjson](#Hjson)
    3.  [`mod.json`](#~mod.json~)
    4.  [Content](#Content)
    5.  [Types](#Types)
    6.  [Tech Tree](#Tech%20Tree)
    7.  [Sprites](#Sprites)
    8.  [Sound](#Sound)
    9.  [Dependencies](#Dependencies)
    10. [Bundles](#Bundles)
    11. [Markup](#Markup)
        -   [Built-in Colors](#Built-in%20Colors)
    12. [Schematic](#Schematic)
    13. [Scripts](#Scripts)
    14. [FAQ](#FAQ)
    15. [Change Log](#Change%20Log)
        -   [Dec 09](#74dc31b10a82763d4f1ff29d32ae430ee87b9def)
        -   [Dec 08](#268f3cc3c)
        -   [Dec 04](#a087df077)
        -   [Nov 26](#a5fbc0756)
        -   [Nov 22](#2d4270406)
        -   [Nov 22](#2c61fcdfa)
        -   [Nov 20](#968f3ace3)
2.  [World](#World)
    1.  [Block](#Block)
    2.  [Consumers](#Consumers)
    3.  [Consume](#Consume)
        -   [ConsumeItems](#ConsumeItems)
        -   [ConsumeLiquid](#ConsumeLiquid)
        -   [ConsumePower](#ConsumePower)
    4.  [BlockStorage](#BlockStorage)
    5.  [Environment](#Environment)
        -   [Floor](#Floor)
        -   [OverlayFloor](#OverlayFloor)
        -   [DoubleOverlayFloor](#DoubleOverlayFloor)
        -   [OreBlock](#OreBlock)
        -   [Rock](#Rock)
        -   [StaticWall](#StaticWall)
        -   [StaticTree](#StaticTree)
        -   [TreeBlock](#TreeBlock)
    6.  [Crafting](#Crafting)
        -   [GenericCrafter](#GenericCrafter)
        -   [GenericSmelter](#GenericSmelter)
        -   [Separator](#Separator)
    7.  [Sandbox](#Sandbox)
        -   [PowerVoid](#PowerVoid)
        -   [PowerSource](#PowerSource)
        -   [ItemSource](#ItemSource)
        -   [ItemVoid](#ItemVoid)
        -   [LiquidSource](#LiquidSource)
    8.  [Logic](#Logic)
        -   [MessageBlock](#MessageBlock)
    9.  [Defense](#Defense)
        -   [Wall](#Wall)
        -   [DeflectorWall](#DeflectorWall)
        -   [SurgeWall](#SurgeWall)
        -   [Door](#Door)
        -   [MendProjector](#MendProjector)
        -   [OverdriveProjector](#OverdriveProjector)
        -   [ForceProjector](#ForceProjector)
        -   [ShockMine](#ShockMine)
    10. [Turrets](#Turrets)
        -   [Turret](#Turret)
        -   [CooledTurret](#CooledTurret)
        -   [ItemTurret](#ItemTurret)
        -   [LiquidTurret](#LiquidTurret)
        -   [DoubleTurret](#DoubleTurret)
        -   [ArtilleryTurret](#ArtilleryTurret)
        -   [BurstTurret](#BurstTurret)
        -   [PowerTurret](#PowerTurret)
        -   [ChargeTurret](#ChargeTurret)
        -   [LaserTurret](#LaserTurret)
    11. [Distribution](#Distribution)
        -   [Conveyor](#Conveyor)
        -   [ArmoredConveyor](#ArmoredConveyor)
        -   [Junction](#Junction)
        -   [ItemBridge](#ItemBridge)
        -   [ExtendingItemBridge](#ExtendingItemBridge)
        -   [BufferedItemBridge](#BufferedItemBridge)
        -   [Sorter](#Sorter)
        -   [OverflowGate](#OverflowGate)
        -   [MassDriver](#MassDriver)
    12. [Liquid Blocks](#Liquid%20Blocks)
        -   [LiquidBlock](#LiquidBlock)
        -   [Pump](#Pump)
        -   [Conduit](#Conduit)
        -   [ArmoredConduit](#ArmoredConduit)
        -   [LiquidOverflowGate](#LiquidOverflowGate)
        -   [LiquidRouter](#LiquidRouter)
        -   [LiquidTank](#LiquidTank)
        -   [LiquidJunction](#LiquidJunction)
        -   [LiquidBridge](#LiquidBridge)
        -   [LiquidExtendingBridge](#LiquidExtendingBridge)
    13. [Power](#Power)
        -   [PowerBlock](#PowerBlock)
        -   [PowerNode](#PowerNode)
        -   [PowerDistributor](#PowerDistributor)
        -   [Battery](#Battery)
        -   [PowerGenerator](#PowerGenerator)
            -   [ThermalGenerator](#ThermalGenerator)
            -   [ItemLiquidGenerator](#ItemLiquidGenerator)
            -   [SingleTypeGenerator](#SingleTypeGenerator)
            -   [BurnerGenerator](#BurnerGenerator)
            -   [DecayGenerator](#DecayGenerator)
            -   [SolarGenerator](#SolarGenerator)
            -   [NuclearReactor](#NuclearReactor)
            -   [ImpactReactor](#ImpactReactor)
        -   [PowerDiode](#PowerDiode)
        -   [LightBlock](#LightBlock)
    14. [Production](#Production)
        -   [Drill](#Drill)
        -   [SolidPump](#SolidPump)
        -   [Cultivator](#Cultivator)
        -   [Fracker](#Fracker)
        -   [Incinerator](#Incinerator)
    15. [Unit Blocks](#Unit%20Blocks)
        -   [RepairPoint](#RepairPoint)
        -   [UnitFactory](#UnitFactory)
        -   [CommandCenter](#CommandCenter)
        -   [MechPad](#MechPad)
    16. [Storage](#Storage)
        -   [StorageBlock](#StorageBlock)
        -   [CoreBlock](#CoreBlock)
        -   [Vault](#Vault)
        -   [Unloader](#Unloader)
        -   [LaunchPad](#LaunchPad)
    17. [Attributes](#Attributes)
    18. [Attribute](#Attribute)
    19. [BuildVisibility](#BuildVisibility)
    20. [BlockGroup](#BlockGroup)
3.  [Type](#Type)
    1.  [Item](#Item)
        -   [ItemType](#ItemType)
    2.  [ItemStack](#ItemStack)
    3.  [Liquid](#Liquid)
    4.  [LiquidStack](#LiquidStack)
    5.  [Weapon](#Weapon)
    6.  [UnitType](#UnitType)
    7.  [Mech](#Mech)
    8.  [Category](#Category)
    9.  [Zone](#Zone)
    10. [StatusEffect](#StatusEffect)
4.  [Graphics](#Graphics)
    1.  [Layer](#Layer)
    2.  [Color](#Color)
    3.  [CacheLayer](#CacheLayer)
5.  [Entities](#Entities)
    1.  [BulletType](#BulletType)
        -   [BasicBulletType](#BasicBulletType)
            -   [ArtilleryBulletType](#ArtilleryBulletType)
            -   [FlakBulletType](#FlakBulletType)
            -   [MissileBulletType](#MissileBulletType)
            -   [BombBulletType](#BombBulletType)
        -   [HealBulletType](#HealBulletType)
        -   [LiquidBulletType](#LiquidBulletType)
        -   [MassDriverBolt](#MassDriverBolt)
        -   [Built-in Bullets](#Built-in%20Bullets)
    2.  [BaseUnit](#BaseUnit)
    3.  [Effect](#Effect)
    4.  [TargetPriority](#TargetPriority)
6.  [Objective](#Objective)
7.  [Other](#Other)
    1.  [Mindustry Source Structure](#Mindustry%20Source%20Structure)



Submit `test` pull requests, issues or suggestions on Github: <https://github.com/SimonWoodburyForget/mindustry-modding>


<a id="Overview"></a>

# Overview

Mindustry mods are simply directories of assests. You reuse existing types and can use different values to initialize them, and you can even overwrite initialization of vanilla content.

You can add custom sprites and sounds; sharing your mod is as simple as giving someone your project directory; mods are also cross platfrom to any platform that supports them.

It is also now possible to put schematics into mods


<a id="Directory%20Structure"></a>

## Directory Structure

Your project directory should look something like this:

    project
    ├── mod.json
    ├── content
    │   ├── items
    │   ├── blocks
    │   ├── mechs
    │   ├── liquids
    │   ├── units
    │   └── zones
    ├── maps
    ├── bundles
    ├── sounds
    ├── schematics
    ├── scripts
    ├── sprites-override
    └── sprites

*(only the `mod.json` file is required)*

Every platform has a different user application data directory, and this is where your mods should be placed:

-   Linux: `~/.local/share/Mindustry/mods/`
-   Steam: `steam/steamapps/common/Mindustry/mods/`
-   Windows: `%appdata%/Mindustry/mods/`
-   Apple: `~/Library/Application Support/Mindustry/mods/`

**Note;** your filenames should be lowercased and hyphen separated:

-   correct: `my-custom-block.json`
-   incorrect: `My Custom Block.json`


<a id="Hjson"></a>

## Hjson

Mindustry uses [Hjson](https://hjson.org/), which is a superset of the very popular serialization language known as Json. This means that any valid Json will work, but you get extra useful stuff:

    # single line comment
    
    // single line comment
    
    /* multiline
    comment */
    
    key1: single line string
    
    key2:
    '''
    multiline
    string
    '''
    
    key3: [ value 1
            value 2
            value 3 ]
    
    key4: { key1: string
            key2: 0 }

**[new [Nov 22](#2d4270406)]** Files may have either a `.json` or `.hjson` extension.


<a id="~mod.json~"></a>

## `mod.json`

At the root of your project directory, you must have a `mod.json` which defines the basic metadata for your project.

    name: Mod Name
    displayName: Mod [red]Name[]
    author: Yourself
    description: This is a useless description.
    version: "1.0"
    minGameVersion: "100.3"
    dependencies: [ ]

Notes:

-   `name` will be used to reference to your mod, so name it carefully;
-   `displayName` this will be used as a display name for the UI, which you can use to add formatting to said name;
-   `description` of the mod will be rendered in the ingame mod manager, so keep it short and to the point;
-   `dependencies` is optional, if you want to know more about that, go to the [dependencies](#Dependencies) section;
-   `minGameVersion` is the minimum build version of the game.


<a id="Content"></a>

## Content

**[new [Nov 22](#2d4270406)]** *file extension `.hjson` now supported*

At the root of your project directory you can have a `content/` directory, this is where all the JSON/HJSON data goes for your content, and in this directory you have subdirectories for the various content types, these are the current common ones:

-   `content/items/` for [items](#Item), like `copper` and `surge-alloy`;
-   `content/blocks/` for [blocks](#Block), like turrets and floors;
-   `content/mechs/` for [mechs](#Mech), like `tau` and `glaive`;
-   `content/liquids/` for [liquids](#Liquid), like `water` and `slag`;
-   `content/units/` for flying or ground [units](#UnitType), like `reaper` and `dagger`;
-   `content/zones/` for [zones](#Zone), configuration of campaign maps.

This is important, because it's how Mindustry will know which types to lookup. &#x2013; How you name your files is also important as the stem `name` of your path `content/blocks/<name>.json` is going to be used to reference it.

The content of these files should look as follows:

    type: TypeOfThing
    name: Name Of Thing
    description: Description of thing.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">type</td>
<td class="org-left">String</td>
<td class="org-left">Content type of this object.</td>
</tr>


<tr>
<td class="org-left">name</td>
<td class="org-left">String</td>
<td class="org-left">Displayed name of content.</td>
</tr>


<tr>
<td class="org-left">description</td>
<td class="org-left">String</td>
<td class="org-left">Displayed description of content.</td>
</tr>
</tbody>
</table>

Other fields included would be the fields of the `type` in question.


<a id="Types"></a>

## Types

Types have numerous fields, but the important one is `type`; this is a special field used by the content parser, that changes which type your object is. *A `Router` type can't be a `Turret` type*, as they're just completely different.

Types *extend* each other, so if `MissileBulletType` extends `BasicBulletType`, you'll have access to all the fields of `BasicBulletType` inside of `MissileBulletType` like `damage`, `lifetime` and `speed`. Fields are case sensitive: `hitSize =/= hitsize`.

What you can expect a field to do is up to the specific type, some types do absolutely nothing with their fields, and work mostly as a base types will extend from. One such type is `Block`.

`type` can be refer to the actual type field of the object. A type may also refer to other things like `float` is a type so it means you can type `0.3` in a field.

Here you can see, the type of the top level object is `Revenant`, but the type of the `bullet` is `BulletType` so you can use `MissileBulletType`, because `MissileBulletType` extends `BulletType`.

    type: Revenant
    weapon: {
      bullet: {
        type: MissileBulletType
        damage: 9000
      }
    }


<a id="Tech%20Tree"></a>

## Tech Tree

Much like `type` there exist another magical field known as `research` which can go at the root of any block object to put it in the techtree.

    research: duo

This would put your block after `duo` in the techtree, and to put it after your own mods block you would write your `<block-name>`, a mod name prefix is only required if you're using the content from another mod.

Research cost will be `30 + requirements * 6`, where `requirements` is the build cost of your block. *(in otherwords you can't set `requirements` and `research cost` individually)*


<a id="Sprites"></a>

## Sprites

All you need to make sprites, is an image editor that supports transparency *(aka: not paint).* Block sprites should be `32 * size`, so a `2x2` block would require a `64x64` image. Images must be `.png` files with 32 bit depth.

Sprites can simply be dropped in the `sprites/` subdirectory. The content parser will look through it recursively, so you can organize them how ever you feel.

Content is going to look for sprites relative to it's own name. `content/blocks/my-hail.json` has the name `my-hail` and similarly `sprites/my-hail.png` has the name `my-hail`, so it'll be used by this content.

Content may look for multiple sprites. `my-hail` could be a turret, and it could look for the suffix `<name>-heat` and what this means is it'll look for `my-hail-heat`.

You can find all the vanilla sprites here:

-   <https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites>

Another thing to know about sprites is that some of them are modified by the game. Turrets specifically have a black border added to them, so you must account for that while making your sprites, leaving transparent space around turrets for example: [Ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

**[new [Nov 26](#a5fbc0756)]** to override ingame content sprites, you can simply put them in `sprites-override/`.


<a id="Sound"></a>

## Sound

Custom sounds can be added through the modding system by dropping them in the `sounds/` subdirectory. It doesn't matter where you put them. Two formats are needed:

-   `.ogg` required for Desktop/Android
-   `.mp3` required for iOS

Just like any other assets, you reference them by the stem of your filenames, so `pewpew.ogg` and `pewpew.mp3` can be referenced with `pewpew` from a field of type `Sound`.

Here's a list of built-in sounds:

-   `artillery`
-   `back`
-   `bang`
-   `beam`
-   `bigshot`
-   `boom`
-   `break`
-   `build`
-   `buttonClick`
-   `click`
-   `conveyor`
-   `corexplode`
-   `door`
-   `drill`
-   `empty`
-   `explosionbig`
-   `explosion`
-   `fire`
-   `flame2`
-   `flame`
-   `laserbig`
-   `laser`
-   `machine`
-   `message`
-   `missile`
-   `pew`
-   `place`
-   `press`
-   `release`
-   `respawning`
-   `respawn`
-   `shootBig`
-   `shoot`
-   `shootSnap`
-   `shotgun`
-   `spark`
-   `splash`
-   `spray`
-   `thruster`
-   `unlock`
-   `wave`
-   `windowHide`


<a id="Dependencies"></a>

## Dependencies

You can add dependencies to your mod by simple adding other mods name in your `mod.json`:

    dependencies: [
      other-mod-name
      not-a-mod
    ]

The name of dependencies are lower-cased and spaces are replaced with `-` hyphens, for example `Other MOD NamE` becomes `other-mod-name`.

To reference the other mods assets, you must prefix the asset with the other mods name:

-   `other-mod-name-not-copper` would reference `not-copper` in `other-mod-name`
-   `other-mod-name-angry-dagger` would reference `angry-dagger` in `other-mod-name`
-   `not-a-mod-angry-dagger` would reference `angry-dagger` in `not-a-mod`


<a id="Bundles"></a>

## Bundles

An optional addition to your mod is called bundles. The main use of bundles are give translations of your content, but there's no reason you couldn't use them in English. These are plaintext files which go in the `bundles/` subdirectory, and they should be named something like `bundle_ru.properties` (for Russian).

The contents of this file is very simple:

    block.example-mod-silver-wall.name = Серебряная Стена
    block.example-mod-silver-wall.description = Стена из серебра.

If you've read the first few sections of this guide, you'll spot it right away:

-   `<content type>.<mod name>-<content name>.name`
-   `<content type>.<mod name>-<content name>.description`

Notes:

-   mod/content names are lowercased and hyphen separated.

List of content type:

-   `item`
-   `block`
-   `mech`
-   `bullet`
-   `liquid`
-   `status`
-   `unit`
-   `weather`
-   `effect`
-   `zone`
-   `loadout`
-   `typeid`

List of filenames relative to languages:

-   English `bundle.properties`
-   Czech `bundle_cs.properties`
-   German `bundle_de.properties`
-   Spanish `bundle_es.properties`
-   Estonian `bundle_et.properties`
-   Basque `bundle_eu.properties`
-   French BE `bundle_fr_BE.properties`
-   French `bundle_fr.properties`
-   Bergabung `bundle_in_ID.properties`
-   Italian `bundle_it.properties`
-   Japanese `bundle_ja.properties`
-   Korean `bundle_ko.properties`
-   Dutch BE `bundle_nl_BE.properties`
-   Dutch `bundle_nl.properties`
-   Polish `bundle_pl.properties`
-   Portuguese BR `bundle_pt_BR.properties`
-   Portuguese  `bundle_pt.properties`
-   Russian `bundle_ru.properties`
-   Danish `bundle_sv.properties`
-   Turkman `bundle_tk.properties`
-   Turkish `bundle_tr.properties`
-   Ukrainian `bundle_uk_UA.properties`
-   Chinese CN `bundle_zh_CN.properties`
-   Chinese TW `bundle_zh_TW.properties`


<a id="Markup"></a>

## Markup

The text renderer uses a simple makeup language for coloring text.

-   `[name]` sets the color by name, there's a few [built-in colors](#Built-in%20Colors);
-   `[#rrggbb]` / `[#rrggbbaa]` sets the color by hex value, with each value being anything from `00` to `ff`:
    -   `rr` is the red value,
    -   `gg` is the green value,
    -   `bb` is the blue value,
    -   `aa` is the alpha value;
-   `[]` sets the color back to the previous color;
-   `[[` escapes the left bracket, so you can write `[[red]` to write and it'll render as `[red]`.

Notes:

-   erros/unknown colors will be silently ignored.

Example:

    [red]red
    [#ff0000]full-red
    [#ff000066]half-red
    [#ff000033]half-half-red
    [#00ff00]green
    []half-half-red


<a id="Built-in%20Colors"></a>

### Built-in Colors

    [clear]clear
    [black]black
    [white]white
    [lightgray]lightgray
    [gray]gray
    [darkgray]darkgray
    [blue]blue
    [navy]navy
    [royal]royal
    [slate]slate
    [sky]sky
    [cyan]cyan
    [teal]teal
    [green]green
    [acid]acid
    [lime]lime
    [forest]forest
    [olive]olive
    [yellow]yellow
    [gold]gold
    [goldenrod]goldenrod
    [orange]orange
    [brown]brown
    [tan]tan
    [brick]brick
    [red]red
    [scarlet]scarlet
    [coral]coral
    [salmon]salmon
    [pink]pink
    [magenta]magenta
    [purple]purple
    [violet]violet
    [maroon]maroon


<a id="Schematic"></a>

## Schematic

Fields that require the type `Schematic` can either take a built-in loadout *(see the [Zone](#Zone) section)* a base64 string, or the stem name of a `.msch` file in the `schematics/` subdirectory.

*As of now, the only purpose of schematics is to give a zone a loadout.*


<a id="Scripts"></a>

## Scripts

**[new [Dec 08](#268f3cc3c)]**

Scripting in Mindustry is done with the [Rhino JavaScript](https://github.com/mozilla/rhino) runtime. Scripts may be added to your mod by putting them in `scripts/`. Using the built-in `extendContent` function, you can extend existing Java types from JS, using *allowed classes* which are injected into your namespace.

For example:

-   `scripts/silo.js`
    
        // create a simple shockwave effect
        const siloLaunchEffect = newEffect(20, e => {
        
            // color goes from white to light gray
            Draw.color(Color.white, Color.lightGray, e.fin());
        
            // line thickness goes from 3 to 0
            Lines.stroke(e.fout() * 3);
        
            // draw a circle whose radius goes from 0 to 100
            Lines.circle(e.x, e.y, e.fin() * 100);
        });
        
        // create the block type
        const silo = extendContent(Block, "scatter-silo", {
        
            // override the method to build configuration
            buildConfiguration(tile, table) {
                table.addImageButton(
                    Icon.arrowUpSmall,
                    Styles.clearTransi,
        
                    // configure the tile to signal that it has been
                    // pressed (this sync on client to server)
                    run(() => tile.configure(0))
                ).size(50);
            },
        
            // override configure event
            configured(tile, value) {
        
                // make sure this silo has the items it needs to fire
                if (tile.entity.cons.valid()) {
        
                    // make this effect occur at the tile location
                    Effects.effect(siloLaunchEffect, tile);
        
                    // create 10 bullets at this tile's location with
                    // random rotation and velocity/lifetime
                    for (var i = 0; i < 10; i++) {
                        Calls.createBullet(
                            Bullets.flakExplosive,
                            tile.getTeam(),
                            tile.drawx(),
                            tile.drawy(),
                            Mathf.random(360),
                            Mathf.random(0.5, 1.0),
                            Mathf.random(0.2, 1.0)
                        );
                    }
        
                    // triggering consumption makes it use up the
                    // items it requires
                    tile.entity.cons.trigger();
                }
            }
        });

-   `content/blocks/scatter-silo.hjson`
    
        localizedName: "Scatter Silo"
        description: "A player-activatable block that scatters bullets everywhere upon use."
        
        category: turret
        size: 2
        
        update: true
        solid: true
        hasItems: true
        configurable: true
        
        requirements: [ "graphite/75"
                        "titanium/30" ]
        
        consumes: { items: { items: [ "scrap/10" ] } }


<a id="FAQ"></a>

## FAQ

-   `time` in game is calculated through `ticks`;
-   `ticks` *sometimes called `frames`,* are assumed to be 60/1 second;
-   `tilesize` is 8 units internally;
-   to calculate range out of `lifetime` and `speed` you can do `lifetime * speed = range`;
-   <a id="orgdb78fe9"></a> what is `abstract`? all you need to know about abstract types, is this is a Java specific term, which means you cannot instantiate/initialize this specific type by itself. If you do so you'll probably get an *"initialization exception"* of some kind;
-   what is a `NullPointerException`? This is an error message that indicates a field is null and shouldn't be null, meaning one of the required fields may be missing;
-   <a id="orgcafc2a6"></a> what is `bleeding-edge`? This is the developer version of Mindustry, specifically it's refering to the Github master branch. Changes on bleeding-edge usually make it into Mindustry in the next release.


<a id="Change%20Log"></a>

## Change Log

This is a log of changes done on the Mindustry Master branch that affected the modding API. The sections are ordered by date commited, and provide a description of what was changed, with a link to the diff on Github.


<a id="74dc31b10a82763d4f1ff29d32ae430ee87b9def"></a>

### Dec 09

[ [commit](https://github.com/Anuken/Mindustry/commit/74dc31b10a82763d4f1ff29d32ae430ee87b9def)  Removed unnecessary unit types ]

-   changed unit types names:
    -   `Draug` &rarr; `MinerDrone`;
    -   `Spirit` &rarr; `RepairDrone`;
    -   `Phantom` &rarr; `BuilderDrone`;
    -   [ `Dagger` `Crawler` `Titan` `Fortress` `Eruptor` ] &rarr; `GroundUnit`;
    -   [ `Wraith` `Ghoul` ] &rarr; `FlyingUnit`;
    -   `Revenant` &rarr; `HoverUnit`;


<a id="268f3cc3c"></a>

### Dec 08

[ [commit](https://github.com/Anuken/Mindustry/commit/268f3cc3c) Merge branches `master` and `rhino-js-suffering` ]

-   `scripts/` sub-directory and Rhino JS runtime was added;
-   `displayName` can now be used as field name in `mod.json`


<a id="a087df077"></a>

### Dec 04

[ [commit](https://github.com/Anuken/Mindustry/commit/a087df077) Added experimental server block syncing ]

-   `sync` field for `Block` type was added;


<a id="a5fbc0756"></a>

### Nov 26

[ [commit](https://github.com/Anuken/Mindustry/commit/a5fbc0756) Texture overrides / Potential mod texture binding optimizations ]

-   `sprites-override/` subdirectory can now be used to override existing ingame sprites;


<a id="2d4270406"></a>

### Nov 22

[ [commit](https://github.com/Anuken/Mindustry/commit/2d4270406) Switched to hjson extension ]

-   `.hjson` can now be used as a file extension;


<a id="2c61fcdfa"></a>

### Nov 22

[ [commit](https://github.com/Anuken/Mindustry/commit/2c61fcdfa) Added optional mod minimum game version ]

-   `minGameVersion` can now be used within `mod.json`;


<a id="968f3ace3"></a>

### Nov 20

[ [commit](https://github.com/Anuken/Mindustry/commit/968f3ace3) Better mod parsing ]

-   `liquid/amount` can now be used as a string for `LiquidStack`;
-   `item/amount` can now be used as a string for `ItemStack`;
-   `mod.json` now supports hjson;


<a id="World"></a>

# World


<a id="Block"></a>

## Block

Extends [BlockStorage](#BlockStorage)

Block is the base type of all blocks in the game. All blocks have at least one sprite, which is picked relative to the blocks name.

Fields for all objects that are blocks.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether this block has a tile entity that updates</td>
</tr>


<tr>
<td class="org-left">destructible</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether this block has health and can be destroyed</td>
</tr>


<tr>
<td class="org-left">unloadable</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">whether unloaders work on this block</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether this is solid</td>
</tr>


<tr>
<td class="org-left">solidifes</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether this block CAN be solid.</td>
</tr>


<tr>
<td class="org-left">rotate</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether this is rotateable</td>
</tr>


<tr>
<td class="org-left">breakable</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether you can break this with rightclick</td>
</tr>


<tr>
<td class="org-left">placeableOn</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">whether this [floor](#Floor) can be placed on.</td>
</tr>


<tr>
<td class="org-left">insulated</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">whether this block has insulating properties.</td>
</tr>


<tr>
<td class="org-left">health</td>
<td class="org-left">int</td>
<td class="org-right">-1</td>
<td class="org-left">tile entity health</td>
</tr>


<tr>
<td class="org-left">baseExplosiveness</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">base block explosiveness</td>
</tr>


<tr>
<td class="org-left">floating</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">whether this block can be placed on edges of liquids.</td>
</tr>


<tr>
<td class="org-left">size</td>
<td class="org-left">int</td>
<td class="org-right">1</td>
<td class="org-left">multiblock size</td>
</tr>


<tr>
<td class="org-left">expanded</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">Whether to draw this block in the expanded draw range.</td>
</tr>


<tr>
<td class="org-left">timers</td>
<td class="org-left">int</td>
<td class="org-right">0</td>
<td class="org-left">Max of timers used.</td>
</tr>


<tr>
<td class="org-left">cacheLayer</td>
<td class="org-left">[CacheLayer](#CacheLayer)</td>
<td class="org-right">normal</td>
<td class="org-left">Cache layer. Only used for 'cached' rendering.</td>
</tr>


<tr>
<td class="org-left">fillesTile</td>
<td class="org-left">true</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Special flag; if false, [floor](#Floor) will be drawn under this block even if it is cached.</td>
</tr>


<tr>
<td class="org-left">alwaysReplace</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">whether this block can be replaced in all cases</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">[BlockGroup](#BlockGroup)</td>
<td class="org-right">none</td>
<td class="org-left">Unless `canReplace` is overriden, blocks in the same group can replace each other.</td>
</tr>


<tr>
<td class="org-left">priority</td>
<td class="org-left">TargetPriority</td>
<td class="org-right">base</td>
<td class="org-left">Targeting priority of this block, as seen by enemies.</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Whether the block can be tapped and selected to configure.</td>
</tr>


<tr>
<td class="org-left">consumesTap</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Whether this block consumes touchDown events when tapped.</td>
</tr>


<tr>
<td class="org-left">drawLiquidLight</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether to draw the glow of the liquid for this block, if it has one.</td>
</tr>


<tr>
<td class="org-left">posConfig</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Whether the config is positional and needs to be shifted.</td>
</tr>


<tr>
<td class="org-left">sync</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">**[new [Dec 04](#a087df077)]** Whether to periodically sync this block across the network.</td>
</tr>


<tr>
<td class="org-left">targetable</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether units target this block.</td>
</tr>


<tr>
<td class="org-left">canOverdrive</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether the overdrive core has any effect on this block.</td>
</tr>


<tr>
<td class="org-left">outlineColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">404049</td>
<td class="org-left">Outlined icon color.</td>
</tr>


<tr>
<td class="org-left">outlineIcon</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">Whether the icon region has an outline added.</td>
</tr>


<tr>
<td class="org-left">hasShadow</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this block has a shadow under it.</td>
</tr>


<tr>
<td class="org-left">breakSound</td>
<td class="org-left">[Sound](#Sound)</td>
<td class="org-right">boom</td>
<td class="org-left">Sounds made when this block breaks.</td>
</tr>


<tr>
<td class="org-left">activeSound</td>
<td class="org-left">[Sound](#Sound)</td>
<td class="org-right">none</td>
<td class="org-left">The sound that this block makes while active. One sound loop. Do not overuse.</td>
</tr>


<tr>
<td class="org-left">activeSoundVolume</td>
<td class="org-left">float</td>
<td class="org-right">0.5</td>
<td class="org-left">Active sound base volume.</td>
</tr>


<tr>
<td class="org-left">idleSound</td>
<td class="org-left">[Sound](#Sound)</td>
<td class="org-right">none</td>
<td class="org-left">The sound that this block makes while idle. Uses one sound loop for all blocks.</td>
</tr>


<tr>
<td class="org-left">idleSoundVolume</td>
<td class="org-left">float</td>
<td class="org-right">0.5</td>
<td class="org-left">Idle sound base volume.</td>
</tr>


<tr>
<td class="org-left">requirements</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Cost of constructing and researching this block.</td>
</tr>


<tr>
<td class="org-left">category</td>
<td class="org-left">[Category](#Category)</td>
<td class="org-right">distribution</td>
<td class="org-left">Category in place menu.</td>
</tr>


<tr>
<td class="org-left">buildCost</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Cost of building this block; do not modify directly!</td>
</tr>


<tr>
<td class="org-left">buildVisibility</td>
<td class="org-left">[BuildVisibility](#BuildVisibility)</td>
<td class="org-right">hidden</td>
<td class="org-left">Whether this block is visible and can currently be built.</td>
</tr>


<tr>
<td class="org-left">buildCostMultiplier</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">Multiplier for speed of building this block.</td>
</tr>


<tr>
<td class="org-left">instantTransfer</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">Whether this block has instant transfer.</td>
</tr>


<tr>
<td class="org-left">alwaysUnlocked</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">[Layer](#Layer)</td>
<td class="org-right">null</td>
<td class="org-left">Layer to draw extra stuff on.</td>
</tr>


<tr>
<td class="org-left">layer2</td>
<td class="org-left">[Layer](#Layer)</td>
<td class="org-right">null</td>
<td class="org-left">Extra layer to draw extra stuff on.</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>` the main sprite for the block.


<a id="Consumers"></a>

## Consumers

This type is commonly used in block type with it's field `consumes`, it's a type that allows your block to consume something, and how this field works is up to the specific type extension you're using.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">item</td>
<td class="org-left">String</td>
<td class="org-left">shorthand for `items`</td>
</tr>


<tr>
<td class="org-left">items</td>
<td class="org-left">[ConsumeItems](#ConsumeItems)</td>
<td class="org-left">consume a number of different items</td>
</tr>


<tr>
<td class="org-left">liquid</td>
<td class="org-left">[ConsumeLiquid](#ConsumeLiquid)</td>
<td class="org-left">consume a single liquid</td>
</tr>


<tr>
<td class="org-left">power</td>
<td class="org-left">float or [ConsumePower](#ConsumePower)</td>
<td class="org-left">consume or buffer power</td>
</tr>


<tr>
<td class="org-left">powerBuffered</td>
<td class="org-left">float</td>
<td class="org-left">amount of power buffered</td>
</tr>
</tbody>
</table>

Notes:

-   you shouldn't have `power` and `powerBuffered`.

For example with [ConsumeItems](#ConsumeItems) and [ConsumeLiquid](#ConsumeLiquid):

    items: {
      items: [
        copper/10
        surge-alloy/5
      ]
      booster: true
      optional: true
    }
    liquid: {
      water/1.0
    }


<a id="Consume"></a>

## Consume

[Abstract](#orgdb78fe9) type which defines a type of resource that a block can consume.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">optional</td>
<td class="org-left">boolean</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">consumer will not influence consumer validity.</td>
</tr>


<tr>
<td class="org-left">booster</td>
<td class="org-left">boolean</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">consumer will be displayed as a boost input.</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">boolean</td>
<td class="org-left">true</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="ConsumeItems"></a>

### ConsumeItems

Extends [Consume](#Consume)

Type to consume ItemStacks.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">items</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
</tr>
</tbody>
</table>


<a id="ConsumeLiquid"></a>

### ConsumeLiquid

Extends [Consume](#Consume)

Type to consume a LiquidStack.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">liquid</td>
<td class="org-left">String</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">the name of [liquid](#Liquid) type consumed</td>
</tr>


<tr>
<td class="org-left">amount</td>
<td class="org-left">float</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">amount used per frame</td>
</tr>


<tr>
<td class="org-left">timePeriod</td>
<td class="org-left">float</td>
<td class="org-left">60</td>
<td class="org-left">how much time is taken to use this liquid, example: a normal ConsumeLiquid with 10/s and a 10 second timePeriod would display as *100 seconds*, but without a time override it would display as *10 liquid/second*. This is used for generic crafters.</td>
</tr>
</tbody>
</table>


<a id="ConsumePower"></a>

### ConsumePower

Extends [Consume](#Consume)

Type to consume or buffer power.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">usage</td>
<td class="org-left">float</td>
<td class="org-left">The maximum amount of power which can be processed per tick. This might influence efficiency or load a buffer</td>
</tr>


<tr>
<td class="org-left">capacity</td>
<td class="org-left">float</td>
<td class="org-left">The maximum power capacity in power units.</td>
</tr>


<tr>
<td class="org-left">buffered</td>
<td class="org-left">boolean</td>
<td class="org-left">True if the module can store power.</td>
</tr>
</tbody>
</table>


<a id="BlockStorage"></a>

## BlockStorage

[Abstract](#orgdb78fe9) type that extends [Content](#Content)

Type for blocks which may store a buffer of items or liquid.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">outputsLiquid</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">consumesPower</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">outputsPower</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">itemCapacity</td>
<td class="org-left">int</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">liquidCapacity</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">item</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">liquidPressure</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">consumes</td>
<td class="org-left">[Consumers](#Consumers)</td>
<td class="org-right">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="Environment"></a>

## Environment

Environmental blocks are blocks that must be placed from the editor, and they're the ones that will generally dictate how the game can or will be played. These blocks wont appear on a map unless you've built a map to support them.


<a id="Floor"></a>

### Floor

Extends [Block](#Block)

Type used for floors themselves or extended to make ores and other things.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">variants</td>
<td class="org-left">int</td>
<td class="org-right">3</td>
<td class="org-left">number of different variant regions to use.</td>
</tr>


<tr>
<td class="org-left">edge</td>
<td class="org-left">String</td>
<td class="org-right">stone</td>
<td class="org-left">edge fallback, used mainly for ores.</td>
</tr>


<tr>
<td class="org-left">speedMultiplier</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">multiplies unit velocity by this when walked on.</td>
</tr>


<tr>
<td class="org-left">dragMultiplier</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">multiplies unit drag by this when walked on.</td>
</tr>


<tr>
<td class="org-left">damageTaken</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">damage taken per tick on this tile.</td>
</tr>


<tr>
<td class="org-left">drownTime</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">how many ticks it takes to drown on this.</td>
</tr>


<tr>
<td class="org-left">walkEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">ripple</td>
<td class="org-left">effect when walking on this [floor](#Floor).</td>
</tr>


<tr>
<td class="org-left">drownUpdateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">bubble</td>
<td class="org-left">effect displayed when drowning on this [floor](#Floor).</td>
</tr>


<tr>
<td class="org-left">status</td>
<td class="org-left">StatusEffect</td>
<td class="org-right">none</td>
<td class="org-left">status effect applied when walking on.</td>
</tr>


<tr>
<td class="org-left">statusDuration</td>
<td class="org-left">float</td>
<td class="org-right">60</td>
<td class="org-left">intensity of applied status effect.</td>
</tr>


<tr>
<td class="org-left">liquidDrop</td>
<td class="org-left">[Liquid](#Liquid)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">liquids that drop from this block, used for pumps.</td>
</tr>


<tr>
<td class="org-left">itemDrop</td>
<td class="org-left">[Item](#Item)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">item that drops from this block, used for drills.</td>
</tr>


<tr>
<td class="org-left">isLiquid</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether this block can be drowned in.</td>
</tr>


<tr>
<td class="org-left">playerUnmineable</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">block cannot be mined by players if true.</td>
</tr>


<tr>
<td class="org-left">blendGroup</td>
<td class="org-left">[Block](#Block)</td>
<td class="org-right">this</td>
<td class="org-left">group of blocks that this block does not draw edges on.</td>
</tr>


<tr>
<td class="org-left">updateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">effect displayed when randomly updated.</td>
</tr>


<tr>
<td class="org-left">attributes</td>
<td class="org-left">[Attributes](#Attributes)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">array of affinities to certain things.</td>
</tr>
</tbody>
</table>

Notes:

-   this type requires a sprite to be visible from the map editor.

Sprites:

-   `<name><1..>` for variant sprites of the floor;
-   `<name>-edge` optional edge sprite.


<a id="OverlayFloor"></a>

### OverlayFloor

Extends [Floor](#Floor)

For example:

-   `tendrils`


<a id="DoubleOverlayFloor"></a>

### DoubleOverlayFloor

Extends [OverlayFloor](#OverlayFloor)

For example:

-   `pebbles`


<a id="OreBlock"></a>

### OreBlock

Extends [OverlayFloor](#OverlayFloor)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">variants</td>
<td class="org-right">3</td>
</tr>
</tbody>
</table>


<a id="Rock"></a>

### Rock

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">variants</td>
<td class="org-left">int</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">breakable</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">alwaysReplace</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="StaticWall"></a>

### StaticWall

Extends [Rock](#Rock)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">breakable</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">alwaysReplace</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">variants</td>
<td class="org-right">2</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-large.png` which is a 2x2 variant of the block.


<a id="StaticTree"></a>

### StaticTree

Extends [StaticWall](#StaticWall)

For example:

-   `spore-pine`
-   `snow-pine`
-   `pine`
-   `shrubs`


<a id="TreeBlock"></a>

### TreeBlock

Extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">power</td>
</tr>


<tr>
<td class="org-left">expanded</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="Crafting"></a>

## Crafting


<a id="GenericCrafter"></a>

### GenericCrafter

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">outputItem</td>
<td class="org-left">[ItemStack](#ItemStack)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">one item stack</td>
</tr>


<tr>
<td class="org-left">outputLiquid</td>
<td class="org-left">[LiquidStack](#LiquidStack)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">one liquid stack</td>
</tr>


<tr>
<td class="org-left">craftTime</td>
<td class="org-left">float</td>
<td class="org-right">80</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">craftEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">updateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">updateEffectChance</td>
<td class="org-left">float</td>
<td class="org-right">0.04</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">health</td>
<td class="org-right">60</td>
</tr>


<tr>
<td class="org-left">idleSound</td>
<td class="org-right">machine</td>
</tr>


<tr>
<td class="org-left">idleSoundVolume</td>
<td class="org-right">0.03</td>
</tr>


<tr>
<td class="org-left">sync</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="GenericSmelter"></a>

### GenericSmelter

Extends [GenericCrafter](#GenericCrafter)

A GenericCrafter with a new glowing region drawn on top.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">flameColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ffc999</td>
</tr>
</tbody>
</table>

Sprite suffix:

-   `<name>-top`


<a id="Separator"></a>

### Separator

Extends [Block](#Block)

Separator takes liquid as an input, and will produce items from it's stack randomly, using the amount of items in the stack as probability. Separator can't accept items as input, as it will output all the items you put in it, regardless of what you put in `results`.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">results</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">**[required]**</td>
</tr>


<tr>
<td class="org-left">craftTime</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">spinnerRadius</td>
<td class="org-left">float</td>
<td class="org-right">2.5</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">spinnerLength</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">spinnerThickness</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">spinnerSpeed</td>
<td class="org-left">float</td>
<td class="org-right">2</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">color</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">858585</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">liquidRegion</td>
<td class="org-left">int</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>

Sprite suffixes:

-   `<name>-liquid`


<a id="Sandbox"></a>

## Sandbox


<a id="PowerVoid"></a>

### PowerVoid

Extends [PowerBlock](#PowerBlock)

Deafults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">consumesPower</td>
<td class="org-right">MAX<sub>VALUE</sub></td>
</tr>
</tbody>
</table>


<a id="PowerSource"></a>

### PowerSource

Extends [PowerNode](#PowerNode)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">maxNodes</td>
<td class="org-right">100</td>
</tr>


<tr>
<td class="org-left">outputsPower</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">consumesPower</td>
<td class="org-right">false</td>
</tr>
</tbody>
</table>


<a id="ItemSource"></a>

### ItemSource

Extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-right">transportation</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="ItemVoid"></a>

### ItemVoid

Extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="LiquidSource"></a>

### LiquidSource

Extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasLiquids</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">liquidCapacity</td>
<td class="org-right">100</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">outputsLiquid</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="Logic"></a>

## Logic


<a id="MessageBlock"></a>

### MessageBlock

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">maxTextLength</td>
<td class="org-left">int</td>
<td class="org-right">220</td>
</tr>


<tr>
<td class="org-left">maxNewlines</td>
<td class="org-left">int</td>
<td class="org-right">24</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">destructible</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="Defense"></a>

## Defense


<a id="Wall"></a>

### Wall

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">variants</td>
<td class="org-left">int</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">destructible</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-right">walls</td>
</tr>


<tr>
<td class="org-left">buildCostMultiplier</td>
<td class="org-right">5</td>
</tr>
</tbody>
</table>


<a id="DeflectorWall"></a>

### DeflectorWall

Extends [Wall](#Wall) &#x2013; Wall that deflects low damage bullets.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hitTime</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">maxDamageDeflect</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
</tr>
</tbody>
</table>


<a id="SurgeWall"></a>

### SurgeWall

Extends [Wall](#Wall) &#x2013; Wall that creates lightning when shot.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">lightningChance</td>
<td class="org-left">float</td>
<td class="org-right">0.05</td>
</tr>


<tr>
<td class="org-left">lightningDamage</td>
<td class="org-left">float</td>
<td class="org-right">15</td>
</tr>


<tr>
<td class="org-left">lightningLength</td>
<td class="org-left">int</td>
<td class="org-right">17</td>
</tr>
</tbody>
</table>


<a id="Door"></a>

### Door

Extends [Wall](#Wall)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">openfx</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">dooropen</td>
</tr>


<tr>
<td class="org-left">closefx</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">doorclose</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">solidfies</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">consumesTap</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-open`


<a id="MendProjector"></a>

### MendProjector

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">color</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">84f491</td>
</tr>


<tr>
<td class="org-left">phase</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ffd59e</td>
</tr>


<tr>
<td class="org-left">reload</td>
<td class="org-left">float</td>
<td class="org-right">250</td>
</tr>


<tr>
<td class="org-left">range</td>
<td class="org-left">float</td>
<td class="org-right">60</td>
</tr>


<tr>
<td class="org-left">healPercent</td>
<td class="org-left">float</td>
<td class="org-right">12</td>
</tr>


<tr>
<td class="org-left">phaseBoost</td>
<td class="org-left">float</td>
<td class="org-right">12</td>
</tr>


<tr>
<td class="org-left">phaseRangeBoost</td>
<td class="org-left">float</td>
<td class="org-right">50</td>
</tr>


<tr>
<td class="org-left">useTime</td>
<td class="org-left">float</td>
<td class="org-right">400</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-top`


<a id="OverdriveProjector"></a>

### OverdriveProjector

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">color</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">feb380</td>
</tr>


<tr>
<td class="org-left">phase</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ffd59e</td>
</tr>


<tr>
<td class="org-left">reload</td>
<td class="org-left">float</td>
<td class="org-right">60</td>
</tr>


<tr>
<td class="org-left">range</td>
<td class="org-left">float</td>
<td class="org-right">80</td>
</tr>


<tr>
<td class="org-left">speedBoost</td>
<td class="org-left">float</td>
<td class="org-right">1.5</td>
</tr>


<tr>
<td class="org-left">speedBoostPhase</td>
<td class="org-left">float</td>
<td class="org-right">0.75</td>
</tr>


<tr>
<td class="org-left">useTime</td>
<td class="org-left">float</td>
<td class="org-right">400</td>
</tr>


<tr>
<td class="org-left">phaseRangeBoost</td>
<td class="org-left">float</td>
<td class="org-right">20</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">canOverdrive</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-top`


<a id="ForceProjector"></a>

### ForceProjector

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">phaseUseTime</td>
<td class="org-left">float</td>
<td class="org-right">350</td>
</tr>


<tr>
<td class="org-left">phaseRadiusBoost</td>
<td class="org-left">float</td>
<td class="org-right">80</td>
</tr>


<tr>
<td class="org-left">radius</td>
<td class="org-left">float</td>
<td class="org-right">101.7</td>
</tr>


<tr>
<td class="org-left">breakage</td>
<td class="org-left">float</td>
<td class="org-right">550</td>
</tr>


<tr>
<td class="org-left">cooldownNormal</td>
<td class="org-left">float</td>
<td class="org-right">1.75</td>
</tr>


<tr>
<td class="org-left">cooldownLiquid</td>
<td class="org-left">float</td>
<td class="org-right">1.5</td>
</tr>


<tr>
<td class="org-left">cooldownBrokenBase</td>
<td class="org-left">float</td>
<td class="org-right">0.35</td>
</tr>


<tr>
<td class="org-left">basePowerDraw</td>
<td class="org-left">float</td>
<td class="org-right">0.2</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">canOverdrive</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">consumes</td>
<td class="org-left">[cold-liquid](#org0403084)</td>
</tr>
</tbody>
</table>

<a id="org0403084"></a>[cold-liquid](#org0403084):

-   temperature less then 0.5
-   flammability less then 0.1
-   booster true
-   optional true
-   update false

Sprites:

-   `<name>-top`


<a id="ShockMine"></a>

### ShockMine

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">cooldown</td>
<td class="org-left">float</td>
<td class="org-right">80</td>
</tr>


<tr>
<td class="org-left">tileDamage</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">damage</td>
<td class="org-left">float</td>
<td class="org-right">13</td>
</tr>


<tr>
<td class="org-left">length</td>
<td class="org-left">int</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">tendrils</td>
<td class="org-left">int</td>
<td class="org-right">6</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">destructible</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">targetable</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-right">overlay</td>
</tr>
</tbody>
</table>


<a id="Turrets"></a>

## Turrets

This section is for turret types. All turrets shoot [BulletType](#BulletType), and this means [LiquidTurret](#LiquidTurret) can shoot [MissileBulletType](#MissileBulletType) and [ItemTurret](#ItemTurret) can shoot [LiquidBulletType](#LiquidBulletType).


<a id="Turret"></a>

### Turret

[Abstract](#orgdb78fe9) type which extends [Block](#Block)

The purpose of a turret type is to be a `Block` that shoots bullets. `Turret` is the base type for all turrets, it's *abstract* meaning it shouldn't be used directly, but everything which extends it will get it's fields.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">heatColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">turretHeat</td>
<td class="org-left">The color of the `-heat` sprite.</td>
</tr>


<tr>
<td class="org-left">shootEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">An effect fired on tile in the direction the turret is aiming when it shoots.</td>
</tr>


<tr>
<td class="org-left">smokeEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">An effect fired on tile in the direction the turret is aiming when it shoots.</td>
</tr>


<tr>
<td class="org-left">ammoUseEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">An effect fired on the tile, when ammo is consumed.</td>
</tr>


<tr>
<td class="org-left">shootSound</td>
<td class="org-left">[Sound](#Sound)</td>
<td class="org-right">shoot</td>
<td class="org-left">A sound created from the tile when a bullet is fired.</td>
</tr>


<tr>
<td class="org-left">ammoPerShot</td>
<td class="org-left">int</td>
<td class="org-right">1</td>
<td class="org-left">The amount of ammo used per shot.</td>
</tr>


<tr>
<td class="org-left">ammoEjectBack</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">The eject angle of shells in radians.</td>
</tr>


<tr>
<td class="org-left">range</td>
<td class="org-left">float</td>
<td class="org-right">50</td>
<td class="org-left">The range at which the turret can target enemies. Range is in `tilesize` so 8 is 1 tile.</td>
</tr>


<tr>
<td class="org-left">reload</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
<td class="org-left">The amount of ticks it takes to reload.</td>
</tr>


<tr>
<td class="org-left">inaccuracy</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">The degrees of inaccuracy.</td>
</tr>


<tr>
<td class="org-left">shots</td>
<td class="org-left">int</td>
<td class="org-right">1</td>
<td class="org-left">The numbers of bullets fired at once.</td>
</tr>


<tr>
<td class="org-left">spread</td>
<td class="org-left">float</td>
<td class="org-right">4</td>
<td class="org-left">The angular spread of multiple bullets when shot.</td>
</tr>


<tr>
<td class="org-left">recoil</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">The recoil of the turret when fired.</td>
</tr>


<tr>
<td class="org-left">restitution</td>
<td class="org-left">float</td>
<td class="org-right">0.02</td>
<td class="org-left">The restitution from recoil after shooting. *(time taken to recenter)*</td>
</tr>


<tr>
<td class="org-left">cooldown</td>
<td class="org-left">float</td>
<td class="org-right">0.02</td>
<td class="org-left">The amount of time it takes for the `-heat` sprite to become transparent.</td>
</tr>


<tr>
<td class="org-left">rotatespeed</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
<td class="org-left">The degrees per tick at which the turret can rotate.</td>
</tr>


<tr>
<td class="org-left">shootCone</td>
<td class="org-left">float</td>
<td class="org-right">8</td>
<td class="org-left">The angle used to determine whether the turret should be shooting.</td>
</tr>


<tr>
<td class="org-left">shootShake</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">The amount of camera shake.</td>
</tr>


<tr>
<td class="org-left">xRand</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">The random `x` axis multiplier, to make bullets appear to come out of multiple places. Used in Swarmer for example.</td>
</tr>


<tr>
<td class="org-left">targetAir</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this target can target air units.</td>
</tr>


<tr>
<td class="org-left">targetGround</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this turret can target ground units or blocks.</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">priority</td>
<td class="org-left">turret</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">turret</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">turrets</td>
</tr>


<tr>
<td class="org-left">outlineIcon</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>` the turret sprite,
-   `<name>-heat` the heat map.

Sprites-Override:

-   `block-<1..>` global turret base override, where the number is the turrets size. Can be used to override existing turret bases, as well as adding larger ones.


<a id="CooledTurret"></a>

### CooledTurret

Extends [Turret](#Turret) &#x2013; This is a base type that turrets which use [Liquid](#Liquid) to cool themselves extend from.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">coolantMultiplier</td>
<td class="org-left">float</td>
<td class="org-left">5</td>
<td class="org-left">How much reload is lowered by for each unit of liquid of heat capacity.</td>
</tr>


<tr>
<td class="org-left">coolEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">shoot</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Notes:

-   doesn't take flammable fluid
-   doesn't take hot fluid


<a id="ItemTurret"></a>

### ItemTurret

Extends [CooledTurret](#CooledTurret)

This type is a turret that uses items as ammo. The key to the `ammo` field should be the name of an [Item](#Item), while the value may be any [Built-in Bullets](#Built-in%20Bullets) or a [BulletType](#BulletType) itself.

    type: ItemTurret
    ammo: {
      copper: standardCopper
    
      metaglass: {
        type: MissileBulletType
        damage: 2
      }
    
      surge-alloy: {
        type: LiquidBulletType
        damage: 3
      }
    }

Here we're using `copper` to shoot `standardCopper` (built-in bullet) and `metalglass` to shoot a custom bullet of type `MissileBulletType`.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">maxAmmo</td>
<td class="org-left">int</td>
<td class="org-right">30</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">ammo</td>
<td class="org-left">{ String: [BulletType](#BulletType) }</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">String is the name of an [Item](#Item), which will be used to select the type of bullet which will be shot.</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="LiquidTurret"></a>

### LiquidTurret

Extends [Turret](#Turret)

This type is just a turret that uses liquid as ammo. The key to `ammo` must be the name of a [Liquid](#Liquid), while the value may either be the name of any [Built-in Bullets](#Built-in%20Bullets) or a [BulletType](#BulletType) itself.

For example you could do something like this:

    type: LiquidTurret
    ammo: {
      water: {
        type: MissileBulletType
        damage: 9000
      }
    
      slag: {
        type: LiquidBulletType
        damage: 0
      }
    }

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">fields</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">ammo</td>
<td class="org-left">{ String: [BulletType](#BulletType) }</td>
<td class="org-left">object with [Liquid](#Liquid) names to bullet types.</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">fields</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">activeSound</td>
<td class="org-left">spray</td>
</tr>
</tbody>
</table>


<a id="DoubleTurret"></a>

### DoubleTurret

Extends [ItemTurret](#ItemTurret)

ItemTurret that shoots from two side-by-side barrels.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">shotWidth</td>
<td class="org-left">float</td>
<td class="org-right">2</td>
</tr>
</tbody>
</table>

Default:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">shots</td>
<td class="org-right">2</td>
</tr>
</tbody>
</table>


<a id="ArtilleryTurret"></a>

### ArtilleryTurret

Extends [ItemTurret](#ItemTurret) &#x2013; Artillery turrets have special shooting calculations done to hit targets.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">targetAir</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="BurstTurret"></a>

### BurstTurret

Extends [ItemTurret](#ItemTurret) &#x2013; Turrets capable of bursts of specially spaced bullets, separated by long reload times.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">burstSpacing</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>
</tbody>
</table>


<a id="PowerTurret"></a>

### PowerTurret

Extends [CooledTurret](#CooledTurret) &#x2013; Turret which uses power has ammo to shoot.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">shootType</td>
<td class="org-left">[BulletType](#BulletType)</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">**[required]**</td>
</tr>


<tr>
<td class="org-left">powerUse</td>
<td class="org-left">float</td>
<td class="org-left">1</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="ChargeTurret"></a>

### ChargeTurret

Extends [PowerTurret](#PowerTurret)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">chargeTime</td>
<td class="org-left">float</td>
<td class="org-right">30</td>
</tr>


<tr>
<td class="org-left">chargeEffects</td>
<td class="org-left">int</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">chargeMaxDelay</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">chargeEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
</tr>


<tr>
<td class="org-left">chargeBeginEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
</tr>
</tbody>
</table>


<a id="LaserTurret"></a>

### LaserTurret

Extends [PowerTurret](#PowerTurret)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">firingMoveFract</td>
<td class="org-left">float</td>
<td class="org-right">0.25</td>
<td class="org-left">rotatespeed fraction when turret is shooting</td>
</tr>


<tr>
<td class="org-left">shootDuration</td>
<td class="org-left">float</td>
<td class="org-right">100</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">canOverdrive</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">coolantMultiplier</td>
<td class="org-left">1</td>
</tr>
</tbody>
</table>

Doesn't update shoot if:

-   liquid temperature greater or equal to `0.5`
-   liquid flammability greater then `0.1`


<a id="Distribution"></a>

## Distribution


<a id="Conveyor"></a>

### Conveyor

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

Default:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">rotate</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-right">overlay</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-right">transportation</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">itemCapacity</td>
<td class="org-right">4</td>
</tr>


<tr>
<td class="org-left">idleSound</td>
<td class="org-right">conveyor</td>
</tr>


<tr>
<td class="org-left">idleSoundVolume</td>
<td class="org-right">0.004</td>
</tr>


<tr>
<td class="org-left">unloadable</td>
<td class="org-right">false</td>
</tr>
</tbody>
</table>

Sprite suffix:

-   `-<0..4>-<0..3>` example: [Conveyors-sprites](https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites/blocks/distribution/conveyors)


<a id="ArmoredConveyor"></a>

### ArmoredConveyor

Extends [Conveyor](#Conveyor)  -A type of conveyor don't accept item coming from side


<a id="Junction"></a>

### Junction

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">26</td>
<td class="org-left">frames taken to go through this junction</td>
</tr>


<tr>
<td class="org-left">capacity</td>
<td class="org-left">capacity</td>
<td class="org-right">6</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">instantTransfer</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">transportation</td>
</tr>


<tr>
<td class="org-left">unloadable</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="ItemBridge"></a>

### ItemBridge

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">range</td>
<td class="org-left">int</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">transportTime</td>
<td class="org-left">float</td>
<td class="org-left">2</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">power</td>
</tr>


<tr>
<td class="org-left">expanded</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">itemCapacity</td>
<td class="org-left">10</td>
</tr>


<tr>
<td class="org-left">posConfig</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">unloadable</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">transportation</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-end` example: [bridge-conveyor-end](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/distribution/bridge-conveyor-end.png)
-   `<name>-bridge` example: [bridge-conveyor-bridge](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/distribution/bridge-conveyor-bridge.png)
-   `<name>-arrow` example: [bridge-conveyor-arrow](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/distribution/bridge-conveyor-arrow.png)


<a id="ExtendingItemBridge"></a>

### ExtendingItemBridge

Extends [ItemBridge](#ItemBridge)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="BufferedItemBridge"></a>

### BufferedItemBridge

Extends [ExtendingItemBridge](#ExtendingItemBridge)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">40</td>
</tr>


<tr>
<td class="org-left">bufferCapacity</td>
<td class="org-left">int</td>
<td class="org-right">50</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="Sorter"></a>

### Sorter

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">invert</td>
<td class="org-left">boolean</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">**[optional]**</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">instantTransfer</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">transportation</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">unloadable</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="OverflowGate"></a>

### OverflowGate

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">transportation</td>
</tr>


<tr>
<td class="org-left">unloadable</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="MassDriver"></a>

### MassDriver

Extends [Block](#Block) &#x2013; Uses `driverBolt` to transfer items.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">range</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">rotateSpeed</td>
<td class="org-left">float</td>
<td class="org-right">0.04</td>
</tr>


<tr>
<td class="org-left">translation</td>
<td class="org-left">float</td>
<td class="org-right">7</td>
</tr>


<tr>
<td class="org-left">minDistribute</td>
<td class="org-left">int</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">knockback</td>
<td class="org-left">float</td>
<td class="org-right">4</td>
</tr>


<tr>
<td class="org-left">reloadTime</td>
<td class="org-left">float</td>
<td class="org-right">100</td>
</tr>


<tr>
<td class="org-left">shootEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">shootBig2</td>
</tr>


<tr>
<td class="org-left">smokeEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">shootBigSmoke2</td>
</tr>


<tr>
<td class="org-left">recieveEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">mineBig</td>
</tr>


<tr>
<td class="org-left">shake</td>
<td class="org-left">float</td>
<td class="org-right">3</td>
</tr>
</tbody>
</table>

Notes:

-   range is limited by `driverBolt`'s max range, which is hard coded, so you cannot change it.

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">posConfig</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">turret</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">outlineIcon</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-base`


<a id="Liquid%20Blocks"></a>

## Liquid Blocks


<a id="LiquidBlock"></a>

### LiquidBlock

Extends [Block](#Block) &#x2013; For blocks that can carry liquids. Apart from the better defaults, it also fetches extra sprites.

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">liquids</td>
</tr>


<tr>
<td class="org-left">outputsLiquid</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-liquid`
-   `<name>-top`
-   `<name>-bottom`


<a id="Pump"></a>

### Pump

Extends [LiquidBlock](#LiquidBlock)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">pumpAmount</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">layer</td>
<td class="org-left">overlay</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">liquids</td>
</tr>


<tr>
<td class="org-left">floating</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="Conduit"></a>

### Conduit

Extends [LiquidBlock](#LiquidBlock)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">leakResistance</td>
<td class="org-left">float</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">rotate</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">floating</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-top-<0..6>`


<a id="ArmoredConduit"></a>

### ArmoredConduit

**[new type v99 (268)]** &#x2013; Extends [Conduit](#Conduit)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">leakResistance</td>
<td class="org-right">10</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-cap`


<a id="LiquidOverflowGate"></a>

### LiquidOverflowGate

**[new type v99 (268)]** &#x2013; Extends [LiquidBlock](#LiquidBlock)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">rotate</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-top`


<a id="LiquidRouter"></a>

### LiquidRouter

Extends [LiquidBlock](#LiquidBlock)


<a id="LiquidTank"></a>

### LiquidTank

Extends [LiquidRouter](#LiquidRouter)


<a id="LiquidJunction"></a>

### LiquidJunction

Extends [LiquidBlock](#LiquidBlock)


<a id="LiquidBridge"></a>

### LiquidBridge

Extends [LiquidBridge](#LiquidBridge)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">outputsLiquid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">liquids</td>
</tr>
</tbody>
</table>


<a id="LiquidExtendingBridge"></a>

### LiquidExtendingBridge

Extends [ExtendingItemBridge](#ExtendingItemBridge)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">outputsLiquid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">liquids</td>
</tr>
</tbody>
</table>


<a id="Power"></a>

## Power


<a id="PowerBlock"></a>

### PowerBlock

[Abstract](#orgdb78fe9) type which extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">power</td>
</tr>
</tbody>
</table>


<a id="PowerNode"></a>

### PowerNode

Extends [PowerBlock](#PowerBlock)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">laserRange</td>
<td class="org-left">float</td>
<td class="org-right">6</td>
</tr>


<tr>
<td class="org-left">maxNodes</td>
<td class="org-left">int</td>
<td class="org-right">3</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">expanded</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">power</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">consumesPower</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">outputsPower</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="PowerDistributor"></a>

### PowerDistributor

Extends [PowerBlock](#PowerBlock)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">consumesPower</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">outputsPower</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="Battery"></a>

### Battery

Extends [PowerDistributor](#PowerDistributor) &#x2013; Just a change of defaults for batteries.

Defauts:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">outputsPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">consumesPower</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="PowerGenerator"></a>

### PowerGenerator

Extends [PowerDistributor](#PowerDistributor)

Power generators will produce power with their [Consumers](#Consumers) type.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">powerProduction</td>
<td class="org-left">float</td>
<td class="org-left">Power produced per tick at 100% (`1.0`) efficiency; 1 `powerProduction` is approximately `60 pu/s`.</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">baseExplosiveness</td>
<td class="org-left">5</td>
</tr>


<tr>
<td class="org-left">sync</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="ThermalGenerator"></a>

#### ThermalGenerator

Extends [PowerGenerator](#PowerGenerator) &#x2013; Generates power with the heat [attribute](#Attributes) of a tile. Power production is `powerProduction * heat`, and `heat` must be greater then `0.01`.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">generateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">none</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="ItemLiquidGenerator"></a>

#### ItemLiquidGenerator

Extends [PowerGenerator](#PowerGenerator) &#x2013; Base of power generation blocks.

Notes:

-   item efficiency is **always** 0.0
-   liquid efficiency is **always** 0.0

*(this type doesn't produce power)*

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">minItemEfficiency</td>
<td class="org-left">float</td>
<td class="org-left">0.2</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">itemDuration</td>
<td class="org-left">float</td>
<td class="org-left">70</td>
<td class="org-left">number of ticks during which a single item will produce power.</td>
</tr>


<tr>
<td class="org-left">minLiquidEfficiency</td>
<td class="org-left">float</td>
<td class="org-left">0.2</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">maxLiquidGenerate</td>
<td class="org-left">float</td>
<td class="org-left">0.4</td>
<td class="org-left">Maximum liquid used per frame.</td>
</tr>


<tr>
<td class="org-left">generateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">generatespark</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">explodeEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">generatespark</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">heatColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">ff9b59</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">randomlyExplode</td>
<td class="org-left">boolean</td>
<td class="org-left">true</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">defaults</td>
<td class="org-left">boolean</td>
<td class="org-left">false</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Extra sprites:

-   `<name>-top` if `hasItems` is `true`
-   `<name>-liquid`


<a id="SingleTypeGenerator"></a>

#### SingleTypeGenerator

Extends [ItemLiquidGenerator](#ItemLiquidGenerator) &#x2013; Generates power from an item.


<a id="BurnerGenerator"></a>

#### BurnerGenerator

Extends [ItemLiquidGenerator](#ItemLiquidGenerator) &#x2013; Generates power from item flamability.


<a id="DecayGenerator"></a>

#### DecayGenerator

Extends [ItemLiquidGenerator](#ItemLiquidGenerator) &#x2013; Generates power from item radioactivity.

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="SolarGenerator"></a>

#### SolarGenerator

Extends [PowerGenerator](#PowerGenerator) &#x2013; A generator that always produces 100% efficiency power.

Notes:

-   Lower targetting priority then other generators.


<a id="NuclearReactor"></a>

#### NuclearReactor

Extends [PowerGenerator](#PowerGenerator) &#x2013; Generates power relative to how many items are in storage, and explodes if it runs out of coolant.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">lightColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">7f19ea</td>
<td class="org-left">**[new v99 (268)]**</td>
</tr>


<tr>
<td class="org-left">coolColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ffffff00</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">hotColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ff9575a3</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">itemDuration</td>
<td class="org-left">float</td>
<td class="org-right">120</td>
<td class="org-left">time to consume 1 fuel</td>
</tr>


<tr>
<td class="org-left">heating</td>
<td class="org-left">float</td>
<td class="org-right">0.01</td>
<td class="org-left">heating per frame \* fullness</td>
</tr>


<tr>
<td class="org-left">smokeThreshold</td>
<td class="org-left">float</td>
<td class="org-right">0.3</td>
<td class="org-left">heat at which blocks start smoking</td>
</tr>


<tr>
<td class="org-left">explosionRadius</td>
<td class="org-left">int</td>
<td class="org-right">40</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">explosionDamage</td>
<td class="org-left">int</td>
<td class="org-right">1350</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">flashThreshold</td>
<td class="org-left">float</td>
<td class="org-right">0.46</td>
<td class="org-left">heat at which lights start flashing</td>
</tr>


<tr>
<td class="org-left">coolantPower</td>
<td class="org-left">float</td>
<td class="org-right">0.5</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">itemCapacity</td>
<td class="org-left">30</td>
</tr>


<tr>
<td class="org-left">liquidCapacity</td>
<td class="org-left">30</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Extra Sprites:

-   `<name>-center` top region
-   `<name>-lights` lights region


<a id="ImpactReactor"></a>

#### ImpactReactor

Extends [PowerGenerator](#PowerGenerator) &#x2013; Generator that uses power and has a startup time.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">plasmas</td>
<td class="org-left">int</td>
<td class="org-right">4</td>
<td class="org-left">number of plasma sprites</td>
</tr>


<tr>
<td class="org-left">warmupSpeed</td>
<td class="org-left">float</td>
<td class="org-right">0.001</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">itemDuration</td>
<td class="org-left">float</td>
<td class="org-right">60</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">explosionRadius</td>
<td class="org-left">int</td>
<td class="org-right">50</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">explosionDamage</td>
<td class="org-left">int</td>
<td class="org-right">2000</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">plasma1</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ffd06b</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">plasma2</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ff361b</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">liquidCapacity</td>
<td class="org-left">30</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">outputsPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">consumesPower</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-bottom` bottom region
-   `<name>-plasma-<i>` plasma regions, where `i` is `0` to `plasmas - 1`.


<a id="PowerDiode"></a>

### PowerDiode

Extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">rotate</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">insulated</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-arrow`


<a id="LightBlock"></a>

### LightBlock

**[new type v99 (268)]** &#x2013; Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">brightness</td>
<td class="org-left">float</td>
<td class="org-right">0.9</td>
</tr>


<tr>
<td class="org-left">radius</td>
<td class="org-left">float</td>
<td class="org-right">200</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-top`


<a id="Production"></a>

## Production


<a id="Drill"></a>

### Drill

Extends [Block](#Block) &#x2013; Types which can be placed on ore blocks to extract the [OreBlock](#OreBlock)'s item.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">tier</td>
<td class="org-left">int</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">Maximum tier of blocks this drill can mine.</td>
</tr>


<tr>
<td class="org-left">drillTime</td>
<td class="org-left">float</td>
<td class="org-left">300</td>
<td class="org-left">Base time to drill one ore, in frames.</td>
</tr>


<tr>
<td class="org-left">liquidBoostIntensity</td>
<td class="org-left">float</td>
<td class="org-left">1.6</td>
<td class="org-left">How many times faster the drill will progress when boosted by liquid.</td>
</tr>


<tr>
<td class="org-left">warmupSpeed</td>
<td class="org-left">float</td>
<td class="org-left">0.02</td>
<td class="org-left">Speed at which the drill speeds up.</td>
</tr>


<tr>
<td class="org-left">drawMineItem</td>
<td class="org-left">boolean</td>
<td class="org-left">false</td>
<td class="org-left">Whether to draw the item this drill is mining.</td>
</tr>


<tr>
<td class="org-left">drillEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">mine</td>
<td class="org-left">Effect played when an item is produced. This is colored.</td>
</tr>


<tr>
<td class="org-left">rotateSpeed</td>
<td class="org-left">float</td>
<td class="org-left">2</td>
<td class="org-left">Speed the drill bit rotates at.</td>
</tr>


<tr>
<td class="org-left">updateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">pulverizeSmall</td>
<td class="org-left">Effect randomly played while drilling.</td>
</tr>


<tr>
<td class="org-left">updateEffectChance</td>
<td class="org-left">float</td>
<td class="org-left">0.02</td>
<td class="org-left">Chance the update effect will appear.</td>
</tr>


<tr>
<td class="org-left">drawRim</td>
<td class="org-left">boolean</td>
<td class="org-left">false</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">heatColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">ff5512</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">overlay</td>
</tr>


<tr>
<td class="org-left">group</td>
<td class="org-left">drills</td>
</tr>


<tr>
<td class="org-left">hasLiquids</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">liquidCapacity</td>
<td class="org-left">5</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">idleSound</td>
<td class="org-left">drill</td>
</tr>


<tr>
<td class="org-left">idleSoundVolume</td>
<td class="org-left">0.003</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-rim`
-   `<name>-rotator`
-   `<name>-top`


<a id="SolidPump"></a>

### SolidPump

Extends [Pump](#Pump) &#x2013; Pump that makes liquid from solids and takes in power. Only works on solid floor blocks.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">result</td>
<td class="org-left">[Liquid](#Liquid)</td>
<td class="org-right">water</td>
</tr>


<tr>
<td class="org-left">updateEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
</tr>


<tr>
<td class="org-left">updateEffectChance</td>
<td class="org-left">float</td>
<td class="org-right">0.02</td>
</tr>


<tr>
<td class="org-left">rotateSpeed</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">attribute</td>
<td class="org-left">[Attribute](#Attribute)</td>
<td class="org-right">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-liquid`


<a id="Cultivator"></a>

### Cultivator

Extends [GenericCrafter](#GenericCrafter)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">recurrence</td>
<td class="org-left">float</td>
<td class="org-right">6</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">craftEffect</td>
<td class="org-left">none</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-middle`
-   `<name>-top`


<a id="Fracker"></a>

### Fracker

Extends [SolidPump](#SolidPump)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">itemUseTime</td>
<td class="org-right">100</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-liquid`
-   `<name>-rotater`
-   `<name>-top`


<a id="Incinerator"></a>

### Incinerator

Extends [Block](#Block)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">effect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">fuelburn</td>
</tr>


<tr>
<td class="org-left">flameColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">ffad9d</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasPower</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">hasLiquid</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-right">true</td>
</tr>
</tbody>
</table>


<a id="Unit%20Blocks"></a>

## Unit Blocks


<a id="RepairPoint"></a>

### RepairPoint

Extends [Block](#Block) &#x2013; Block which can repair units within range, with a laser.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">repairRadius</td>
<td class="org-left">float</td>
<td class="org-right">50</td>
</tr>


<tr>
<td class="org-left">repairSpeed</td>
<td class="org-left">float</td>
<td class="org-right">0.3</td>
</tr>


<tr>
<td class="org-left">powerUse</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">outlineIcon</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">turret</td>
</tr>


<tr>
<td class="org-left">layer2</td>
<td class="org-left">power</td>
</tr>
</tbody>
</table>

Extra sprites:

-   `<name>-base`


<a id="UnitFactory"></a>

### UnitFactory

Extends [block](#Block) &#x2013; A block can produce units

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">produceTime</td>
<td class="org-left">float</td>
<td class="org-right">1000</td>
</tr>


<tr>
<td class="org-left">launchVelocity</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">maxSpawn</td>
<td class="org-left">int</td>
<td class="org-right">4</td>
</tr>


<tr>
<td class="org-left">unitType</td>
<td class="org-left">[UnitType](#UnitType)</td>
<td class="org-right">none</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">flags</td>
<td class="org-left">producer</td>
</tr>
</tbody>
</table>

Sprite suffix:

-   `-top`


<a id="CommandCenter"></a>

### CommandCenter

Extends [Block](#Block) &#x2013; A block which can issue commands to your unit.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">topColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">command</td>
</tr>


<tr>
<td class="org-left">bottomColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">5e5e5e</td>
</tr>


<tr>
<td class="org-left">effect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">commandSend</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">flags</td>
<td class="org-left">comandCenter</td>
</tr>


<tr>
<td class="org-left">destructible</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">configurable</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="MechPad"></a>

### MechPad

Extends [Block](#Block) &#x2013; A block which will spawn a player in a mech.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">mech</td>
<td class="org-left">[Mech](#Mech)</td>
<td class="org-left">none</td>
</tr>


<tr>
<td class="org-left">buildTime</td>
<td class="org-left">float</td>
<td class="org-left">60 \* 5</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasPower</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">overlay</td>
</tr>


<tr>
<td class="org-left">flags</td>
<td class="org-left">mechpad</td>
</tr>
</tbody>
</table>


<a id="Storage"></a>

## Storage


<a id="StorageBlock"></a>

### StorageBlock

[Abstract](#orgdb78fe9) type which extends [Block](#Block)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="CoreBlock"></a>

### CoreBlock

Extends [StorageBlock](#StorageBlock)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">mech</td>
<td class="org-left">Mech</td>
<td class="org-left">starter</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">activeSound</td>
<td class="org-left">respawning</td>
</tr>


<tr>
<td class="org-left">activeSoundVolume</td>
<td class="org-left">1</td>
</tr>


<tr>
<td class="org-left">layer</td>
<td class="org-left">overlay</td>
</tr>
</tbody>
</table>


<a id="Vault"></a>

### Vault

Extends [StorageBlock](#StorageBlock)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">destructible</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">false</td>
</tr>
</tbody>
</table>


<a id="Unloader"></a>

### Unloader

Extends [Block](#Block)

A block which can take items from [StorageBlock](#StorageBlock), like [Vault](#Vault), [CoreBlock](#CoreBlock) or [Crafters](#Crafting).

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">health</td>
<td class="org-left">70</td>
</tr>


<tr>
<td class="org-left">update</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">confugurable</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>-center`


<a id="LaunchPad"></a>

### LaunchPad

Extends [StroageBlock](#StorageBlock)

A block which can launch materials.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">launchTime</td>
<td class="org-left">float</td>
<td class="org-left">none</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">update</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">hasItems</td>
<td class="org-left">true</td>
</tr>


<tr>
<td class="org-left">solid</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="Attributes"></a>

## Attributes

An object with an array of [attribute](#Attribute). Used in the `Floor` type to give a tile specific properties, like *hottness* or *sporness* for efficiency of various systems, like ThermalPumps and WaterExtractors.

`array` has 4 items:

-   index `0` is `heat`,
-   index `1` is `spores`,
-   index `2` is `water`,
-   index `3` is `oil`.
    
    For example, this would give you `100` heat, `1` spores, `0.5` water and `0.1` oil.
    
        {
            "array": [ 100, 1, 0.5, 0.1]
        }
    
    You could use it inside of [Floor](#Floor) type as such:
    
        {
            "type": "Floor",
            "name": "magma",
            "attributes": { "array": [ 0.75, 0, 0, 0 ] }
        }


<a id="Attribute"></a>

## Attribute

New attributes cannot be added. List of built-in attributes:

-   `heat`
-   `spores`
-   `water`
-   `oil`


<a id="BuildVisibility"></a>

## BuildVisibility

A flag used by the game to change a few special-case things. It may be one of the following strings:

-   `hidden`
-   `shown`
-   `debugOnly`
-   `sandboxOnly`
-   `campaignOnly`
-   `lightingOnly`


<a id="BlockGroup"></a>

## BlockGroup

Groups for blocks to build on top of each other:

-   `none`
-   `walls`
-   `turrets`
-   `transportation`
-   `power`
-   `liquids`
-   `drills`


<a id="Type"></a>

# Type


<a id="Item"></a>

## Item

Extends [Content](#Content) &#x2013; It's the object that can ride conveyors, sorters and be stored in containers, and is commonly used in crafters.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">color</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">black</td>
<td class="org-left">hex string of color</td>
</tr>


<tr>
<td class="org-left">type</td>
<td class="org-left">[ItemType](#ItemType)</td>
<td class="org-right">resource</td>
<td class="org-left">used for tabs and core acceptance</td>
</tr>


<tr>
<td class="org-left">explosiveness</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">how explosive this item is.</td>
</tr>


<tr>
<td class="org-left">flammability</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">flammability above 0.3 makes this eleigible for item burners.</td>
</tr>


<tr>
<td class="org-left">radioactivity</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">how radioactive this item is. 0=none, 1=chernobyl ground zero</td>
</tr>


<tr>
<td class="org-left">hardness</td>
<td class="org-left">int</td>
<td class="org-right">0</td>
<td class="org-left">drill hardness of the item</td>
</tr>


<tr>
<td class="org-left">cost</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">used for calculating place times; 1 cost = 1 tick added to build time</td>
</tr>


<tr>
<td class="org-left">alwaysUnlocked</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">If true, item is always unlocked.</td>
</tr>
</tbody>
</table>


<a id="ItemType"></a>

### ItemType

-   `resource` can't go in the core;
-   `material` can go in the core.


<a id="ItemStack"></a>

## ItemStack

A `ItemStack` can be a string or an object. It's used to describe the type and amount of items to a machine.

As a `string`:

    copper/5

As an `object`:

    item: copper
    amount: 5

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">item</td>
<td class="org-left">string</td>
<td class="org-left">The name of an [Item](#Item).</td>
</tr>


<tr>
<td class="org-left">amount</td>
<td class="org-left">int</td>
<td class="org-left">The amount of said item.</td>
</tr>
</tbody>
</table>


<a id="Liquid"></a>

## Liquid

Extends [Content](#Content)

Type which defines the properties of a liquid. Like [Item](#Item) this will go into it's own subdirectory `content/liquids/liquid-name.json`, and from it's stem name you can reuse it from your other mod content.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">color</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">**[required]** color of liquid</td>
</tr>


<tr>
<td class="org-left">barColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">*[optional]* color used in bars.</td>
</tr>


<tr>
<td class="org-left">lightColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">Color used to draw lights. Note that the alpha channel is used to dictate brightness.</td>
</tr>


<tr>
<td class="org-left">flammability</td>
<td class="org-left">float</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">0 to 1; 0 is completely inflammable, above that may catch fire when exposed to heat.</td>
</tr>


<tr>
<td class="org-left">temperature</td>
<td class="org-left">float</td>
<td class="org-left">0.5</td>
<td class="org-left">0.5 is 'room' temperature, 0 is very cold, 1 is molten hot</td>
</tr>


<tr>
<td class="org-left">heatCapacity</td>
<td class="org-left">float</td>
<td class="org-left">0.5</td>
<td class="org-left">used in cooling; water is 0.4, cryofluid is 0.9.</td>
</tr>


<tr>
<td class="org-left">viscosity</td>
<td class="org-left">float</td>
<td class="org-left">0.5</td>
<td class="org-left">how thick this liquid is; water is 0.5, oil is 0.7.</td>
</tr>


<tr>
<td class="org-left">explosiveness</td>
<td class="org-left">float</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">explosiveness when heated; 0 is nothing, 1 is nuke</td>
</tr>


<tr>
<td class="org-left">effect</td>
<td class="org-left">[StatusEffect](#StatusEffect)</td>
<td class="org-left">none</td>
<td class="org-left">the associated status effect.</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>`, the sprite used when displaying the liquid from a menu.


<a id="LiquidStack"></a>

## LiquidStack

A `LiquidStack` can be a string or an object. It's used to describe the type and amount of liquid to a machine.

As a `string`:

    water/0.5

As an `object`:

    liquid: water
    amount: 0.5

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">liquid</td>
<td class="org-left">string</td>
<td class="org-left">The name of a [Liquid](#Liquid).</td>
</tr>


<tr>
<td class="org-left">amount</td>
<td class="org-left">float</td>
<td class="org-left">The amount of said liquid.</td>
</tr>
</tbody>
</table>


<a id="Weapon"></a>

## Weapon

Weapons are used by units and mechs alike. A weapon is a type used to shoot bullets [bullets](#BulletType) just like turrets *(except that they don't have an `ammo` mapping)*. Weapons can only shoot one type of bullet, which you define in the `bullet` field.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">name</td>
<td class="org-left">String</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">used to fetch the sprite of the weapon</td>
</tr>


<tr>
<td class="org-left">nimPlayerDist</td>
<td class="org-left">float</td>
<td class="org-right">20</td>
<td class="org-left">minimum cursor distance from player, fixes 'cross-eyed' shooting.</td>
</tr>


<tr>
<td class="org-left">sequenceNum</td>
<td class="org-left">int</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">bullet</td>
<td class="org-left">[BulletType](#BulletType)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">bullet shot</td>
</tr>


<tr>
<td class="org-left">ejectEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">none</td>
<td class="org-left">shell ejection effect</td>
</tr>


<tr>
<td class="org-left">reload</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">weapon reload in frames</td>
</tr>


<tr>
<td class="org-left">shots</td>
<td class="org-left">int</td>
<td class="org-right">1</td>
<td class="org-left">amount of shots per fire</td>
</tr>


<tr>
<td class="org-left">spacing</td>
<td class="org-left">float</td>
<td class="org-right">12</td>
<td class="org-left">spacing in degrees between multiple shots, if applicable</td>
</tr>


<tr>
<td class="org-left">inaccuracy</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">inaccuracy of degrees of each shot</td>
</tr>


<tr>
<td class="org-left">shake</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">intensity and duration of each shot's screen shake</td>
</tr>


<tr>
<td class="org-left">recoil</td>
<td class="org-left">float</td>
<td class="org-right">1.5</td>
<td class="org-left">visual weapon knockback.</td>
</tr>


<tr>
<td class="org-left">length</td>
<td class="org-left">float</td>
<td class="org-right">3</td>
<td class="org-left">shoot barrel y offset</td>
</tr>


<tr>
<td class="org-left">width</td>
<td class="org-left">float</td>
<td class="org-right">4</td>
<td class="org-left">shoot barrel x offset.</td>
</tr>


<tr>
<td class="org-left">velocityRnd</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">fraction of velocity that is random</td>
</tr>


<tr>
<td class="org-left">alternate</td>
<td class="org-left">bool</td>
<td class="org-right">false</td>
<td class="org-left">shoot one arm after another, rather than all at once</td>
</tr>


<tr>
<td class="org-left">lengthRand</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">randomization of shot length</td>
</tr>


<tr>
<td class="org-left">shotDelay</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">delay in ticks between shots</td>
</tr>


<tr>
<td class="org-left">ignoreRotation</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">whether shooter rotation is ignored when shooting.</td>
</tr>


<tr>
<td class="org-left">shootSound</td>
<td class="org-left">[Sound](#Sound)</td>
<td class="org-right">pew</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Sprite:

-   `<name>` or `<name>-equip`


<a id="UnitType"></a>

## UnitType

Extends [Content](#Content)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">type</td>
<td class="org-left">[BaseUnit](#BaseUnit)</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">health</td>
<td class="org-left">float</td>
<td class="org-right">60</td>
</tr>


<tr>
<td class="org-left">hitsize</td>
<td class="org-left">float</td>
<td class="org-right">7</td>
</tr>


<tr>
<td class="org-left">hitsizeTile</td>
<td class="org-left">float</td>
<td class="org-right">4</td>
</tr>


<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">0.4</td>
</tr>


<tr>
<td class="org-left">range</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">attackLength</td>
<td class="org-left">float</td>
<td class="org-right">150</td>
</tr>


<tr>
<td class="org-left">rotatespeed</td>
<td class="org-left">float</td>
<td class="org-right">0.2</td>
</tr>


<tr>
<td class="org-left">baseRotateSpeed</td>
<td class="org-left">float</td>
<td class="org-right">0.1</td>
</tr>


<tr>
<td class="org-left">shootCone</td>
<td class="org-left">float</td>
<td class="org-right">15</td>
</tr>


<tr>
<td class="org-left">mass</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">flying</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">targetAir</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">rotateWeapon</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">drag</td>
<td class="org-left">float</td>
<td class="org-right">0.1</td>
</tr>


<tr>
<td class="org-left">maxVelocity</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">retreatPercent</td>
<td class="org-left">float</td>
<td class="org-right">0.6</td>
</tr>


<tr>
<td class="org-left">itemCapacity</td>
<td class="org-left">int</td>
<td class="org-right">30</td>
</tr>


<tr>
<td class="org-left">buildPower</td>
<td class="org-left">float</td>
<td class="org-right">0.3</td>
</tr>


<tr>
<td class="org-left">minePower</td>
<td class="org-left">float</td>
<td class="org-right">0.7</td>
</tr>


<tr>
<td class="org-left">weapon</td>
<td class="org-left">[Weapon](#Weapon)</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">weaponOffsetY</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">engineOffset</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">engineSize</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>`
-   `<name>-leg`
-   `<name>-base`


<a id="Mech"></a>

## Mech

Extends [Content](#Content)

Mechs are the player controlled entities. They shoot [bullets](#BulletType) just like turrets from their [weapon](#Weapon).

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">flying</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
</tr>


<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">1.1</td>
</tr>


<tr>
<td class="org-left">maxSpeed</td>
<td class="org-left">float</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">boostSpeed</td>
<td class="org-left">float</td>
<td class="org-right">0.75</td>
</tr>


<tr>
<td class="org-left">drag</td>
<td class="org-left">float</td>
<td class="org-right">0.4</td>
</tr>


<tr>
<td class="org-left">mass</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">shake</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">health</td>
<td class="org-left">float</td>
<td class="org-right">200</td>
</tr>


<tr>
<td class="org-left">hitsize</td>
<td class="org-left">float</td>
<td class="org-right">6</td>
</tr>


<tr>
<td class="org-left">cellTrnsY</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">mineSpeed</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">drillPower</td>
<td class="org-left">int</td>
<td class="org-right">-1</td>
</tr>


<tr>
<td class="org-left">buildPower</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">engineColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">boostTo</td>
</tr>


<tr>
<td class="org-left">itemCapacity</td>
<td class="org-left">int</td>
<td class="org-right">30</td>
</tr>


<tr>
<td class="org-left">turnCursor</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
</tr>


<tr>
<td class="org-left">canHeal</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
</tr>


<tr>
<td class="org-left">compoundSpeed</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">compoundSpeedBoost</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">weaponOffsetY</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">engineOffset</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-left">engineSize</td>
<td class="org-left">float</td>
<td class="org-right">2.5</td>
</tr>


<tr>
<td class="org-left">weapon</td>
<td class="org-left">[Weapon](#Weapon)</td>
<td class="org-right">null</td>
</tr>
</tbody>
</table>

Sprites:

-   `<name>`
-   `<name>-leg`
-   `<name>-base`


<a id="Category"></a>

## Category

Categories for building menu:

-   `turret` Offensive turrets;
-   `production` Blocks that produce raw resources, such as drills;
-   `distribution` Blocks that move items around;
-   `liquid` Blocks that move liquids around;
-   `power` Blocks that generate or transport power;
-   `defense` Walls and other defensive structures;
-   `crafting` Blocks that craft things;
-   `units` Blocks that create units;
-   `upgrade` Things that upgrade the player such as mech pads;
-   `effect` Things for storage or passive effects.


<a id="Zone"></a>

## Zone

Extends [Content](#Content)

A `Zone` is a type that takes a map *(named the same as the json's filename)* and puts it into campaign. *(a zone isn't a map)*

Every `Zone` has a `Generator`, which once initialized, `MapGenerator` will run through the map and do *initialization related stuff.* One of those notable things, is deleting all cores on in your map and placing a `loadout` on top of a random one of them. This allows your campaign map to have multiple core locations. *(it doesn't matter which core was previously on the map, `loadout` will dictate that)*

It is entirely possible to produce a custom schematic, but take note that this schematic must contain a `CoreBlock` within it.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">baseLaunchCost</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">launchCost</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">startingItems</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">Items you start with on the map.</td>
</tr>


<tr>
<td class="org-left">conditionWave</td>
<td class="org-left">int</td>
<td class="org-left">MAX<sub>VALUE</sub></td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">alwaysUnlocked</td>
<td class="org-left">boolean</td>
<td class="org-left">false</td>
<td class="org-left">Whether this map is always unlocked</td>
</tr>


<tr>
<td class="org-left">launchPeriod</td>
<td class="org-left">int</td>
<td class="org-left">10</td>
<td class="org-left">Rate of waves at which the core may be launched.</td>
</tr>


<tr>
<td class="org-left">loadout</td>
<td class="org-left">[Schematic](#Schematic)</td>
<td class="org-left">basicShard</td>
<td class="org-left">Core layout placed by MapGenerators.</td>
</tr>


<tr>
<td class="org-left">resources</td>
<td class="org-left">[ String ]</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">Array of [item](#Item) names.</td>
</tr>


<tr>
<td class="org-left">requirements</td>
<td class="org-left">[ [Objective](#Objective) ]</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">An array of requirements to unlock configuration.</td>
</tr>


<tr>
<td class="org-left">configureObjective</td>
<td class="org-left">[Objective](#Objective)</td>
<td class="org-left">ZoneWave 15</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">defaultStartingItems</td>
<td class="org-left">[ [ItemStack](#ItemStack) ]</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Sprites:

-   `zone-<name>` preview
-   `<name>-zone` preview

Built-in loadouts:

-   basicShard
    
        bXNjaAB4nD2K2wqAIBiD5ymibnoRn6YnEP1BwUMoBL19FuJ2sbFvUFgYZDaJsLeQrkinN9UJHImsNzlYE7WrIUastuSbnlKx2VJJt+8IQGGKdfO/8J5yrGJSMegLg+YUIA==
    
    ![img](img/basicShard.png)

-   advancedShard
    
        bXNjaAB4nD2LjQqAIAyET7OMIOhFfJqeYMxBgSkYCL199gu33fFtB4tOwUTaBCP5QpHFzwtl32DahBeKK1NwPq8hoOcUixwpY+CUxe3XIwBbB/pa6tadVCUP02hgHvp5vZq/0b7pBHPYFOQ=
    
    ![img](img/advancedShard.png)

-   basicFoundation
    
        bXNjaAB4nD1OSQ6DMBBzFhVu8BG+0X8MQyoiJTNSukj8nlCi2Adbtg/GA4OBF8oB00rvyE/9ykafqOIw58A7SWRKy1ZiShhZ5RcOLZhYS1hefQ1gRIeptH9jq/qW2lvc1d2tgWsOfVX/tOwE86AYBA==
    
    ![img](img/basicFoundation.png)

-   basicNucleus
    
        bXNjaAB4nD2MUQqAIBBEJy0s6qOLdJXuYNtCgikYBd2+LNmdj308hkGHtkId7M4YFns4mk/yfB4a48602eDI+mlNznu0FMPFd0wYKCaewl8F0EOueqM+yKSLVfJrNKWnSw/FZGzEGXFG9sy/px4gEBW1
    
    ![img](img/basicNucleus.png)

Built-in zones:

-   nuclearComplexe
-   desolateRift
-   tarFields
-   overgrowth
-   stainedMountains
-   frozenForest
-   saltFlats
-   desertWastes
-   groundZero


<a id="StatusEffect"></a>

## StatusEffect

*Not be be confused with [Effect](#Effect)*, a status effect will give an entity special properties. It is currently **not possible to add custom status effects**. &#x2013; Status effects are used as transitions between intermediate effects. If some a `wet` unit gets `shocked` it then gets 20 damage.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">damageMultiplier</td>
<td class="org-left">float</td>
<td class="org-left">1</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">armorMultiplier</td>
<td class="org-left">float</td>
<td class="org-left">1</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">speedMultiplier</td>
<td class="org-left">float</td>
<td class="org-left">1</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">color</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-left">white</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">damage</td>
<td class="org-left">float</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">Damage (or healing) per frame.</td>
</tr>


<tr>
<td class="org-left">effect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">none</td>
<td class="org-left">Random effect (0.15% per frame), on affected units.</td>
</tr>
</tbody>
</table>

-   opposites: effect which reduces anothers lifetime.

Built-in status effects:

-   `none` &#x2013; Does nothing.

-   `burning`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-left">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">damage</td>
    <td class="org-left">0.06</td>
    </tr>
    
    
    <tr>
    <td class="org-left">effect</td>
    <td class="org-left">burning</td>
    </tr>
    </tbody>
    </table>
    
    -   opposites: `wet` `freezing`
    -   tarred: 1 damage and keeps burning

-   `freezing`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-right">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">speedMultiplier</td>
    <td class="org-right">0.6</td>
    </tr>
    
    
    <tr>
    <td class="org-left">armorMultiplier</td>
    <td class="org-right">0.8</td>
    </tr>
    
    
    <tr>
    <td class="org-left">effect</td>
    <td class="org-right">freezing</td>
    </tr>
    </tbody>
    </table>
    
    -   opposites: `melting` `burning`

-   `wet`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-left">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">speedMultiplier</td>
    <td class="org-left">0.9</td>
    </tr>
    
    
    <tr>
    <td class="org-left">effect</td>
    <td class="org-left">wet</td>
    </tr>
    </tbody>
    </table>
    
    -   opposites: `burning`
    -   shocked: 20 damage

-   `melting`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-right">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">speedMultiplier</td>
    <td class="org-right">0.8</td>
    </tr>
    
    
    <tr>
    <td class="org-left">armorMultiplier</td>
    <td class="org-right">0.8</td>
    </tr>
    
    
    <tr>
    <td class="org-left">damage</td>
    <td class="org-right">0.3</td>
    </tr>
    
    
    <tr>
    <td class="org-left">effect</td>
    <td class="org-right">melting</td>
    </tr>
    </tbody>
    </table>
    
    -   opposites: `wet` `freezing`
    -   tarred: keeps melting

-   `tarred`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-left">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">speedMultiplier</td>
    <td class="org-left">0.6</td>
    </tr>
    
    
    <tr>
    <td class="org-left">effect</td>
    <td class="org-left">oily</td>
    </tr>
    </tbody>
    </table>
    
    -   burning: keeps burning
    -   melting: keeps burning

-   `overdrive`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-right">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">armorMultiplier</td>
    <td class="org-right">0.95</td>
    </tr>
    
    
    <tr>
    <td class="org-left">speedMultiplier</td>
    <td class="org-right">1.15</td>
    </tr>
    
    
    <tr>
    <td class="org-left">damageMultiplier</td>
    <td class="org-right">1.4</td>
    </tr>
    
    
    <tr>
    <td class="org-left">damage</td>
    <td class="org-right">-0.01</td>
    </tr>
    
    
    <tr>
    <td class="org-left">effect</td>
    <td class="org-right">overdriven</td>
    </tr>
    </tbody>
    </table>

-   `shielded`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-right">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">armorMultiplier</td>
    <td class="org-right">3</td>
    </tr>
    </tbody>
    </table>

-   `boss`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-right">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">armorMultiplier</td>
    <td class="org-right">3</td>
    </tr>
    
    
    <tr>
    <td class="org-left">damageMultiplier</td>
    <td class="org-right">3</td>
    </tr>
    
    
    <tr>
    <td class="org-left">speedMultiplier</td>
    <td class="org-right">1.1</td>
    </tr>
    </tbody>
    </table>

-   `shocked` &#x2013; Does nothing.

-   `corroded`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-right">value</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">damage</td>
    <td class="org-right">0.1</td>
    </tr>
    </tbody>
    </table>


<a id="Graphics"></a>

# Graphics


<a id="Layer"></a>

## Layer

Layers is an enumeration type, which the renderer will use to group rendering order:

-   `block`, base block layer;
-   `placement`, for placement;
-   `overlay`, first overlay stuff like conveyor items;
-   `turret`, "high" blocks like turrets;
-   `power` power lasers


<a id="Color"></a>

## Color

Color is a hexadecimal string, `<rr><gg><bb>` for example:

-   `ff0000` is red,
-   `00ff00` is green,
-   `0000ff` is blue,
-   `ffff00` is yellow,
-   `00ffff` is cyan,
-   *ect..*


<a id="CacheLayer"></a>

## CacheLayer

Flags used by for cache render:

-   `normal` normal layer;
-   `walls` walls layer;
-   `water` water layer, adding tile water shaders, and giving wave reflections;
-   `tar` tar layer, adding tar shaders, making it darker and giving it some bubble reflections;


<a id="Entities"></a>

# Entities


<a id="BulletType"></a>

## BulletType

[Abstract](#orgdb78fe9) type which extends [Content](#Content)

BulletType can either be an object `{}` or a `"string"`, where a string would be reusing [Built-in Bullets](#Built-in%20Bullets) and an object would be making a custom one.

There are two major categories of bullet types:

-   [BasicBulletType](#BasicBulletType) and,
-   other special bullets.

Here's an example of a custom bullet:

    {
        "type": "MissileBulletType",
        "lifetime": 1000,
        "speed": 2,
        "splashDamageRadius": 2,
        "splashDamage": 9,
        "frontColor": "ffff00",
        "backColor": "00ffff",
        "homingPower": 1,
        "homingRange": 20,
        "fragBullets": 3,
        "fragBullet": {
            "type": "LiquidBulletType"
            "liquid": "oil",
            "lifetime": 2,
            "speed": 1,
            "fragBullets": 2,
            "fragBullet": {
                "type": "LiquidBulletType"
                "liquid": "slag",
                "lifetime": 1,
                "speed": 2,
                "damage": 1,
            }
        }
    }

![img](img/green-cyan-oil-slag-missiles.png)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">lifetime</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">amount of ticks it will lasts</td>
</tr>


<tr>
<td class="org-left">speed</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">inital speed of bullet</td>
</tr>


<tr>
<td class="org-left">damage</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">collision damage</td>
</tr>


<tr>
<td class="org-left">hitSize</td>
<td class="org-left">float</td>
<td class="org-right">4</td>
<td class="org-left">collision radius</td>
</tr>


<tr>
<td class="org-left">drawSize</td>
<td class="org-left">float</td>
<td class="org-right">40</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">drag</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">decelleration per tick</td>
</tr>


<tr>
<td class="org-left">pierce</td>
<td class="org-left">boolean</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">whether it can collide</td>
</tr>


<tr>
<td class="org-left">hitEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">created when bullet hits something</td>
</tr>


<tr>
<td class="org-left">despawnEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">created when bullet despawns</td>
</tr>


<tr>
<td class="org-left">shootEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">created when shooting</td>
</tr>


<tr>
<td class="org-left">smokeEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">created when shooting</td>
</tr>


<tr>
<td class="org-left">hitSound</td>
<td class="org-left">Sound</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">made when hitting something or getting removed</td>
</tr>


<tr>
<td class="org-left">inaccuracy</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">extra inaccuracy</td>
</tr>


<tr>
<td class="org-left">ammoMultiplier</td>
<td class="org-left">float</td>
<td class="org-right">2</td>
<td class="org-left">how many bullets get created per item/liquid</td>
</tr>


<tr>
<td class="org-left">reloadMultiplier</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">multiplied by turret reload speed</td>
</tr>


<tr>
<td class="org-left">recoil</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">recoil from shooter entities</td>
</tr>


<tr>
<td class="org-left">knockback</td>
<td class="org-left">float</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">Knockback in velocity.</td>
</tr>


<tr>
<td class="org-left">hitTiles</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this bullet hits tiles.</td>
</tr>


<tr>
<td class="org-left">status</td>
<td class="org-left">[StatusEffect](#StatusEffect)</td>
<td class="org-right">none</td>
<td class="org-left">Status effect applied on hit.</td>
</tr>


<tr>
<td class="org-left">statusDuration</td>
<td class="org-left">float</td>
<td class="org-right">600</td>
<td class="org-left">Intensity of applied status effect in terms of duration.</td>
</tr>


<tr>
<td class="org-left">collidesTiles</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this bullet type collides with tiles.</td>
</tr>


<tr>
<td class="org-left">collidesTeam</td>
<td class="org-left">boolean</td>
<td class="org-right">false</td>
<td class="org-left">Whether this bullet type collides with tiles that are of the same team.</td>
</tr>


<tr>
<td class="org-left">collidesAir</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this bullet type collides with air units.</td>
</tr>


<tr>
<td class="org-left">collides</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether this bullet types collides with anything at all.</td>
</tr>


<tr>
<td class="org-left">keepVelocity</td>
<td class="org-left">boolean</td>
<td class="org-right">true</td>
<td class="org-left">Whether velocity is inherited from the shooter.</td>
</tr>


<tr>
<td class="org-left">fragBullets</td>
<td class="org-left">int</td>
<td class="org-right">9</td>
<td class="org-left">Number of frag bullets created.</td>
</tr>


<tr>
<td class="org-left">fragVelocityMin</td>
<td class="org-left">float</td>
<td class="org-right">0.2</td>
<td class="org-left">Minimum random multiplier.</td>
</tr>


<tr>
<td class="org-left">fragVelocityMax</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">Maximum random multiplier.</td>
</tr>


<tr>
<td class="org-left">fragBullet</td>
<td class="org-left">[BulletType](#BulletType)</td>
<td class="org-right">null</td>
<td class="org-left">The frag bullet that will be created, may be a string, an object or null. If field is null, no frag bullet is created.</td>
</tr>


<tr>
<td class="org-left">splashDamage</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">Area of effect damage when the bullet despawns or hits a target. Damage is calculated with [linear interpolation](https://en.wikipedia.org/wiki/Linear_interpolation), also known as lerp.</td>
</tr>


<tr>
<td class="org-left">splashDamageRadius</td>
<td class="org-left">float</td>
<td class="org-right">-1</td>
<td class="org-left">Use a negative value to disable splash damage. `splashDamageRadius` is a value used in the equation `lerp(1 - distance / radius, 1, 0.4)` which is a multiplier for `splashDamage`.</td>
</tr>


<tr>
<td class="org-left">incendAmount</td>
<td class="org-left">int</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">incendSpread</td>
<td class="org-left">float</td>
<td class="org-right">8</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">incendChance</td>
<td class="org-left">float</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">homingPower</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">Doesn't do anything complicated; if `homingPower` larger then `0.01` it gets rendered in the UI, if `homingPower` is larger then `0.0001` it allows `homingRange` to work.</td>
</tr>


<tr>
<td class="org-left">homingRange</td>
<td class="org-left">float</td>
<td class="org-right">50</td>
<td class="org-left">How close the bullet needs from a target in order to home/seek said target.</td>
</tr>


<tr>
<td class="org-left">lightining</td>
<td class="org-left">int</td>
<td class="org-right">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">lightningLength</td>
<td class="org-left">int</td>
<td class="org-right">5</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">hitShake</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="BasicBulletType"></a>

### BasicBulletType

Extends [BulletType](#BulletType)

This types purpose is to give basic bullets their sprites. The `bulletSprite` will be used as the shape of the bullet. The visible pixels in your sprites will be tinted with `backColor` and `frontColor` respectively. For example if you had sprites `router.png` and `router-back.png` where `Test Mod` was your mods name, you could do this to include your `bulletSprite`:

    {
        "type": "BasicBulletType",
        "bulletSprite": "test-mod-router"
    }

![img](img/router-bullets.png)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">bulletWidth</td>
<td class="org-left">float</td>
<td class="org-right">5</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">bulletHeight</td>
<td class="org-left">float</td>
<td class="org-right">7</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">bulletShrink</td>
<td class="org-left">float</td>
<td class="org-right">0.5</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">frontColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">bulletYellow</td>
<td class="org-left">Color of front sprite.</td>
</tr>


<tr>
<td class="org-left">backColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">bulletYellowBack</td>
<td class="org-left">Color of back sprite.</td>
</tr>


<tr>
<td class="org-left">bulletSprite</td>
<td class="org-left">String</td>
<td class="org-right">bullet</td>
<td class="org-left">Mapping sprite used to make the shape of the bullet.</td>
</tr>
</tbody>
</table>

Sprites:

-   `<mod-name>-<sprite-name>` top layer `bulletSprite`
-   `<mod-name>-<sprite-name>-back` bottom layer `bulletSprite`

Built-in `bulletSprites`:

-   [bullet](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/effects/bullet.png)
-   [bullet-back](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/effects/bullet-back.png)
-   [missile](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/effects/missile.png)
-   [missile-back](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/effects/missile-back.png)
-   [shell](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/effects/shell.png)
-   [shell-back](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/effects/shell-back.png)


<a id="ArtilleryBulletType"></a>

#### ArtilleryBulletType

Extends [BasicBulletType](#BasicBulletType)

Makes special calculations to give the effect that the bullet is going up and back down.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">trailEffect</td>
<td class="org-left">[Effect](#Effect)</td>
<td class="org-left">artilleryTrail</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">collidesTiles</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">collides</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">collidesAir</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">hitShake</td>
<td class="org-left">1</td>
</tr>


<tr>
<td class="org-left">hitSound</td>
<td class="org-left">explosion</td>
</tr>


<tr>
<td class="org-left">bulletSprite</td>
<td class="org-left">shell</td>
</tr>
</tbody>
</table>


<a id="FlakBulletType"></a>

#### FlakBulletType

Extends [BasicBulletType](#BasicBulletType)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">explodeRange</td>
<td class="org-left">float</td>
<td class="org-right">30</td>
<td class="org-left">The range at which the bullets explode from enemies.</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-right">type</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">splashDamage</td>
<td class="org-right">15</td>
</tr>


<tr>
<td class="org-left">splashDamageRadius</td>
<td class="org-right">34</td>
</tr>


<tr>
<td class="org-left">hitEffect</td>
<td class="org-right">flakExplosionBig</td>
</tr>


<tr>
<td class="org-left">bulletWidth</td>
<td class="org-right">8</td>
</tr>


<tr>
<td class="org-left">bulletHeight</td>
<td class="org-right">10</td>
</tr>
</tbody>
</table>


<a id="MissileBulletType"></a>

#### MissileBulletType

Extends [BasicBulletType](#BasicBulletType)

Weave is simple a sin wave with the following equation.

    rotation = sin(time/scale) * magnitude

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">trailColor</td>
<td class="org-left">[Color](#Color)</td>
<td class="org-right">missileYellowBack</td>
<td class="org-left">Color of the trail effect.</td>
</tr>


<tr>
<td class="org-left">weaveScale</td>
<td class="org-left">float</td>
<td class="org-right">0</td>
<td class="org-left">A larger `weaveScale` means a longer wave.</td>
</tr>


<tr>
<td class="org-left">weaveMag</td>
<td class="org-left">float</td>
<td class="org-right">-1</td>
<td class="org-left">A higher `weaveMag` means a higher (wider) wave.</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">bulletSprite</td>
<td class="org-left">missile</td>
</tr>
</tbody>
</table>


<a id="BombBulletType"></a>

#### BombBulletType

Extends [BasicBulletType](#BasicBulletType)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">collidesTiles</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">collides</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">bulletShrink</td>
<td class="org-left">0.7</td>
</tr>


<tr>
<td class="org-left">lifetime</td>
<td class="org-left">30</td>
</tr>


<tr>
<td class="org-left">drag</td>
<td class="org-left">0.05</td>
</tr>


<tr>
<td class="org-left">keepVelocity</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">collidesAir</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">hitSound</td>
<td class="org-left">explosion</td>
</tr>
</tbody>
</table>


<a id="HealBulletType"></a>

### HealBulletType

Extends [BulletType](#BulletType) &#x2013; Bullets that can heal blocks of the same team as the shooter.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-right">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">healPercent</td>
<td class="org-left">float</td>
<td class="org-right">3</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">shootEffect</td>
<td class="org-left">shootHeal</td>
</tr>


<tr>
<td class="org-left">smokeEffect</td>
<td class="org-left">hitLaser</td>
</tr>


<tr>
<td class="org-left">hitEffect</td>
<td class="org-left">hitLaser</td>
</tr>


<tr>
<td class="org-left">despawnEffect</td>
<td class="org-left">hitLaser</td>
</tr>


<tr>
<td class="org-left">collidesTeam</td>
<td class="org-left">true</td>
</tr>
</tbody>
</table>


<a id="LiquidBulletType"></a>

### LiquidBulletType

Extends [BulletType](#BulletType)

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">type</th>
<th scope="col" class="org-left">default</th>
<th scope="col" class="org-left">notes</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">liquid</td>
<td class="org-left">String</td>
<td class="org-left">null</td>
<td class="org-left">**[required]** name of [Liquid](#Liquid)</td>
</tr>
</tbody>
</table>

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">lifetime</td>
<td class="org-left">74</td>
</tr>


<tr>
<td class="org-left">statusDuration</td>
<td class="org-left">90</td>
</tr>


<tr>
<td class="org-left">despawnEffect</td>
<td class="org-left">none</td>
</tr>


<tr>
<td class="org-left">hitEffect</td>
<td class="org-left">hitLiquid</td>
</tr>


<tr>
<td class="org-left">smokeEffect</td>
<td class="org-left">none</td>
</tr>


<tr>
<td class="org-left">shootEffect</td>
<td class="org-left">none</td>
</tr>


<tr>
<td class="org-left">drag</td>
<td class="org-left">0.009</td>
</tr>


<tr>
<td class="org-left">knockback</td>
<td class="org-left">0.55</td>
</tr>
</tbody>
</table>


<a id="MassDriverBolt"></a>

### MassDriverBolt

Extends [BulletType](#BulletType)

Defaults:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">field</th>
<th scope="col" class="org-left">default</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">collidesTiles</td>
<td class="org-left">false</td>
</tr>


<tr>
<td class="org-left">lifetime</td>
<td class="org-left">200</td>
</tr>


<tr>
<td class="org-left">despawnEffect</td>
<td class="org-left">smeltsmoke</td>
</tr>


<tr>
<td class="org-left">hitEffect</td>
<td class="org-left">hitBulletBig</td>
</tr>


<tr>
<td class="org-left">drag</td>
<td class="org-left">0.005</td>
</tr>
</tbody>
</table>


<a id="Built-in%20Bullets"></a>

### Built-in Bullets

-   artillery:
    -   `artilleryDense` `arilleryPlastic` `artilleryPlasticFrag` `artilleryHoming` `artlleryIncendiary` `artilleryExplosive` `artilleryUnit`
-   flak:
    -   `flakScrap` `flakLead` `flakPlastic` `flakExplosive` `flakSurge` `flakGlass` `glassFrag`
-   missiles:
    -   `missileExplosive` `missileIncendiary` `missileSurge` `missileJavelin` `missileSwarm` `missileRevenant`
-   standard:
    -   `standardCopper` `standardDense` `standardThorium` `standardHoming` `standardIncendiary` `standardMechSmall` `standardGlaive` `standardDenseBig` `standardThoriumBig` `standardIncendiaryBig`
-   electric:
    -   `lancerLaser` `meltdownLaser` `lightning` `arc` `damageLightning`
-   liquid:
    -   `waterShot` `cryoShot` `slagShot` `oilShot`
-   environment & misc:
    -   `fireball` `basicFlame` `pyraFlame` `driverBolt` `healBullet` `healBulletBig` `frag` `eruptorShot`
-   bombs:
    -   `bombExplosive` `bombIncendiary` `bombOil`


<a id="BaseUnit"></a>

## BaseUnit

There are a few useful base unit types:

-   `FlyingUnit`
    -   `HoverUnit`
    -   `BuilderDrone`
    -   `MinerDrone`
    -   `RepairDrone`
-   `GroundUnit`


<a id="Effect"></a>

## Effect

Type should be a `string`. You can't currently create custom effects. List of built-in effects are as follows:

-   `none` `placeBlock` `breakBlock` `smoke` `spawn` `tapBlock` `select`
-   `vtolHover` `unitDrop` `unitPickup` `unitLand` `pickup` `healWave` `heal`
    `landShock` `reactorsmoke` `nuclearsmoke` `nuclearcloud`
-   `redgeneratespark` `generatespark` `fuelburn` `plasticburn` `pulverize`
    `pulverizeRed` `pulverizeRedder` `pulverizeSmall` `pulverizeMedium`
-   `producesmoke` `smeltsmoke` `formsmoke` `blastsmoke` `lava` `doorclose`
    `dooropen` `dooropenlarge` `doorcloselarge` `purify` `purifyoil` `purifystone` `generate`
-   `mine` `mineBig` `mineHuge` `smelt` `teleportActivate` `teleport` `teleportOut` `ripple` `bubble` `launch`
-   `healBlock` `healBlockFull` `healWaveMend` `overdriveWave` `overdriveBlockFull` `shieldBreak` `hitBulletSmall` `hitFuse`
-   `hitBulletBig` `hitFlameSmall` `hitLiquid` `hitLaser` `hitLancer` `hitMeltdown` `despawn` `flakExplosion` `blastExplosion`
-   `plasticExplosion` `artilleryTrail` `incendTrail` `missileTrail` `absorb` `flakExplosionBig` `plasticExplosionFlak` `burning` `fire`
-   `fireSmoke` `steam` `fireballsmoke` `ballfire` `freezing` `melting` `wet` `oily` `overdriven` `dropItem` `shockwave`
-   `bigShockwave` `nuclearShockwave` `explosion` `blockExplosion`
    `blockExplosionSmoke` `shootSmall` `shootHeal` `shootSmallSmoke` `shootBig` `shootBig2` `shootBigSmoke`
-   `shootBigSmoke2` `shootSmallFlame` `shootPyraFlame` `shootLiquid` `shellEjectSmall` `shellEjectMedium`
-   `shellEjectBig` `lancerLaserShoot` `lancerLaserShootSmoke` `lancerLaserCharge`
    `lancerLaserChargeBegin` `lightningCharge` `lightningShoot`
-   `unitSpawn` `spawnShockwave` `magmasmoke` `impactShockwave`
    `impactcloud` `impactsmoke` `dynamicExplosion` `padlaunch` `commandSend` `coreLand`


<a id="TargetPriority"></a>

## TargetPriority

-   `base`
-   `turret`


<a id="Objective"></a>

# Objective

Objective is a trait, which a few types implement, which is used by [Zone](#Zone) to give campaign maps objectives.

Types which implement Objective are as follows:

-   `ZoneWave` &#x2013; complete if best wave within `zone` is heigher then target `wave`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-left">type</th>
    <th scope="col" class="org-left">notes</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">zone</td>
    <td class="org-left">String</td>
    <td class="org-left">target [Zone](#Zone) name</td>
    </tr>
    
    
    <tr>
    <td class="org-left">wave</td>
    <td class="org-left">int</td>
    <td class="org-left">target wave to reach</td>
    </tr>
    </tbody>
    </table>

-   `Launched` &#x2013; complete if core launched from `zone`
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-left">type</th>
    <th scope="col" class="org-left">notes</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">zone</td>
    <td class="org-left">String</td>
    <td class="org-left">target [Zone](#Zone) name</td>
    </tr>
    </tbody>
    </table>

-   `Unlock` &#x2013; complete if `block` is unlocked
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <thead>
    <tr>
    <th scope="col" class="org-left">field</th>
    <th scope="col" class="org-left">type</th>
    <th scope="col" class="org-left">notes</th>
    </tr>
    </thead>
    
    <tbody>
    <tr>
    <td class="org-left">block</td>
    <td class="org-left">String</td>
    <td class="org-left">target [Block](#Block) name</td>
    </tr>
    </tbody>
    </table>


<a id="Other"></a>

# Other


<a id="Mindustry%20Source%20Structure"></a>

## Mindustry Source Structure

    core/src/io/anuke/mindustry/
    ├── ai
    │   ├── BlockIndexer.java
    │   ├── Pathfinder.java
    │   └── WaveSpawner.java
    ├── ClientLauncher.java
    ├── content
    │   ├── Blocks.java
    │   ├── Bullets.java
    │   ├── Fx.java
    │   ├── Items.java
    │   ├── Liquids.java
    │   ├── Loadouts.java
    │   ├── Mechs.java
    │   ├── StatusEffects.java
    │   ├── TechTree.java
    │   ├── TypeIDs.java
    │   ├── UnitTypes.java
    │   └── Zones.java
    ├── core
    │   ├── ContentLoader.java
    │   ├── Control.java
    │   ├── FileTree.java
    │   ├── GameState.java
    │   ├── Logic.java
    │   ├── NetClient.java
    │   ├── NetServer.java
    │   ├── Platform.java
    │   ├── Renderer.java
    │   ├── UI.java
    │   ├── Version.java
    │   └── World.java
    ├── ctype
    │   ├── Content.java
    │   ├── ContentList.java
    │   ├── ContentType.java
    │   ├── MappableContent.java
    │   └── UnlockableContent.java
    ├── editor
    │   ├── DrawOperation.java
    │   ├── EditorTile.java
    │   ├── EditorTool.java
    │   ├── MapEditorDialog.java
    │   ├── MapEditor.java
    │   ├── MapGenerateDialog.java
    │   ├── MapInfoDialog.java
    │   ├── MapLoadDialog.java
    │   ├── MapRenderer.java
    │   ├── MapResizeDialog.java
    │   ├── MapSaveDialog.java
    │   ├── MapView.java
    │   ├── OperationStack.java
    │   └── WaveInfoDialog.java
    ├── entities
    │   ├── bullet
    │   │   ├── ArtilleryBulletType.java
    │   │   ├── BasicBulletType.java
    │   │   ├── BombBulletType.java
    │   │   ├── BulletType.java
    │   │   ├── FlakBulletType.java
    │   │   ├── HealBulletType.java
    │   │   ├── LiquidBulletType.java
    │   │   ├── MassDriverBolt.java
    │   │   └── MissileBulletType.java
    │   ├── Damage.java
    │   ├── effect
    │   │   ├── Decal.java
    │   │   ├── Fire.java
    │   │   ├── GroundEffectEntity.java
    │   │   ├── ItemTransfer.java
    │   │   ├── Lightning.java
    │   │   ├── Puddle.java
    │   │   ├── RubbleDecal.java
    │   │   └── ScorchDecal.java
    │   ├── Effects.java
    │   ├── Entities.java
    │   ├── EntityCollisions.java
    │   ├── EntityGroup.java
    │   ├── Predict.java
    │   ├── TargetPriority.java
    │   ├── traits
    │   │   ├── AbsorbTrait.java
    │   │   ├── BelowLiquidTrait.java
    │   │   ├── BuilderMinerTrait.java
    │   │   ├── BuilderTrait.java
    │   │   ├── DamageTrait.java
    │   │   ├── DrawTrait.java
    │   │   ├── Entity.java
    │   │   ├── HealthTrait.java
    │   │   ├── KillerTrait.java
    │   │   ├── MinerTrait.java
    │   │   ├── MoveTrait.java
    │   │   ├── Saveable.java
    │   │   ├── SaveTrait.java
    │   │   ├── ScaleTrait.java
    │   │   ├── ShooterTrait.java
    │   │   ├── SolidTrait.java
    │   │   ├── SpawnerTrait.java
    │   │   ├── SyncTrait.java
    │   │   ├── TargetTrait.java
    │   │   ├── TeamTrait.java
    │   │   ├── TimeTrait.java
    │   │   ├── TypeTrait.java
    │   │   └── VelocityTrait.java
    │   ├── type
    │   │   ├── base
    │   │   │   ├── BaseDrone.java
    │   │   │   ├── BuilderDrone.java
    │   │   │   ├── FlyingUnit.java
    │   │   │   ├── GroundUnit.java
    │   │   │   ├── HoverUnit.java
    │   │   │   ├── MinerDrone.java
    │   │   │   └── RepairDrone.java
    │   │   ├── BaseEntity.java
    │   │   ├── BaseUnit.java
    │   │   ├── Bullet.java
    │   │   ├── DestructibleEntity.java
    │   │   ├── EffectEntity.java
    │   │   ├── Player.java
    │   │   ├── SolidEntity.java
    │   │   ├── TileEntity.java
    │   │   ├── TimedEntity.java
    │   │   └── Unit.java
    │   ├── units
    │   │   ├── StateMachine.java
    │   │   ├── Statuses.java
    │   │   ├── UnitCommand.java
    │   │   ├── UnitDrops.java
    │   │   └── UnitState.java
    │   └── Units.java
    ├── game
    │   ├── DefaultWaves.java
    │   ├── Difficulty.java
    │   ├── EventType.java
    │   ├── Gamemode.java
    │   ├── GlobalData.java
    │   ├── LoopControl.java
    │   ├── MusicControl.java
    │   ├── Objective.java
    │   ├── Objectives.java
    │   ├── Rules.java
    │   ├── Saves.java
    │   ├── Schematic.java
    │   ├── Schematics.java
    │   ├── SoundLoop.java
    │   ├── SpawnGroup.java
    │   ├── Stats.java
    │   ├── Team.java
    │   ├── Teams.java
    │   └── Tutorial.java
    ├── graphics
    │   ├── BlockRenderer.java
    │   ├── Bloom.java
    │   ├── CacheLayer.java
    │   ├── Drawf.java
    │   ├── FloorRenderer.java
    │   ├── IndexedRenderer.java
    │   ├── Layer.java
    │   ├── LightRenderer.java
    │   ├── MenuRenderer.java
    │   ├── MinimapRenderer.java
    │   ├── MultiPacker.java
    │   ├── OverlayRenderer.java
    │   ├── Pal.java
    │   ├── Pixelator.java
    │   └── Shaders.java
    ├── input
    │   ├── Binding.java
    │   ├── DesktopInput.java
    │   ├── InputHandler.java
    │   ├── MobileInput.java
    │   ├── Placement.java
    │   └── PlaceMode.java
    ├── io
    │   ├── JsonIO.java
    │   ├── LegacyMapIO.java
    │   ├── MapIO.java
    │   ├── SaveFileReader.java
    │   ├── SaveIO.java
    │   ├── SaveMeta.java
    │   ├── SavePreviewLoader.java
    │   ├── SaveVersion.java
    │   ├── TypeIO.java
    │   └── versions
    │       ├── LegacyTypeTable.java
    │       ├── Save1.java
    │       ├── Save2.java
    │       └── Save3.java
    ├── maps
    │   ├── filters
    │   │   ├── BlendFilter.java
    │   │   ├── ClearFilter.java
    │   │   ├── DistortFilter.java
    │   │   ├── FilterOption.java
    │   │   ├── GenerateFilter.java
    │   │   ├── MedianFilter.java
    │   │   ├── MirrorFilter.java
    │   │   ├── NoiseFilter.java
    │   │   ├── OreFilter.java
    │   │   ├── OreMedianFilter.java
    │   │   ├── RiverNoiseFilter.java
    │   │   ├── ScatterFilter.java
    │   │   └── TerrainFilter.java
    │   ├── generators
    │   │   ├── BasicGenerator.java
    │   │   ├── Generator.java
    │   │   ├── MapGenerator.java
    │   │   └── RandomGenerator.java
    │   ├── MapException.java
    │   ├── Map.java
    │   ├── MapPreviewLoader.java
    │   ├── Maps.java
    │   └── zonegen
    │       ├── DesertWastesGenerator.java
    │       └── OvergrowthGenerator.java
    ├── mod
    │   ├── ClassAccess.java
    │   ├── ContentParser.java
    │   ├── Mod.java
    │   ├── ModLoadingSound.java
    │   ├── Mods.java
    │   └── Scripts.java
    ├── net
    │   ├── Administration.java
    │   ├── ArcNetProvider.java
    │   ├── CrashSender.java
    │   ├── Host.java
    │   ├── Interpolator.java
    │   ├── NetConnection.java
    │   ├── Net.java
    │   ├── NetworkIO.java
    │   ├── Packet.java
    │   ├── Packets.java
    │   ├── Registrator.java
    │   ├── Streamable.java
    │   └── ValidateException.java
    ├── plugin
    │   └── Plugin.java
    ├── type
    │   ├── Category.java
    │   ├── ErrorContent.java
    │   ├── Item.java
    │   ├── ItemStack.java
    │   ├── ItemType.java
    │   ├── Liquid.java
    │   ├── LiquidStack.java
    │   ├── Mech.java
    │   ├── Publishable.java
    │   ├── StatusEffect.java
    │   ├── TypeID.java
    │   ├── UnitType.java
    │   ├── Weapon.java
    │   ├── WeatherEvent.java
    │   └── Zone.java
    ├── ui
    │   ├── Bar.java
    │   ├── BorderImage.java
    │   ├── Cicon.java
    │   ├── ContentDisplay.java
    │   ├── dialogs
    │   │   ├── AboutDialog.java
    │   │   ├── AdminsDialog.java
    │   │   ├── BansDialog.java
    │   │   ├── ColorPicker.java
    │   │   ├── ContentInfoDialog.java
    │   │   ├── ControlsDialog.java
    │   │   ├── CustomGameDialog.java
    │   │   ├── CustomRulesDialog.java
    │   │   ├── DatabaseDialog.java
    │   │   ├── DeployDialog.java
    │   │   ├── DiscordDialog.java
    │   │   ├── FileChooser.java
    │   │   ├── FloatingDialog.java
    │   │   ├── GameOverDialog.java
    │   │   ├── HostDialog.java
    │   │   ├── JoinDialog.java
    │   │   ├── LanguageDialog.java
    │   │   ├── LoadDialog.java
    │   │   ├── LoadoutDialog.java
    │   │   ├── MapPlayDialog.java
    │   │   ├── MapsDialog.java
    │   │   ├── MinimapDialog.java
    │   │   ├── ModsDialog.java
    │   │   ├── PaletteDialog.java
    │   │   ├── PausedDialog.java
    │   │   ├── SaveDialog.java
    │   │   ├── SchematicsDialog.java
    │   │   ├── SettingsMenuDialog.java
    │   │   ├── TechTreeDialog.java
    │   │   ├── TraceDialog.java
    │   │   └── ZoneInfoDialog.java
    │   ├── Fonts.java
    │   ├── fragments
    │   │   ├── BlockConfigFragment.java
    │   │   ├── BlockInventoryFragment.java
    │   │   ├── ChatFragment.java
    │   │   ├── FadeInFragment.java
    │   │   ├── Fragment.java
    │   │   ├── HudFragment.java
    │   │   ├── LoadingFragment.java
    │   │   ├── MenuFragment.java
    │   │   ├── OverlayFragment.java
    │   │   ├── PlacementFragment.java
    │   │   ├── PlayerListFragment.java
    │   │   └── ScriptConsoleFragment.java
    │   ├── GridImage.java
    │   ├── IconSize.java
    │   ├── IntFormat.java
    │   ├── ItemDisplay.java
    │   ├── ItemImage.java
    │   ├── ItemsDisplay.java
    │   ├── layout
    │   │   ├── BranchTreeLayout.java
    │   │   ├── RadialTreeLayout.java
    │   │   └── TreeLayout.java
    │   ├── Links.java
    │   ├── LiquidDisplay.java
    │   ├── Minimap.java
    │   ├── MobileButton.java
    │   ├── MultiReqImage.java
    │   ├── ReqImage.java
    │   └── Styles.java
    ├── Vars.java
    └── world
        ├── Block.java
        ├── blocks
        │   ├── Attributes.java
        │   ├── Autotiler.java
        │   ├── BlockPart.java
        │   ├── BuildBlock.java
        │   ├── defense
        │   │   ├── DeflectorWall.java
        │   │   ├── Door.java
        │   │   ├── ForceProjector.java
        │   │   ├── MendProjector.java
        │   │   ├── OverdriveProjector.java
        │   │   ├── ShockMine.java
        │   │   ├── SurgeWall.java
        │   │   ├── turrets
        │   │   │   ├── ArtilleryTurret.java
        │   │   │   ├── BurstTurret.java
        │   │   │   ├── ChargeTurret.java
        │   │   │   ├── CooledTurret.java
        │   │   │   ├── DoubleTurret.java
        │   │   │   ├── ItemTurret.java
        │   │   │   ├── LaserTurret.java
        │   │   │   ├── LiquidTurret.java
        │   │   │   ├── PowerTurret.java
        │   │   │   └── Turret.java
        │   │   └── Wall.java
        │   ├── distribution
        │   │   ├── ArmoredConveyor.java
        │   │   ├── BufferedItemBridge.java
        │   │   ├── Conveyor.java
        │   │   ├── ExtendingItemBridge.java
        │   │   ├── ItemBridge.java
        │   │   ├── Junction.java
        │   │   ├── MassDriver.java
        │   │   ├── OverflowGate.java
        │   │   ├── Router.java
        │   │   └── Sorter.java
        │   ├── DoubleOverlayFloor.java
        │   ├── Floor.java
        │   ├── ItemSelection.java
        │   ├── liquid
        │   │   ├── ArmoredConduit.java
        │   │   ├── Conduit.java
        │   │   ├── LiquidBridge.java
        │   │   ├── LiquidExtendingBridge.java
        │   │   ├── LiquidJunction.java
        │   │   ├── LiquidOverflowGate.java
        │   │   ├── LiquidRouter.java
        │   │   └── LiquidTank.java
        │   ├── LiquidBlock.java
        │   ├── logic
        │   │   ├── LogicBlock.java
        │   │   └── MessageBlock.java
        │   ├── OreBlock.java
        │   ├── OverlayFloor.java
        │   ├── power
        │   │   ├── Battery.java
        │   │   ├── BurnerGenerator.java
        │   │   ├── ConditionalConsumePower.java
        │   │   ├── DecayGenerator.java
        │   │   ├── ImpactReactor.java
        │   │   ├── ItemLiquidGenerator.java
        │   │   ├── LightBlock.java
        │   │   ├── NuclearReactor.java
        │   │   ├── PowerDiode.java
        │   │   ├── PowerDistributor.java
        │   │   ├── PowerGenerator.java
        │   │   ├── PowerGraph.java
        │   │   ├── PowerNode.java
        │   │   ├── SingleTypeGenerator.java
        │   │   ├── SolarGenerator.java
        │   │   └── ThermalGenerator.java
        │   ├── PowerBlock.java
        │   ├── production
        │   │   ├── Cultivator.java
        │   │   ├── Drill.java
        │   │   ├── Fracker.java
        │   │   ├── GenericCrafter.java
        │   │   ├── GenericSmelter.java
        │   │   ├── Incinerator.java
        │   │   ├── LiquidConverter.java
        │   │   ├── Pump.java
        │   │   ├── Separator.java
        │   │   └── SolidPump.java
        │   ├── RespawnBlock.java
        │   ├── Rock.java
        │   ├── sandbox
        │   │   ├── ItemSource.java
        │   │   ├── ItemVoid.java
        │   │   ├── LiquidSource.java
        │   │   ├── PowerSource.java
        │   │   └── PowerVoid.java
        │   ├── StaticWall.java
        │   ├── storage
        │   │   ├── CoreBlock.java
        │   │   ├── LaunchPad.java
        │   │   ├── StorageBlock.java
        │   │   ├── Unloader.java
        │   │   └── Vault.java
        │   ├── TreeBlock.java
        │   └── units
        │       ├── CommandCenter.java
        │       ├── MechPad.java
        │       ├── RallyPoint.java
        │       ├── RepairPoint.java
        │       └── UnitFactory.java
        ├── BlockStorage.java
        ├── Build.java
        ├── CachedTile.java
        ├── consumers
        │   ├── ConsumeItemFilter.java
        │   ├── ConsumeItems.java
        │   ├── Consume.java
        │   ├── ConsumeLiquidBase.java
        │   ├── ConsumeLiquidFilter.java
        │   ├── ConsumeLiquid.java
        │   ├── ConsumePower.java
        │   ├── Consumers.java
        │   └── ConsumeType.java
        ├── DirectionalItemBuffer.java
        ├── Edges.java
        ├── ItemBuffer.java
        ├── LegacyColorMapper.java
        ├── meta
        │   ├── Attribute.java
        │   ├── BlockBars.java
        │   ├── BlockFlag.java
        │   ├── BlockGroup.java
        │   ├── BlockStat.java
        │   ├── BlockStats.java
        │   ├── BuildVisibility.java
        │   ├── PowerType.java
        │   ├── Producers.java
        │   ├── StatCategory.java
        │   ├── StatUnit.java
        │   ├── StatValue.java
        │   └── values
        │       ├── AmmoListValue.java
        │       ├── BooleanValue.java
        │       ├── BoosterListValue.java
        │       ├── ItemFilterValue.java
        │       ├── ItemListValue.java
        │       ├── LiquidFilterValue.java
        │       ├── LiquidValue.java
        │       ├── NumberValue.java
        │       └── StringValue.java
        ├── modules
        │   ├── BlockModule.java
        │   ├── ConsumeModule.java
        │   ├── ItemModule.java
        │   ├── LiquidModule.java
        │   └── PowerModule.java
        ├── Pos.java
        ├── producers
        │   ├── ProduceItem.java
        │   └── Produce.java
        ├── StaticTree.java
        ├── Tile.java
        └── WorldContext.java

