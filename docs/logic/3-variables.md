# Variables and Constants

Variables and constants are essentially "containers" of values. Each one has a name and value. Mindustry has variables which can be set by the user and their code, and constants which are set only by the processor and cannot be changed by the user. 

*To find out the possible data or parameter types of a variable or constant, see the Glossary.*

## Variables

### Creating and Changing Variables

Variables are what their name suggests; a value that can be changed.

For example, in this code: `set myVariable 3`, the `set` instruction will create a variable named `myVariable`, and give it a value of `3`.

Later on, this can change its value to `9`: `set myVariable 9`.

Notice how we used the same instruction for both creating and changing variables. This is because **if a variable that it's changing does not already exist, an instruction will create it first.** If you know Python, you'll probably have realized that it works in the same way.

Another example is using `sensor`: `sensor playerX playerUnit @x` (or Sensor playerX = @x in playerUnit for the visual editor).

Assuming that the player's position is `141, 20`, a variable named `playerX` will be created first, then assigned a value of `141`.

However, we have another variable in the example called `playerUnit`. That variable is a **parameter**. A parameter is an input value to an instruction. In this case, we probably got `playerUnit` from the `radar` instruction. If a parameter is not provided or is invalid, the instruction will not execute.

### Data Types and Implicit Conversion

The values in variables, of course, have different types that are specific to different sources and purposes, such as `Unit` for Units, `number` for any number, etc. You can find a list of all of them in the Glossary.

Mindustry Logic also has this thing with variables called **Implicit Conversion**. That means that, if needed, it will convert a variable's value from one type to another.

If an instruction is given a `number`, but it needs an `Object`, it will be converted to `null`. If an instruction needs a `number`, but is given an `Object`, it will be converted to 1 if the object isn't `null`, otherwise 0.

Examples:

* `53` -> `null`
* `null` -> 0,
* `Object` which is a Silicon Crucible -> 1

The `print` instruction is the only instruction that requires a `String` as an input, so its rules are stated in its own part of the manual.

### Variable Naming

Naming variables properly is an important skill to have when programming in general. It helps to make code easier to read and understand. Thus, that can make it easier for people to learn from or fix your code.

Variable names can contain any typeable character. However, they cannot be purely numbers, since it will instead use the actual number.

The usual naming convention among the majority of mlog code is camelCase, an example of which is itself. Examples of variables named using camelCase are: `playerX`, `coreFound`, `vertexAngle`. 

**When naming variables, make sure they are descriptive yet short.** They must describe the value they hold or their purpose. At the same time, they shouldn't be complete sentences or span the entire page, or be too short that they get confusing. You can use abbreviations, acronyms, or shorter terms to make them more concise.

Everybody has their own specific styles and preferences, but try to learn from good examples of code in mlog and other languages, while at the same time staying close to the common style.

## Processor Variables and Constants

Constants also hold values, but cannot be changed. Each processor has these constants and variables built-in:

### Processor

#### @this `constant` `Building`

A `Building` Object that represents the processor itself. You can use this with `sensor` to find various properties about the processor.

#### @thisx `constant` `number`

The x coordinate of the processor.

#### @thisy `constant` `number`

The y coordinate of the processor.

#### @counter `variable` `number`

A variable that represents the next line the processor will read code from, equivalent to `%IP` in x86. It can be changed like any other variable as another way to perform jumps.

An (advanced) example of setting `@counter` to jump to a function, then jump back to the caller:

```
op add retAddr @counter 1 # Save where we will continue after the function returns by adding 1 to the counter
set @counter myFunc       # Jump to the line representing myFunc
...
set @counter retAddr      # Return to the line set earlier after the function is called
```
### Links

#### @links `constant` `number`

A constant that equals the number of buildings linked to the processor. It is changed by the processor when blocks are linked or unlinked.

You can use this along with `getlink` to loop through all linked buildings, like so:

```
set linkIter 0                  # Create iterator variable
getlink block linkIter          # Get Building Object of the "linkIter"th linked building.
# Do what you want with the building here
jump 1 lessThan linkIter @links # Loop
```

#### <buidingName><n> `constant` `Building`

This is really multiple constants, one for each building linked to the processor. They are removed or added whenever a building is unlinked or linked to the processor.

`buildingName` represents the building's **internal name**, which you can find in the rest of the Wiki. 

`n` starts at 1 and increases with each building of that type that are linked. It's sort of like the `n`th building of a type.

This can be a little hard to understand, so here are some examples:

* The first Scatter linked to a processor: `scatter1`
* The third Ripple linked: `ripple3`
* The second Laser Drill linked: `drill2`
* The eleventh Spore Press linked: `press11`

You can also view each linked building's "constant name" over them when the processor is selected.

<img src="/wiki/images/misc/logic-variables-constants-links-linkedBuilding.png">

### Misc

#### @unit `constant` `Unit`

A constant that represents the current bound unit. It only changes when the processor unbinds a unit, or binds another one. It can be accessed using Unit instructions such as `ucontrol`, `ulocate`, and `uradar`. Since it's a Unit Object, you can also use it with `sensor`.

This presents a core part of unit control in mlog; **only one unit can be bound at a time.** However, you can reference this in a variable, like `set unitReference @unit`. That variable, though, can not be used to get information about or control the referenced unit. It can only be used to check against other units. Therefore, you can think of it as a "unit identity".

#### @time `constant` `number`

Represents the current UNIX timestamp *in milliseconds*.

#### @mapw `constant` `number`

Width of the map, in tiles.

#### @maph `constant` `number`

Height of the map, in tiles.
