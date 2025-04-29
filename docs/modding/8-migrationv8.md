# 8.0 Migration Guide

This guide is incomplete. As v8 has not been fully released yet, it will continue to change until v8 fully stabilizes.

## JSON Mods

If you have a JSON mod, you *probably* don't need to do anything. All existing JSON mods should still work, albeit with some changes to the way content is displayed on certain planets. See the section on 'Planets' below.

## Java/JS Mods

## Misc

- `Binding` keybind values are now in camelCase.
- The old keybind system has been completely reworked to allow for custom mod keybinds - see `arc.input.KeyBind#add`. `Core.keybinds` has been removed, use the `Keybind` class instead.

## Blocks

- Most unnecessary 'getter' methods (e.g. `void tile(Tile), Tile tile(), block()`) for `Building` have been removed. There was no reason to use these in the first place, but if your mod happened to do that, you'll need to access the field directly instead.
- Blocks now have a separate `lightClipSize` field for `drawLight()` size clipping. `emitLight` must now be true in order for this method to be called.
- `loopSound` has been removed; loops must be created and updated manually in the `Building` of each block. See `Turret` source code for examples.

## Units

- `Player#unit()` **can now be null.** Make sure you check that `!player.dead()` before accessing the unit.
- `Units.null` has been removed.
- Commands are now content. `UnitCommand.all` has been removed.
- Unit commands are now a `Seq`, not an array.

## Planets

- All fields related to visibility of items (`itemWhitelist`, `hiddenItems`, `Rules.hiddenBuildItems`) have been removed. In order to make content show up on planet, change its `shownPlanets` field. If you have a tech tree set up for a planet, this will be done automatically.
