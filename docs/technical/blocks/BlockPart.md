extends [block](/technical/block.md)

## Constructor
call super("blockpart")
set solid false
set hasPower, hasItems and hasLiquids true
set viewRange -1

# Methods

### Overrides Draw (Tile tile)
Overriden to do nothing

### Overrides DrawShadow (Tile tile)
Overriden to do nothing

### Overrides Boolean isSolidFor (Tile tile)
Overriden to check if 
tile.getLinked is null,
tile.getLinked().block is instance of BlockPart,
tile.getLinked().solid or
tile.getLinked().block().isSolidFor(tile.getLinked)

### Overrides handleItem (Item item, Tile tile, Tile source)
Overriden to call
tile.getLinked().block().handleItem(item, tile.getLinked(), source)

### Overrides Boolean acceptItem (Item item, Tile tile, TIle source)
Overriden to call
tile.getLinked().block().acceptItem(item, tile.getLinked(), source)

### Overrides Boolean acceptLiquid (Tile tile, Tile source, Liquid liquid, float amount)
Overriden to return
linked(tile).hasLiquids and linked(tile).acceptLiquid(tile.getLinked(), source, liquid, amount)

### Overrides handleLiquid (Tile tile, Tile source, Liquid liquid, float amount)
Overriden to return
linked(tile).handleLiquid(tile.getLinked(), source, liquid, amount)

### Overrides float addPower (Tile tile, float amount)
Overriden to check 
if linked(tile).hasPower
if true return linked(tile).addPower(tile.getLinked(), amount)
if false return amount

### Overrides Boolean acceptPower (Tile tile, Tile from, float amount)
Overriden to return
block.hasPower and block.acceptPower(tile.getLinked(), from, amount)

### private Block linked (Tile tile)
returns tile.getLinked().block()
