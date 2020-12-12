# 6.0 Migration Guide

If you are a plugin or mod developer for 5.0, you may have noticed that your content no longer functions correctly in 6.0. 
This is due to numerous internal changes and additions, which will be documented here.

## General Changes

### Minimum Game Version

All mods must now specify `minGameVersion` with a value of "105" or above to be loaded. This is to ensure that outdated mods do not get loaded.
Simply add `minGameVersion: "$latestRelease"` to your `mod.hjson` file.

## Name Changes

### Variable name changes

Lots of variables had name changes between v5 and v6, here's a list of all of them.

ItemTurret:

- ammo -> ammoTypes

BasicBulletType:

- bulletWidth -> width
- bulletHeight -> height
- bulletSprite -> sprite

### mindustry.plugin.Plugin -> mindustry.mod.Plugin

The `Plugin` class has been moved into the `mod` package, as the old package only contained a single class anyway.

### TileEntity -> Building

`TileEntity` is now `Building`.
Thus, the former `TileEntity`'s functions, as well as any function associated with it(containing or mentioning "entity") have been renamed, now they will refer to the `TileEntity` to "building", or "build". `Tile.entity` has been renamed to `Tile.build`, and all `TileEntity` instances (ex. `RouterEntity`, `ConveyorEntity`) were renamed to end with a "Build" suffix (ex. `RouterBuild`, `ConveyorBuild`), to name a few.  

Many functions like `draw()` or `placed()` have moved from being declared in the `Block` to being so in `Building`. This means that these functions do not pass the `Tile`, as well as making block-specific behavior less complicated. Notably, `update(Tile tile)` has been moved to the `Building` and renamed (technically not true, but this detail can be ignored for porting) to `updateTile()`.

### Array<T> -> Seq<T>

The `arc.struct.Array` has been renamed to `arc.struct.Seq`, which is a short form of `Sequence`.  

Why?

- It's more accurate. The data structure is not an array, it's a list like `ArrayList`.
- It doesn't conflict with other classes named `Array`, such as those in Java's reflection API or Javascript's array.
- It's shorter, which is nice.

### Removal of "on" prefix for Call methods

All remote invocation methods in `Call` have had their "on" prefix removed. For example:

- `onSnapshot` -> `snapshot`
- `onSetRules` -> `setRules`
- `onLabel` -> `label`

### New Player System

Now that players control units, they no longer exist as corporeal beings in the game - that is to say, they do not have health or weapons. Every action is performed by `Unit`s. There is no `Mech`class anymore, only `UnitType`.

- Every unit has a `UnitController`, which can be AI, logic, or a player.
- To check if a unit is being controlled by a player, use `unit.isPlayer()`
- To get the player of a unit (if it has one), use `unit.getPlayer()`
- Setting a player's position will not do anything. Set the unit's position instead.
