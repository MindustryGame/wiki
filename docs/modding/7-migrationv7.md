# 7.0 Migration Guide

## Blocks

- `Block#expanded` is now deprecated and a no-op, use `Block#clipSize`instead. The field is kept to ensure compatibility, but will be removed eventually.
- All `mindustry.world.meta.values.*` classes have been replaced with lambdas. See the `StatValues` class.
- `BlockForge` has been moved out of the experimental package, and will likely undergo significant changes. If you were using this class in a Java mod, I recommend copy-pasting it in so you can keep using the old version. Other experimental blocks may be moved as well.
- `CacheLayer` is now a class with methods that can be overridden - not an enum. `CacheLayer#add` can be used to register new layers.
- Various fields, like `variants` and `attributes` have been moved from `Floor` to `Block`.
- `Iconc` and related methods have been removed; use `UnlockableContent.uiIcon/fullIcon`. 
- `Smelter` and `AttributeSmelter` have been deprecated. These classes had hard-coded drawing functionality. Transition to `GenericCrafter` with a `DrawSmelter` as quickly as possible. For attribute support, use `AttributeCrafter`.
- `Cultivator` is deprecated for the same reasons as `Smelter`, use `AttributeCrafter` instead.
- `PayloadAcceptor` was a misleading name in the wrong package, use `PayloadBlock` instead.
- Generated icons **must** be created in `createIcons` now; attempting to use `Core.atlas.addRegion` simply will not work.
- All fields in `Tex` are now `Drawable`, not `NinePatchDrawable` or `TextureRegionDrawable`. Why? These fields are loaded from the atlas, which means mods that change UI sprites or an outdated atlas could previously cause a `ClassCastException` crash.

## Ammo

- Any mod code that worked with unit ammo is now broken.
- The `ResupplyPoint` class has been removed.
- `AmmoType` is now an interface, not a class.
- `AmmoTypes` has been removed, make new instances instead.
- Ammo type classes have been moved into the `mindustry.type.ammo` package.

## Arc

- `Pixmap`'s API has been completely changed. Most methods now have blending disabled, and color/blending/scaling parameters are no longer part of the `Pixmap` state machine. Most image-related methods are now pure Java instead of JNI + C.
- `SettingsDialog` (`Vars.ui.settings`) has been moved into Mindustry's codebase. This technically doesn't change the API; however, Java mods compiled with 6.0 source will try to access non-existent fields of a non-existent class, leading to crashes. Recompiling with v7 Mindustry/arc dependencies should be enough to fix this.
- TextureAtlas now uses the smaller, faster `aatls` binary format. Update your Arc dependencies to read it.
- `Core.net` has been removed, use the static methods in `arc.util.Http` instead.
- `RidgedPerlin` has been renamed to `Ridged`.
- `Simplex` and `Ridged` are now stateless; use static methods to generate noise now. The seed is a parameter.

## Networking

- `Registrator` for packets has been moved to `Net`, and registration methods have been made public, for potential use in Java mods. 
- `InvokePacket` has been removed, and replaced with generated packet classes that handle events directly. 
- `RemoteRead{Server, Client}` have also been removed. 
- `Packet` is now an abstract class, not an interface.

## Misc

- `BulletType#despawned` is no longer called in many cases, use `#removed` if you need to listen to all removal events
- `Attribute` is now a standard class, not an enum. Use `Attribute.add` to register a new one.
- `Vars.miningRange` has been moved to `UnitType`.

## Sprites

- Outlines are now automatically generated for unit & weapon sprites. Leg regions are currently exempt.
- All mod sprites are now automatically alpha-bled at load time when linear filtering is enabled - there is no need to do so manually.

*More changes to come.*

I will be introducing `@Deprecated` compatibility methods for most significant changes as needed. Ideally, most 6.0 java mods should still work with 7.0.
