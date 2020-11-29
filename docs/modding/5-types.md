# Types

$allTypes


# Other

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


### Built-in Bullets

$bullets

## Effect

Type should be a `string`. You can't currently create custom effects. List of built-in effects are as follows:

$effects

## TargetPriority

A higher ordinal means a higher priority. Higher priority blocks will always get targeted over those of lower priority, regardless of distance.

1.  `base`
2.  `turret`

