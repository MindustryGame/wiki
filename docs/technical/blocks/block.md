# Variables:

### name (String)
Internal name for the block, is final

### formalName (String)
Displayed name for the block

### fullDescription (String)
Description of the block, is final

### update (Boolean)
Whether the block has a tile entity and should update

### destructible (Boolean)
Whether the block has health and can be destroyed

### solid (Boolean)
Whether the block is solid

### solidifes (Boolean)
Whether this block can be solid

### rotate (Boolean)
Whether this block is rotateable

### breakable (Boolean)
Whether you can break/deconstruct this block

### placeableOn (Boolean, true)
Whether you can place blocks on this block (as a floor)

### health (Integer, -1)
Tile entity health

### baseExplosiveness (Float, 0f)
The base explosiveness of the block

### floating (Boolean, false)
Whether this block can be placed on liquids

### drops (ItemStack, null)
Items that are dropped when the block is destroyed

### size (Integer, 1)
The size of the block, the block size is size*size

### expanded (Boolean, false)
Whether to draw the block in the expanded draw range

### timers (Integer, 0)
Max of timers used

### cacheLayer (CacheLayer, CacheLayer.normal)
Only used for 'cached' rendering

### layer (Layer, null)
The layer to draw extra graphics on

### layer2 (Layer, null)
The extra layer to draw extra extra graphics on

### alwaysReplace (Boolean, false)
Whether this block will be replaced in all cases

### instantTransfer (Boolean, false)
Whether this block has instant transfer checking. Used for calculations to prevent infinite loops

### group (BlockGroup, BlockGroup.none)
The block group. Unless canReplace method return false, blocks in the same group can replace each other

### bars (BlockBars, new BlockBars)
List of displayed block status bars. Defaults to health bar.

### stats (BlockStats, new BlockStats)
List of block stats

### flags (EnumSet<BlockFlag>)
List of block flags, used for AI indexing

### autoSleep (Boolean)
Whether to automatically set the entity to 'sleeping' when created

### shadow (String, null)
The name of the shadow region to load. Null to indicate normal shadow

### configurable (Boolean)
Whether this block can be tapped and selected to configure

### consumesTap (Boolean)
Whether this block consumes touchDown events when Tapped

### minimapColor (Color, Color.CLEAR)
The color of the block when displayed on the minimap or map preview

### viewRange (Float, 10f)
View range of this block type. Use a value that is less than zero (0) to disable

### turretIcon (Boolean, false)
Whether the top icon is outlined, like a turret

### targetable (Boolean, true)
Whether units can target this block

### canOverdrive (Boolean, true)
Whether the overdrive projector can boost this block

### tempTiles (Array<Tile>, new Array) protected

### tempColor (Color, new Color) protected

### blockIcon (TextureRegion[])

### icon (TextureRegion[])

### compactIcon (TextureRegion[])

### editorIcon (TextureRegion)

### shadowRegion (TextureRegion)

### region (TextureRegion)

# Methods

# getByProduction (takes Array<Block> + Content result) static

# canBreak (returns Boolean, takes Tile tile)

# dropsItem (returns Boolean, takes Item item)

# updatePowerGraph (takes Tile tile)

# powerGraphRemoved (takes Tile tile)

# getPowerConnections (returns Array<Tile> tile, takes Tile + Array<Tile> out)

# isLayer (returns Boolean, takes Tile tile)

# isLayer2 (returns Boolean, takes Tile tile)

# drawLayer (takes Tile tile)

# drawLayer2 (takes Tile tile)

# drawSelect (takes Tile tile)

# drawPlace (takes Integer x + Integer y + Integer rotation + Boolean valid)

# playerPlaced (takes Tile tile)

# removed (takes Tile tile)

# placed (takes Tile tile)

# unitOn (takes Tile tile + Unit unit)

# canPlaceOn (takes Tile tile)

# useContent (takes Tile tile + UnlockableContent content)

# getContentType (returns ContentType)
By default returns ContentType.block

# getContentName (returns String)
By default returns variable name

# init ()

# load ()

# transformLinks (takes Tile tile + Integer oldWidth + Integer oldHeight + Integer newWidth + Integer newHeight + Integer shiftX + Integer shiftY)

# tapped (takes Tile tile + Player player)

# getCursor (returns CursorType, takes Tile tile)
By default 
if configurable is true returns CursorType.hand
else returns CursorType.normal

# buildTable (takes Tile tile + Table table)

# onConfigureTileTapped (returns Boolean, takes Tile tile + Tile other)
By default check if tile is not other

# shouldShowConfigure (returns Boolean, takes Tile tile + Player player)
By default returns true

# shouldHideConfigure (returns Boolean, takes Tile tile + Player player)
By default returns false

# syntethic (returns Boolean)
By default if either update, destructible or solid are true returns true

# drawConfigure (takes Tile tile)

# setStats ()

# setBars ()

# name (returns String)
By default returns variable name

# isSolidFor (returns Boolean, takes Tile tile)
By default returns false

# canReplace (returns Boolean, takes Block other)

# handleDamage (returns Float, takes Tile tile + Float amount)
By default returns amount

# handleBulletHit (takes TileEntity entity + Bullet bullet)
By default call entity.damage with arguments bullet.getDamage

# Update (takes Tile tile)

# isAccessible (returns Boolean)
By default returns true if variable hasItems AND itemCapacity is more than zero (0)

# afterDestroyed (takes Tile tile + TileEntity entity)

# onDestroyed (takes Tile tile)

# getFlammability (returns Float, takes Tile tile)

# getEditorIcon (returns TextureRegion)

# getIcon (returns TextureRegion[])

# getBlockIcon (returns TextureRegion[])

# getCompactIcon (returns TextureRegion[])

# iconRegion (returns TextureRegion, takes TextureRegion src)
Crops a region to 8*8

# hasEntity (returns Boolean)
By default returns true if destructible or update is true

# newEntity (returns TileEntity) 
By default returns new TileEntity

# draw (takes Tile tile)

# drawNonLayer (takes Tile tile)

# drawShadow (takes Tile tile)

# offset (returns Float)

# isMultiblock (returns Boolean)
By default returns true if variable size is larger than one (1)

# getDebugInfo (returns Array<Object>, takes Tile tile)
