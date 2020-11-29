# Types

$blockTypes

## BuildVisibility

A flag used by the game to change a few special-case things. It may be one of the following strings:

-   `hidden`
-   `shown`
-   `debugOnly`
-   `sandboxOnly`
-   `campaignOnly`
-   `lightingOnly`



## BlockGroup

Groups for blocks to build on top of each other:

-   `none`
-   `walls`
-   `turrets`
-   `transportation`
-   `power`
-   `liquids`
-   `drills`



# Type



## Item

Extends [Content](#content) &#x2013; It's the object that can ride conveyors, sorters and be stored in containers, and is commonly used in crafters.

|field|type|default|notes|
|---|---|---|---|
|color|[Color](#color)|black|hex string of color|
|type|[ItemType](#itemtype)|resource|used for tabs and core acceptance|
|explosiveness|float|0|how explosive this item is.|
|flammability|float|0|flammability above 0.3 makes this eleigible for item burners.|
|radioactivity|float|&#xa0;|how radioactive this item is. 0=none, 1=chernobyl ground zero|
|hardness|int|0|drill hardness of the item|
|cost|float|1|used for calculating place times; 1 cost = 1 tick added to build time|
|alwaysUnlocked|boolean|false|If true, item is always unlocked.|



### ItemType

-   `resource` can't go in the core;
-   `material` can go in the core.



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



## Liquid

Extends [Content](#content)

Type which defines the properties of a liquid. Like [Item](#item) this will go into it's own subdirectory `content/liquids/liquid-name.json`, and from it's stem name you can reuse it from your other mod content.

|field|type|default|notes|
|---|---|---|---|
|color|[Color](#color)|&#xa0;|**[required]** color of liquid|
|barColor|[Color](#color)|&#xa0;|*[optional]* color used in bars.|
|lightColor|[Color](#color)|&#xa0;|Color used to draw lights. Note that the alpha channel is used to dictate brightness.|
|flammability|float|&#xa0;|0 to 1; 0 is completely inflammable, above that may catch fire when exposed to heat.|
|temperature|float|0.5|0.5 is 'room' temperature, 0 is very cold, 1 is molten hot|
|heatCapacity|float|0.5|used in cooling; water is 0.4, cryofluid is 0.9.|
|viscosity|float|0.5|how thick this liquid is; water is 0.5, oil is 0.7.|
|explosiveness|float|&#xa0;|explosiveness when heated; 0 is nothing, 1 is nuke|
|effect|[StatusEffect](#statuseffect)|none|the associated status effect.|

Sprites:

-   `<name>`, the sprite used when displaying the liquid from a menu.



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



## Weapon

Weapons are used by units and mechs alike. A weapon is a type used to shoot bullets [bullets](#bullettype) just like turrets *(except that they don't have an `ammo` mapping)*. Weapons can only shoot one type of bullet, which you define in the `bullet` field.

|field|type|default|notes|
|---|---|---|---|
|name|String|&#xa0;|used to fetch the sprite of the weapon|
|nimPlayerDist|float|20|minimum cursor distance from player, fixes 'cross-eyed' shooting.|
|sequenceNum|int|0|&#xa0;|
|bullet|[BulletType](#bullettype)|&#xa0;|bullet shot|
|ejectEffect|[Effect](#effect)|none|shell ejection effect|
|reload|float|&#xa0;|weapon reload in frames|
|shots|int|1|amount of shots per fire|
|spacing|float|12|spacing in degrees between multiple shots, if applicable|
|inaccuracy|float|0|inaccuracy of degrees of each shot|
|shake|float|0|intensity and duration of each shot's screen shake|
|recoil|float|1.5|visual weapon knockback.|
|length|float|3|shoot barrel y offset|
|width|float|4|shoot barrel x offset.|
|velocityRnd|float|0|fraction of velocity that is random|
|alternate|bool|false|shoot one arm after another, rather than all at once|
|lengthRand|float|0|randomization of shot length|
|shotDelay|float|0|delay in ticks between shots|
|ignoreRotation|boolean|false|whether shooter rotation is ignored when shooting.|
|targetDistance|float|1|if `turnCursor` is `false` for a mech, how far away will the weapon target.|
|shootSound|[Sound](#sound)|pew|&#xa0;|

Sprite:

-   `<name>` or `<name>-equip`



## UnitType

Extends [Content](#content)

|field|type|default|
|---|---|---|
|type|[BaseUnit](#baseunit)|&#xa0;|
|health|float|60|
|hitsize|float|7|
|hitsizeTile|float|4|
|speed|float|0.4|
|range|float|0|
|attackLength|float|150|
|rotatespeed|float|0.2|
|baseRotateSpeed|float|0.1|
|shootCone|float|15|
|mass|float|1|
|flying|boolean|&#xa0;|
|targetAir|boolean|true|
|rotateWeapon|boolean|false|
|drag|float|0.1|
|maxVelocity|float|5|
|retreatPercent|float|0.6|
|itemCapacity|int|30|
|buildPower|float|0.3|
|minePower|float|0.7|
|weapon|[Weapon](#weapon)|&#xa0;|
|weaponOffsetY|float|&#xa0;|
|engineOffset|float|&#xa0;|
|engineSize|float|&#xa0;|

Sprites:

-   `<name>`
-   `<name>-leg`
-   `<name>-base`


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


## StatusEffect

Extends [Content](#content)

*Not be be confused with [Effect](#effect)*, a status effect will give an entity special properties. Status effects are used as transitions between intermediate effects. If some a `wet` unit gets `shocked` it then gets 20 damage.

|field|type|default|notes|
|---|---|---|---|
|damageMultiplier|float|1|&#xa0;|
|armorMultiplier|float|1|&#xa0;|
|speedMultiplier|float|1|&#xa0;|
|color|[Color](#color)|white|&#xa0;|
|damage|float|&#xa0;|Damage (or healing) per frame.|
|effect|[Effect](#effect)|none|Random effect (0.15% per frame), on affected units.|

-   opposites: effect which reduces anothers lifetime.

Built-in status effects:

-   `none` &#x2013; Does nothing.

-   `burning`
    
    |field|value|
    |---|---|
    |damage|0.06|
    |effect|burning|
    
    -   opposites: `wet` `freezing`
    -   tarred: 1 damage and keeps burning

-   `freezing`
    
    |field|value|
    |---|---|
    |speedMultiplier|0.6|
    |armorMultiplier|0.8|
    |effect|freezing|
    
    -   opposites: `melting` `burning`

-   `wet`
    
    |field|value|
    |---|---|
    |speedMultiplier|0.9|
    |effect|wet|
    
    -   opposites: `burning`
    -   shocked: 20 damage

-   `melting`
    
    |field|value|
    |---|---|
    |speedMultiplier|0.8|
    |armorMultiplier|0.8|
    |damage|0.3|
    |effect|melting|
    
    -   opposites: `wet` `freezing`
    -   tarred: keeps melting

-   `tarred`
    
    |field|value|
    |---|---|
    |speedMultiplier|0.6|
    |effect|oily|
    
    -   burning: keeps burning
    -   melting: keeps burning

-   `overdrive`
    
    |field|value|
    |---|---|
    |armorMultiplier|0.95|
    |speedMultiplier|1.15|
    |damageMultiplier|1.4|
    |damage|-0.01|
    |effect|overdriven|

-   `shielded`
    
    |field|value|
    |---|---|
    |armorMultiplier|3|

-   `boss`
    
    |field|value|
    |---|---|
    |armorMultiplier|3|
    |damageMultiplier|3|
    |speedMultiplier|1.1|

-   `shocked` &#x2013; Does nothing.

-   `corroded`
    
    |field|value|
    |---|---|
    |damage|0.1|



# Graphics



## Layer

Layers is an enumeration type, which the renderer will use to group rendering order:

-   `block`, base block layer;
-   `placement`, for placement;
-   `overlay`, first overlay stuff like conveyor items;
-   `turret`, "high" blocks like turrets;
-   `power` power lasers



## Color

Color is a hexadecimal string, `<rr><gg><bb>` for example:

-   `ff0000` is red,
-   `00ff00` is green,
-   `0000ff` is blue,
-   `ffff00` is yellow,
-   `00ffff` is cyan,
-   *ect..*



## CacheLayer

Flags used by for cache render:

-   `normal` normal layer;
-   `walls` walls layer;
-   `water` water layer, adding tile water shaders, and giving wave reflections;
-   `tar` tar layer, adding tar shaders, making it darker and giving it some bubble reflections;



# Entities



## BulletType

[Abstract](#faq) type which extends [Content](#content)

BulletType can either be an object `{}` or a `"string"`, where a string would be reusing [Built-in Bullets](#built-in-bullets) and an object would be making a custom one.

There are two major categories of bullet types:

-   [BasicBulletType](#basicbullettype) and,
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
            "type": "LiquidBulletType",
            "liquid": "oil",
            "lifetime": 2,
            "speed": 1,
            "fragBullets": 2,
            "fragBullet": {
                "type": "LiquidBulletType",
                "liquid": "slag",
                "lifetime": 1,
                "speed": 2,
                "damage": 1,
            }
        }
    }

![img](images/green-cyan-oil-slag-missiles.png)

|field|type|default|notes|
|---|---|---|---|
|lifetime|float|&#xa0;|amount of ticks the bullet will last|
|speed|float|&#xa0;|inital speed of bullet|
|damage|float|&#xa0;|collision damage|
|hitSize|float|4|collision radius|
|drawSize|float|40|&#xa0;|
|drag|float|0|decelleration per tick|
|pierce|boolean|&#xa0;|whether it can collide|
|hitEffect|[Effect](#effect)|&#xa0;|created when bullet hits something|
|despawnEffect|[Effect](#effect)|&#xa0;|created when bullet despawns|
|shootEffect|[Effect](#effect)|&#xa0;|created when shooting|
|smokeEffect|[Effect](#effect)|&#xa0;|created when shooting|
|hitSound|Sound|&#xa0;|made when hitting something or getting removed|
|inaccuracy|float|0|extra inaccuracy|
|ammoMultiplier|float|2|how many bullets get created per item/liquid|
|reloadMultiplier|float|1|multiplied by turret reload speed|
|recoil|float|&#xa0;|recoil from shooter entities|
|killShooter|float|&#xa0;|whether to kill the shooter when this is shot. (for suicide bombers)|
|knockback|float|&#xa0;|Knockback in velocity.|
|hitTiles|boolean|true|Whether this bullet hits tiles.|
|status|[StatusEffect](#statuseffect)|none|Status effect applied on hit.|
|statusDuration|float|600|Intensity of applied status effect in terms of duration.|
|collidesTiles|boolean|true|Whether this bullet type collides with tiles.|
|collidesTeam|boolean|false|Whether this bullet type collides with tiles that are of the same team.|
|collidesAir|boolean|true|Whether this bullet type collides with air units.|
|collides|boolean|true|Whether this bullet types collides with anything at all.|
|keepVelocity|boolean|true|Whether velocity is inherited from the shooter.|
|fragBullets|int|9|Number of frag bullets created.|
|fragVelocityMin|float|0.2|Minimum random multiplier.|
|fragVelocityMax|float|1|Maximum random multiplier.|
|fragBullet|[BulletType](#bullettype)|null|The frag bullet that will be created, may be a string, an object or null. If field is null, no frag bullet is created.|
|instantDisappear|boolean|&#xa0;|Whether to instantly make the bullet disappear. (used in crawlers to make sure they explode)|
|splashDamage|float|0|Area of effect damage when the bullet despawns or hits a target. Damage is calculated with [linear interpolation](https://en.wikipedia.org/wiki/Linear_interpolation), also known as lerp.|
|splashDamageRadius|float|-1|Use a negative value to disable splash damage. `splashDamageRadius` is a value used in the equation `lerp(1 - distance / radius, 1, 0.4)` which is a multiplier for `splashDamage`.|
|incendAmount|int|0|&#xa0;|
|incendSpread|float|8|&#xa0;|
|incendChance|float|1|&#xa0;|
|homingPower|float|0|Doesn't do anything complicated; if `homingPower` larger then `0.01` it gets rendered in the UI, if `homingPower` is larger then `0.0001` it allows `homingRange` to work.|
|homingRange|float|50|How close the bullet needs from a target in order to home/seek said target.|
|lightining|int|&#xa0;|&#xa0;|
|lightningLength|int|5|&#xa0;|
|hitShake|float|0|&#xa0;|



### BasicBulletType

Extends [BulletType](#bullettype)

This types purpose is to give basic bullets their sprites. The `bulletSprite` will be used as the shape of the bullet. The visible pixels in your sprites will be tinted with `backColor` and `frontColor` respectively. For example if you had sprites `router.png` and `router-back.png` where `Test Mod` was your mods name, you could do this to include your `bulletSprite`:

    {
        "type": "BasicBulletType",
        "bulletSprite": "test-mod-router"
    }

![img](images/router-bullets.png)

|field|type|default|&#xa0;|
|---|---|---|---|
|bulletWidth|float|5|&#xa0;|
|bulletHeight|float|7|&#xa0;|
|bulletShrink|float|0.5|Used to squishify the bullet as it gets closer to the target, where `0` is no shrink `-0.5` is stretching and `0.5` is shrinking.|
|frontColor|[Color](#color)|bulletYellow|Color of front sprite.|
|backColor|[Color](#color)|bulletYellowBack|Color of back sprite.|
|bulletSprite|String|bullet|Mapping sprite used to make the shape of the bullet.|

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



#### ArtilleryBulletType

Extends [BasicBulletType](#basicbullettype)

Makes special calculations to give the effect that the bullet is going up and back down.

|field|type|default|
|---|---|---|
|trailEffect|[Effect](#effect)|artilleryTrail|

Defaults:

|field|default|
|---|---|
|collidesTiles|false|
|collides|false|
|collidesAir|false|
|hitShake|1|
|hitSound|explosion|
|bulletSprite|shell|



#### FlakBulletType

Extends [BasicBulletType](#basicbullettype)

|field|type|default|notes|
|---|---|---|---|
|explodeRange|float|30|The range at which the bullets explode from enemies.|

Defaults:

|field|type|
|---|---|
|splashDamage|15|
|splashDamageRadius|34|
|hitEffect|flakExplosionBig|
|bulletWidth|8|
|bulletHeight|10|



#### MissileBulletType

Extends [BasicBulletType](#basicbullettype)

Weave is simple a sin wave with the following equation.

    rotation = sin(time/scale) * magnitude

|field|type|default|notes|
|---|---|---|---|
|trailColor|[Color](#color)|missileYellowBack|Color of the trail effect.|
|weaveScale|float|0|A larger `weaveScale` means a longer wave.|
|weaveMag|float|-1|A higher `weaveMag` means a higher (wider) wave.|

Defaults:

|field|default|
|---|---|
|bulletSprite|missile|



#### BombBulletType

Extends [BasicBulletType](#basicbullettype)

Defaults:

|field|default|
|---|---|
|collidesTiles|false|
|collides|false|
|bulletShrink|0.7|
|lifetime|30|
|drag|0.05|
|keepVelocity|false|
|collidesAir|false|
|hitSound|explosion|



### HealBulletType

Extends [BulletType](#bullettype) &#x2013; Bullets that can heal blocks of the same team as the shooter.

|field|type|default|
|---|---|---|
|healPercent|float|3|

Defaults:

|field|default|
|---|---|
|shootEffect|shootHeal|
|smokeEffect|hitLaser|
|hitEffect|hitLaser|
|despawnEffect|hitLaser|
|collidesTeam|true|



### LiquidBulletType

Extends [BulletType](#bullettype)

|field|type|default|notes|
|---|---|---|---|
|liquid|String|null|**[required]** name of [Liquid](#liquid)|

Defaults:

|field|default|
|---|---|
|lifetime|74|
|statusDuration|90|
|despawnEffect|none|
|hitEffect|hitLiquid|
|smokeEffect|none|
|shootEffect|none|
|drag|0.009|
|knockback|0.55|



### MassDriverBolt

Extends [BulletType](#bullettype)

Defaults:

|field|default|
|---|---|
|collidesTiles|false|
|lifetime|200|
|despawnEffect|smeltsmoke|
|hitEffect|hitBulletBig|
|drag|0.005|



### Built-in Bullets

$bullets

## Effect

Type should be a `string`. You can't currently create custom effects. List of built-in effects are as follows:

$effects

## TargetPriority

A higher ordinal means a higher priority. Higher priority blocks will always get targeted over those of lower priority, regardless of distance.

1.  `base`
2.  `turret`



# Objective

Objective is a trait, which a few types implement, which is used by [Zone](#zone) to give campaign maps objectives.

Types which implement Objective are as follows:

-   `ZoneWave` &#x2013; complete if best wave within `zone` is heigher then target `wave`
    
    |field|type|notes|
    |---|---|---|
    |zone|String|target [Zone](#zone) name|
    |wave|int|target wave to reach|

-   `Launched` &#x2013; complete if core launched from `zone`
    
    |field|type|notes|
    |---|---|---|
    |zone|String|target [Zone](#zone) name|

-   `Unlock` &#x2013; complete if `block` is unlocked
    
    |field|type|notes|
    |---|---|---|
    |block|String|target [Block](#block) name|



