# <img id="spr" src="/wiki/images/block-bridge-conveyor-large.png"></img> Bridge Conveyor

*"Advanced item transport block. Allows transporting items over up to 3 tiles of any terrain or building."*


|General||
| --- | --- |
|Internal Name|`bridge-conveyor`|
|Solid|Yes|
|Health|40    |
|Size|1x1  |
|Build Time|0.08  seconds  |
|Build Cost|<a href="/wiki/items/copper"><img id="spr" src="/wiki/images/item-copper-xlarge.png"/></a>x4 <a href="/wiki/items/lead"><img id="spr" src="/wiki/images/item-lead-xlarge.png"/></a>x4  |

|Items||
| --- | --- |
|Item Capacity|10  items  |


--- 
[comment]: # (WARNING: Do not modify the text above. It is automatically generated every release.)

## Bridge Mechanics

A bridge consists of multiple directionally connected bridge blocks. Each bridge block can have up to one destination set, and an unlimited number of incoming connections from other bridge blocks. Each bridge block has its own separate inventory of 10 items, such that a bridge consisting of three chained bridge blocks has a total capacity of up to 30 items. Bridges cannot be unloaded by Unloaders.

Once a bridge block is placed, you may set its destination to any other bridge block up to four tiles away in any of the four cardinal directions (up, down, left, right) by selecting the bridge block and then pressing the bridge block you want to connect it to. You may not set a bridge block's destination to a bridge which it already has an incoming connection from. If you wish to change the direction of a bridge connection, you must first disconnect the source block by pressing it twice.

Bridge blocks which have a destination set will accept items from adjacent blocks in any direction except the direction their destination is in. For example, a simple source bridge with its destination set to another bridge block four tiles its right will accept items from adjacent blocks on its top, left, and bottom, but not from an adjacent block on its right. This restriction applies even if the adjacent block in question is another bridge block with its destination set to the first block. Note that this restriction only applies to adjacent blocks. In the previous example, the bridge block on the left would accept items from an incoming bridge connection from its right without issue, just so long source block for that connection had at least one tile of empty space between it and the bridge block on the left.

Bridge blocks which do not have a destination set will not accept items from any source except incoming connections from other bridges. Instead, they will actively output their contents into available adjacent blocks in any direction that they do not have a bridge connection coming from. For example, a bridge block with no destination set and three incoming bridge connections from its top, left, and right will only emit its contents to the block below it, but a bridge block with no destination set and only one incoming bridge connection from its left will output items to any available space on its top, right, and bottom. Bridge blocks with a set destination will not output items to any block except the one their destination is set to.