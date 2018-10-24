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

### static getByProduction (Array<Block>, Content result)

### Boolean canBreak (Tile tile)

### Boolean dropsItem (Item item)

### updatePowerGraph (Tile tile)

### powerGraphRemoved (Tile tile)

### Array<Tile> getPowerConnections (Tile tile, Array<Tile> out)

### Boolean isLayer (Tile tile)

### Boolean isLayer2 (Tile tile)

### drawLayer (Tile tile)

### drawLayer2 (Tile tile)

### drawSelect (Tile tile)

### drawPlace (Integer x, Integer y, Integer rotation, Boolean valid)

### playerPlaced (Tile tile)

### removed (Tile tile)

### placed (Tile tile)

### unitOn (Tile tile, Unit unit)

### canPlaceOn (Tile tile)

### useContent (Tile tile, UnlockableContent content)

### ContentType getContentType ()
By default returns ContentType.block

### String getContentName ()
By default returns variable name

### init ()

### load ()

### transformLinks (Tile tile, Integer oldWidth, Integer oldHeight, Integer newWidth, Integer newHeight, Integer shiftX, Integer shiftY)

### tapped (Tile tile, Player player)

### CursorType getCursor (Tile tile)
By default 
if configurable is true returns CursorType.hand
else returns CursorType.normal

### buildTable (Tile tile, Table table)

### Boolean onConfigureTileTapped (Tile tile, Tile other)
By default check if tile is not other

### Boolean shouldShowConfigure (Tile tile, Player player)
By default returns true

### Boolean shouldHideConfigure (Tile tile, Player player)
By default returns false

### Boolean syntethic ()
By default if either update, destructible or solid are true returns true

### drawConfigure (Tile tile)

### setStats ()

### setBars ()

### String name ()
By default returns variable name

### Boolean isSolidFor (Tile tile)
By default returns false

### Boolean canReplace (Block other)

### Float handleDamage (Tile tile, Float amount)
By default returns amount

### handleBulletHit (TileEntity entity, Bullet bullet)
By default call entity.damage with arguments bullet.getDamage

### Update (Tile tile)

### Boolean isAccessible ()
By default returns true if variable hasItems AND itemCapacity is more than zero (0)

### afterDestroyed (Tile tile, TileEntity entity)

### onDestroyed (Tile tile)

### Float getFlammability (Tile tile)

### TextureRegion getEditorIcon ()

### TextureRegion[] getIcon ()

### TextureRegion[] getBlockIcon ()

### TextureRegion[] getCompactIcon ()

### TextureRegion iconRegion (TextureRegion src)
Crops src region to 8*8

### Boolean hasEntity ()
By default returns true if destructible or update is true

### TileEntity newEntity () 
By default returns new TileEntity

### draw (Tile tile)

### drawNonLayer (Tile tile)

### drawShadow (Tile tile)

### Float offset ()

### Boolean isMultiblock ()
By default returns true if variable size is larger than one (1)

### Array<Object> getDebugInfo (Tile tile)
