
# Modding Introduction

Mindustry mods are simply directories of assets. There are many ways to use the modding API, depending on exactly what you want to do, and how far you're willing to go to do it.

You could just resprite existing game content, or create new game content with the simpler Json API (which is the main focus of this documentation). You can add custom sounds (or reuse existing ones), add maps to campaign mode, and add scripts to program special behavior into your mod, like custom effects.

Sharing your mod is as simple as giving someone your project directory; mods work on any platform that supports them. You'll want to use [GitHub](#github) (*or a similar service*) for hosting your source code.
To make mods, all you really need is any computer with a text editor.

## Editing

If you are using HJSON for your mods, it is recommended to use [Visual Studio Code](https://code.visualstudio.com/) with the [Mindustry HJSON](https://github.com/Anuken/MindustryHJsonVSCode/releases/latest) extension.

To install the extension, download `mindustry-hjson-x.x.x.vsix` from the linked release page. In VSCode, open the Extensions tab, click the three dots in the top right -> "Install From VSIX..." -> select the downloaded VSIX file.

The extension provides autocomplete, syntax highlighting, and warnings for unknown or invalid fields in content.

## Directory Structure

Your project directory should look something like this:

    project
    ├── mod.hjson
    ├── content
    │   ├── items
    │   ├── blocks
    │   ├── liquids
    │   ├── weather
    │   ├── liquids
    │   └── units
    ├── maps
    ├── bundles
    ├── sounds
    ├── schematics
    ├── scripts
    ├── sprites-override
    └── sprites

-   `mod.hjson` (required) metadata file for your mod,
-   `content/*` directories for game [Content](#content),
-   `maps/` directory for in-game maps,
-   `bundles/` directory for [Bundles](#bundles),
-   `sounds/` directory for [Sound](#sound) files,
-   `schematics/` directory for schematic files,
-   `scripts/` directory for Javascript script file,
-   `sprites-override/` [Sprites](#sprites) directory for overriding ingame content,
-   `sprites/` [Sprites](#sprites) directory for your content,

Every platform has a different user application data directory, and this is where your mods should be placed:

-   Linux: `~/.local/share/Mindustry/mods/`
-   Steam: `steam/steamapps/common/Mindustry/saves/mods/`
-   Windows: `%appdata%/Mindustry/mods/`
-   MacOS: `~/Library/Application Support/Mindustry/mods/`

*Note that your filenames should be lowercased and hyphen separated:*

-   correct: `my-custom-block.json`
-   incorrect: `My Custom Block.json`


## HJSON

Mindustry uses [Hjson](https://hjson.github.io/), which is a superset of the very popular format known as [JSON ](https://en.wikipedia.org/wiki/JSON). This means that any valid JSON will work, but you get extra features as well:
```js
# single line comment

// single line comment

/* multiline
   comment */

key1: "single line string"

key2:
  '''
  multiline
  string
  '''

key3: [
  //quotes and commas are optional for strings
  value1
  value2
  value3
]

key4: {
  key1: astring
  key2: 0
}

//unlike the official HJSON spec, multiple quoteless strings are allowed in the same line in an array

arrayExample: [several, words, that, will, work]
```
If you don't know any of those words: a serialization language is simply a language which encodes information for a program, and *encode* means to translate information from one form to another, in this case, to translate text into Java data structures.

It is worth noting that the 'official' HJSON standard is dead, and contains several serious flaws. The Mindustry HJSON parser uses a slightly modified format that allows quoteless multiline arrays, for example.

## `mod.hjson`

At the root of your project directory, you must have a `mod.hjson`, which defines the basic metadata for your project. 
```js
name: "mod-name"
displayName: "This isn't a mod."
author: Yourself
description: "A short description of your mod."
version: "1.0"
minGameVersion: "$latestRelease"
dependencies: [ ]
hidden: false
```
-   `name` will be used to reference to your mod, so name it carefully. Should be in kebab-case (no capital letters, spaces are filled with '-') and shouldn't have any color formatting.
-   `displayName` this will be used as a display name for the UI, which you can use to add formatting to said name.
-   `description` of the mod will be rendered in the ingame mod manager, so keep it short and to the point.
-   `dependencies` is optional, if you want to know more about that, go to the [dependencies](#dependencies) section.
-   `minGameVersion` is the minimum build version of the game. This is **required** to be a number greater than 136.
-   `hidden` is whether or not this mod is essential for multiplayer, false by default. Texture packs, JS plugins, etc. should set this to true, so they don't cause version-mismatch conflicts between servers and clients. As a rule of thumb, if your mod creates content it shouldn't be hidden.



## Content

At the root of your project directory you can have a `content/` directory. This is where all the JSON/HJSON data goes. Inside of `content/` you have subdirectories for the various kinds of content; these are the current common ones:

-   `content/items/` for [items](#item), like `copper` and `surge-alloy`;
-   `content/blocks/` for [blocks](#block), like turrets and floors;
-   `content/liquids/` for [liquids](#liquid), like `water` and `slag`;
-   `content/units/` for flying or ground [units](#unittype), like `eclipse` and `dagger`;

Note that each one of these subdirectories needs a specific content type. The filenames of these files is important, because the stem name of your path *(filename without the extension)* is used to reference it.

Furthermore, the files within these `content/<content-type>/*` directories may be arbitrarily nested into other sub-directories of any name, to help you organize them further, for example:

-   `content/items/metals/iron.hjson`, which would respectively create an item named `iron`.

The content of these files will tend to look something like this:

    type: TypeOfThing
    name: Name Of Thing
    description: Description of thing.
    # ... more fields here ...

|field|type|notes|
|---|---|---|
|type|String|Content type of this object.|
|name|String|Displayed name of content.|
|description|String|Displayed description of content.|

Other fields included will be the fields of the type itself.

As a side note, `name` and `description` are not required to be in the json structure. You can define them for any language with [Bundles](#bundles). However, if they are not present in either, the name will default to `<type>.<modname>-<stemname>.name` and the description will be empty.


## Types

Types have numerous fields, but the important one is `type`; this is a special field used by the content parser, that changes which type your object is. *A `Router` type can't be a `Turret` type*, as they're just completely different.

Types *extend* each other, so if `MissileBulletType` extends `BasicBulletType`, you'll have access to all the fields of `BasicBulletType` inside of `MissileBulletType` like `damage`, `lifetime` and `speed`. Fields are case sensitive: `hitSize =/= hitsize`.

What you can expect a field to do is up to the specific type; some types do absolutely nothing with their fields, and mostly serve as a base for other types to extend from. One such type is `Block`.

In this unit example, the type of the unit is `flying`. The type of the `bullet` is `BulletType`, so you can use `MissileBulletType`, because `MissileBulletType` extends `BulletType`.

Other unit types include `mech`, `legs`, `naval`, `payload`, `tank`, `hover`, `crawl`, `missile` and `tether`.

```js
type: flying
weapons: [
  {
    bullet: {
      type: MissileBulletType
      damage: 9000
    }
  }
]
```

## Tech Tree

Much like `type`, there exists another field called `research`, which can go at the root of any content object to place it in the techtree.

    research: duo

This would put your block after `duo` in the techtree, and to put it after your own mods block you would write your `<block-name>`, a mod name prefix is only required if you're using the content from another mod.

Research costs:

|type|cost|notes|
|---|---|---|
|blocks|`60 * researchCostMultiplier + requirements ^ 1.11 * 20 * researchCostMultiplier`|`researchCostMultiplier` is a stat that can be set on blocks, default `1`|
|units|`requirements * researchCostMultiplier`|`researchCostMultiplier` defaults to `50` on `UnitType`|

The cost is then rounded to the nearest 10, 100, 1k, or 100k depending on how large the cost is (rounding isn't always downward).

`requirements` is the cost of the block or unit. Units use their build cost/upgrade cost for the calculations.

If you want to set custom research requirements, use this object in place of just a name:
```js
research: {
  parent: duo
  requirements: [
    copper/100
  ]
}
```
This can be used to override block or unit costs, or make resources need to be researched instead of just having to produce them.

## Sprites

All you need to make sprites, is an image editor that supports transparency *(aka: not paint).* Block sprites should be `32 * size`, so a `2x2` block would require a `64x64` image. Images must be PNG files with a 32-bit RGBA pixel format.
**Any other pixel format, such as 16-bit RGBA, may cause Mindustry to crash with a "Pixmap decode error".** You can use the command-line tool `file` to print information about your sprites:

    file sprites/**.png

If any of them are not 32-bit RGBA formatted, fix them.

Sprites can simply be dropped in the `sprites/` subdirectory. The content parser will look through it recursively.
Images are packed into an "atlas" for efficient for rendering. The first directory in `sprites/`, e.g. `sprites/blocks`, determines the page in this atlas that sprites are put in. Putting a block's sprite in the `units` page is likely to cause lots of lag; thus, you should try to organize things similarly to how the [vanilla game does](https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites).

Content is going to look for sprites relative to its own name. `content/blocks/my-hail.json` has the name `my-hail`, and, similarly `sprites/my-hail.png` has the name `my-hail`, so it'll be used by this content.

Content may look for multiple sprites. `my-hail` could be a turret, and it could look for the suffix `<name>-heat` and what this means is it'll look for `my-hail-heat`.

You can find all the vanilla sprites here:

-   <https://github.com/Anuken/Mindustry/tree/master/core/assets-raw/sprites>

Another thing to know about sprites is that some of them are modified by the game. Turrets specifically have a dark gray border added to them, so you must account for that while making your sprites, leaving transparent space around turrets for example: [Ripple](https://raw.githubusercontent.com/Anuken/Mindustry/master/core/assets-raw/sprites/blocks/turrets/ripple.png)

To override ingame content sprites, you can simply put them in `sprites-override/`.
This removes the `<modname>-` prefix to their id, which allows them to override sprites from vanilla and even other mods.



## Sound

Custom sounds can be added through the modding system by dropping them in the `sounds/` subdirectory. Two formats are supported: `ogg` and `mp3`. Note that `mp3` files cannot loop seamlessly, so try to use `ogg` whenever possible.

Just like any other assets, you reference them by the stem of your filenames, so `pewpew.ogg` and `pewpew.mp3` can be referenced with `pewpew` from a field of type `Sound`.

Here's a list of built-in sounds:

$sounds

## Dependencies

You can add dependencies to your mod by simple adding other mods name in your `mod.json`:
```js
dependencies: [
  other-mod-name
  not-a-mod
]
```
The name of dependencies are lower-cased and spaces are replaced with `-` hyphens, for example `Other MOD NamE` becomes `other-mod-name`.

To reference the other mods assets, you must prefix the asset with the other mods name:

-   `other-mod-name-not-copper` would reference `not-copper` in `other-mod-name`
-   `other-mod-name-angry-dagger` would reference `angry-dagger` in `other-mod-name`
-   `not-a-mod-angry-dagger` would reference `angry-dagger` in `not-a-mod`



## Bundles

An optional addition to your mod is called bundles. The main use of bundles are give translations of your content, but there's no reason you couldn't use them in English. These are plaintext files which go in the `bundles/` subdirectory, and they should be named something like `bundle_ru.properties` (for Russian).

The contents of this file is very simple:

    block.example-mod-silver-wall.name = Серебряная Стена
    block.example-mod-silver-wall.description = Стена из серебра.

If you've read the first few sections of this guide, you'll spot it right away:

-   `<content type>.<mod name>-<content name>.name`
-   `<content type>.<mod name>-<content name>.description`

With your own custom bundle lines for use in scripts you can use whatever key you like:

-    `message.egg = Eat your eggs`
-    `randomline = Random Line`

Notes:

-   mod/content names are lowercased and hyphen separated.

List of content types:

$contentTypes

List of bundle suffixes relative to languages:

$bundles


## GitHub

Once you have a mod of some kind, you'll want to actually share it, and you may even want to work with other people on it, and to do that you can use [GitHub](https://github.com/). If you don't know what Git (or GitHub) is at all, then you should look into [GitHub Desktop](https://desktop.github.com/), otherwise simply use your favorite command line tool or text editor plugin. 

All you need understand is how to open repositories on GitHub, stage and commit changes in your local repository, and push changes to the GitHub repository. Once your project is on GitHub, there are three ways to share it:

-   with the endpoint, for example `Anuken/MindustryJavaModTemplate`, which could then be typed in the ingame GitHub interface, and that would download it;
-   with the zip file, for example `https://github.com/Anuken/MindustryJavaModTemplate/archive/master.zip`, which would download the repository as a zip file, and put in mod directory (unzipping is not required);
-   add the topic/tag `mindustry-mod` on your repository, which should add it to the topic search and the [Mod scraper](https://github.com/Anuken/MindustryMods).



## FAQ

-   `time` in game is calculated through `ticks`; `ticks`, *sometimes called `frames`,* are 1/60th of a second;
-   `tilesize` is 8 world units internally; most values such as hitbox sizes are measured in these world units;
-   to calculate range out of `lifetime` and `speed`, you can do `lifetime * speed = range`;
-   `NullPointerException` is an error message that indicates a field is null and shouldn't be null, meaning one of the required fields may be missing;
-   *bleeding-edge* is latest the development version of Mindustry; specifically it refers to the latest commit on the Github master branch. Changes on bleeding-edge usually make it into Mindustry in the next release.


