# 6.0 Migration Guide

If you are a plugin or mod developer for 5.0, you may have noticed that your content no longer functions correctly in 6.0. 
This is due to numerous internal changes and additions, which will be documented here.

## General Changes

### Minimum Game Version

All mods must now specify `minGameVersion` with a value of "105" or above to be loaded. This is to ensure that outdated mods do not get loaded.
Simply add `minGameVersion: "$latestRelease"` to your `mod.hjson` file.

## Name Changes

### mindustry.plugin.Plugin -> mindustry.mod.Plugin

The `Plugin` class has been moved into the `mod` package, as the old package only contained a single class anyway.

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

