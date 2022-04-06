# Types

*Note:* Deprecated content classes are not listed here, and their use is heavily discouraged. Transition to non-deprecated equivalents as quickly as possible.

View the list of all deprecated classes and methods in the [Mindustry Javadoc](https://mindustrygame.github.io/docs/deprecated-list.html).

All JSON examples are automatically taken from [Exotic Mod](https://github.com/BlueWolf3682/Exotic-Mod) by *BlueWolf3682*. These should *only* be used as a reference for fields - do not directly copy-paste them into your mod, they will **not** work!

$allTypes


## BuildVisibility

A flag used by the game to change a few special-case things. It may be one of the following strings:

$buildVisibilities


## BlockGroup

Groups for blocks to build on top of each other:

$blockGroups


## ItemStack

A `ItemStack` can be a string or an object. It's used to describe the type and amount of items to a machine.

As a `string`:

    copper/5

As an `object`:

    item: copper
    amount: 5

|field|type|notes|
|---|---|---|
|item|string|The name of an [Item](#item).|
|amount|int|The amount of said item.|



## LiquidStack

A `LiquidStack` can be a string or an object. It's used to describe the type and amount of liquid to a machine.

As a `string`:

    water/0.5

As an `object`:

    liquid: water
    amount: 0.5

|field|type|notes|
|---|---|---|
|liquid|string|The name of a [Liquid](#liquid).|
|amount|float|The amount of said liquid.|


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
-   `logic` Blocks that are related to logic operations;
-   `effect` Things for storage or passive effects.


## Color

Color is a hexadecimal string, `<rr><gg><bb>` for example:

-   `ff0000` is red,
-   `00ff00` is green,
-   `0000ff` is blue,
-   `ffff00` is yellow,
-   `00ffff` is cyan,
-   etc.



## CacheLayer

Flags used by for cache render:

-   `normal` normal layer;
-   `walls` walls layer;
-   `water` water layer, adding tile water shaders, and giving wave reflections;
-   `tar` tar layer, adding tar shaders, making it darker and giving it some bubble reflections;

## TargetPriority

A higher ordinal means a higher priority. Higher priority blocks will always get targeted over those of lower priority, regardless of distance.

1.  `base`
2.  `turret`

