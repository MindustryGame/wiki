# Modding

Mods in Mindustry are composed of a folder or zip file, containg a `mod.json` file, as well as a set of sprites and `.json` files defining new content. 

Make sure you look at [this repository](https://github.com/Anuken/ExampleMod) for an example of a simple mod. It may be simpler to download this example and edit it. Take your pick.

## Creating Your First Mod

First, create a folder for your mod. The name is irrelevant.
Then, create a `mod.json` file that will contain the metadata for your mod. It should look like this:

```json
{
  "name": "Mod Name",
  "author": "your name",
  "description": "the mod's description",
  "version": "1.0"
}
```

This defines what the mod will look like in the 'Mods' menu after it is imported.

## Importing Your Mods

There are two ways to import a mod:  
1) Copy-paste the mod's folder into Mindustry's mod folder. On Steam, this is located in Mindustry's Steam installation directory: `steam/steamapps/common/Mindustry/saves/mods`. On other desktop versions, this is located in `%appdata%/Mindustry/mods`.   
2) Zip up the contents of the mod folder (**not** the folder itself - only its contents) and import it through the file chooser in `Main Menu -> Mods -> Import Mod`. If a mod is already zipped up, skip the first step. This is not recommended for mod development, as you will have to re-import the mod every time you change something. 

## Creating Content, Folder Structure

In general, content is defined through `json` files located in a few special folders. The exact format of these files depends on the type of content you're making, but in general, the structure is:

- `<mod root folder>` - *the root folder for your mod*
  - `bundles/` - *the folder where the names and strings for your blocks are stored*
    - `bundle.properties` - *the bundle for a specific language; bundle.properties would be the default (english)*
    - `<bundles for other languages, like bundle_ru.properties>`
  - `content` - *where content files is defined, e.g. units, zones, blocks, items*
    - `blocks/` - *all blocks must go here*
      - `someblock1.json` - *defines a block named 'someblock1'*
    - `items/` - *all items must go here*
      - `someitem.json` - *defines an item named 'someitem'*
    - `<any other content folders, e.g. for units>`
  - `sprites/` - *all sprites for the blocks and items you add must go here*
    - `blocks/` - *technically, it's not required to put your sprites in separate folders, but it's good practice*
      - `crafting/` - *sprites for someblock1, etc*
        - `someblock1.png`
        - `someblock2.png`
      - `environment/` - *sprites for environmental floors and ores*
        - `somefloor1.png`
        - `someore1.png`
    - `items/` - *sprites for items and liquids*
      - `someitem.png`
      - `someliquid.png`
    - `<any other sprites you use>/`
 
See the [example](https://github.com/Anuken/ExampleMod) to see what this hierarchy like in a real mod.

#### Creating a new block

Each type of block needs a few base properties:
- Its `type`. This can range from things like `ItemTurret` to `Floor` to `Wall`. Each type of block had a different set of configuration options. A full, descriptive list of block types will be available soon.
- A `name` and `description`. While these are technically optional, they are highly recommended.

An example of these properties:

```json
{
    "type": "Wall",
    "name": "White Wall",
    "description": "A completely blank wall. Note that this text is displayed in the block's info menu."
}

```

Most further properties depending the `type` of block you've set. 
See the example mod to learn about some of the properties that different types of blocks can have.

#### Turrets types

With different kinds of turrets come different types and properties here is a list of the differents kind of turret and some of there in game representant.

|Type|Turret|
|:---|-----:|
|DoubleTurret|Duo|
|BurstTurret|Scatter|
|ItemTurret|Scorch|
|ArtilleryTurret|Hail|
|LiquidTurret|Wave|
|ChargeTurret|Lancer|
|PowerTurret|Arc|
|LaserTurret|Meltdown|

most of theyse propeties can be ommited, some specials propeties are explain later.

|Propertie|Type|Avalable on|Note|
|:--------|:--:|:---------:|---:|
|name|quoted string | All |  |
|description|quoted string| All |  |
|targetAir|boolean| All |define if the turret target flying ennemies|
|targetGround|boolean| All |define if the turrettarget walking ennemies|
|health|integer| All ||
|size|integer| All ||
|inaccuracy|integer| All |represent in degree the inaccuracy of the turret|
|reload|integer| All | time in tick needed by the turret to reload|
|recoil|integer| All | only graphic|
|range|integer| All ||
|category|quoted string| All | define in wich group the turret will be added in the building menu as it's a turret "turret" is highly recomended|
|health|integer| All ||
|shootShake|integer| All |//need note|
|shots|integer| All |how many bullets are shot per shoot|
|shootCone|integer| All except ArtilleryTurret, ChargeTurret, BurstTurret |//need note|
|powerUse|integer| All | how much power consume the turret |
|shootEffect|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|
|smokeEffect|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|
|shootSound|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|
|chargeEffect|<span style='color:red'>help needed</span>|ChargeTurret|<span style='color:red'>help needed</span>|
|chargeEffects|<span style='color:red'>help needed</span>|ChargeTurret|<span style='color:red'>help needed</span>|
|chargeBeginEffect|<span style='color:red'>help needed</span>|ChargeTurret|<span style='color:red'>help needed</span>|
|rotatespeed|integer| All | define how fast your turret rotate |
|coolantMultiplier|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|<span style='color:red'>help needed</span>|
|burstSpacing|<span style='color:red'>help needed</span>|BurstTurret|<span style='color:red'>help needed</span>|
|xRand|<span style='color:red'>help needed</span>|BurstTurret|<span style='color:red'>help needed</span>|

there is other field that need a bit more explain than the Note column allow like the ammo, requirements, research fields

//TODO help wanted!

#### Items & Other Content

