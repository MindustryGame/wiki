# Scripting

Mindustry uses JavaScript for mod scripting. Scripts use the `js` extension and are placed in the `scripts/` subdirectory.

Execution starts with the file named `main.js`. Any other script files can be imported by the main file with `require("script_name")`. 
A typical setup looks like this:

*scripts/main.js*:
```js

require("blocks");
require("items");

```

*scripts/blocks.js*:
```js
const myBlock = extend(Conveyor, "terrible-conveyor", {
  //various overrides...
});

myBlock.health = 200;
//...
```

*scripts/items.js*:
```js

const terribleium = Item("terribleium");
terribleium.color = Color.valueOf("ff0000");
//...

```

# Examples

## Listening to events

```js

//listen for the event where a unit is destroyed
Events.on(UnitDestroyEvent, event => {
  //display toast on top of screen when the unit was a player
  if(event.unit.isPlayer()){
    Vars.ui.hudfrag.showToast("Pathetic.");
  }
})

```

<img src="/wiki/images/misc/modding-pathetic.gif">

## Displaying a dialog box

```js
const myDialog = new BaseDialog("Dialog Title");
//Add "go back" button
myDialog.addCloseButton();
//Add text to the main content
myDialog.cont.add("Goodbye.");
//Show dialog
myDialog.show();
```

//TODO test these out and add more examples
