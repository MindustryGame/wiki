# Server UI Builder System

## Why this system exists

Servers were previously limited to `Call.menu`, which only allowed a plain grid of buttons, and nothing else.

UI builders add a way to create a dynamic, serializable UI tree on the server, with support for multiple return values per dialog.

*Note: This system is only available in build 160+.*

## An example dialog

```java
static int voteId; //ID of vote menu

static{
    //register handler once
    voteId = Menus.registerMenuBuilder((player, result) -> {
        Log.info(result); //for debugging

        if(result.is("vote1")){ //player pressed vote1 button
            MenuBuilder.of(
            """
            id: table1
            background: button
            margin: 10
            image{
              region: "ok"
              size: 300
            }
            row
            label: "you voted!!!!"
            """).id(voteId).update(player, "table1");
        }else if(result.is("vote2")){ //player pressed vote2 button
            MenuBuilder.of(
            """
            id: table2
            background: button
            margin: 10
            image{
              region: "ok"
              size: 300
            }
            row
            label: "you voted!!!!"
            """).id(voteId).update(player, "table2");
        }else if(result.is("ok")){ //player pressed 'ok' button (it has clicked: ok)
            //hide menu
            Call.hideMenuBuilder(player.con, voteId);
            //search label
            Call.infoMessage(player.con, "You typed: " + result.getString("searchLabel"));
        }
    });
}

public static void show(){
    //if you don't want to parse the DSL each time (might be a little slow), you can cache it with UiBuilder.parse("yourDsl") as a static field and pass that to MenuBuilder.
    MenuBuilder.of("""
    defaults{
      pad: 2
    }
    table{
      id: table1
      background: button
      margin: 10
      image{
        region: "ranai"
        size: 300
      }
      row
      //note: you can add a bundle to assets/bundles, and use "@somebundlekey" for text instead, which will automatically be localized!
      label: "Map 1"
    }
    table{
      id: table2
      background: button
      margin: 10
      image{
        //regions can be data patch regions too, e.g. dp-mysprite
        region: "cat"
        size: 300
      }
      row
      label: "Map 2"
    }
    row
    button{
      fillX: true
      height: 60
      text: "Vote for map 1"
      clicked: vote1
    }

    button{
      fillX: true
      height: 60
      text: "Vote for map 2"
      clicked: vote2
    }
    row
    table{
      colspan: 2
      height: 50
      growX: true
      image{
        region: zoom
        size: 32
        padRight: 8
      }
      label: "Input text here..."
      field{
        //by setting an ID, the value will be returned in the result, so you can call result.getString("searchLabel")
        id: searchLabel
        growX: true
      }
    }
    row
    button{
      icon: ok
      text: "Do something"
      //result will be 'ok' when this is clicked
      clicked: ok
      colspan: 2
      width: 200
      height: 60
    }
    """)
    .id(voteId) //menu ID, important, unless you're reusing IDs
    .title("Select Map") //can be null for no title table at all
    //.token(someLong) //you can pass an optional long token if you want to reuse menu IDs; this is returned in menu results, and can be used for tracking which specific menu the player had opened
    .hideOnClick(false) //do not hide automatically when a button is clicked
    .show(Groups.player.find(p -> !p.isLocal())); //show to first online player (for testing), substitute for proper person
}
```

## Builder API vs DSL

Both produce the same `NodeBuilder<?>` tree; pick whichever is easier for the situation. DSL is more compact for static layouts, while the Java builder is easier when the layout depends on data (loops, conditionals in Java itself).

**Builder API:**

```java
import static mindustry.ui.builder.UiBuilder.*;

TableBuilder ui = table()
    .add(defaults().pad(2))
    .add(
        table().background("button").margin(10)
            .add(image().region("ranai").size(300))
            .row()
            .add(label("Map 1"))
    )
    .row()
    .add(button("Vote for map 1").fillX().height(60).clicked("vote1"));

MenuBuilder.of(ui).id(voteId).title("Select Map").show(player);
```

**DSL:**

```java
MenuBuilder.of("""
defaults{
  pad: 2
}
table{
  background: button
  margin: 10
  image{
    region: "ranai"
    size: 300
  }
  row
  label: "Map 1"
}
row
button{
  fillX: true
  height: 60
  text: "Vote for map 1"
  clicked: vote1
}
""").id(voteId).title("Select Map").show(player);
```

## Editing & previewing DSL

For syntax highlighting, validation and autocomplete, consider installing the [VSCode plugin](https://github.com/Anuken/MindustryUiDslVSCode) or the [IntelliJ plugin](https://github.com/Anuken/MindustryUiDslIntelliJ).

Once you have that set up, open a `.msui` file in your preferred editor. Launch Mindustry, and in the console (enabled in Developer options, opened with F8), type:

`UiHotReload.show()`

This will open a file chooser window. Select your `.msui` file. The in-game dialog will now automatically display the layout file you're working on, and live-reload it when the file changes.

## Conditional layout (portrait vs landscape)

Nodes accept a `condition` string. If it evaluates false, that node is skipped entirely (not just hidden). This is checked on the client at build time, so it naturally reacts to whatever screen shape that specific player has.

Supported conditions: `"portrait"`, `"landscape"`, or `"<width|height> <op> <number>"` where `op` is one of `>=`, `>`, `<=`, `<`.

```js
table{
  condition: "landscape"
  row
  label: "Wide layout: map previews side by side"
}
table{
  condition: "portrait"
  row
  label: "Narrow layout: map previews stacked"
}
table{
  condition: "width >= 900"
  label: "Extra info panel, only on large screens"
}
```

Since this is evaluated per-client during tree build, each player sees the layout appropriate to their own window, from the same single DSL string sent by the server.

## More examples

### Player list with working search; builder API

Shows a list of players, filtered by a search box, with the filtered list rebuilt in place when you hit search. The menu handler is registered once in a static block.

`update(player, "list")` replaces a single element by id, not the whole dialog. The update builds the `pane{ id: list }` node with its rows and sends that, while the initial `show` call builds the full dialog (search bar included). That's why `buildList` is split out into its own method instead of being in `buildRoot`.

```java
//replace with real player names
static String[] players = {"Alice", "Bob", "Charlie", "Dave", "Eve", "Frank", "Grace", "Heidi", "Ivan", "Judy"};
static int listId;

static{
    listId = Menus.registerMenuBuilder((player, result) -> {
        if(result.is("search")){
            String query = result.getString("query", "");
            //rebuild inner contents of search pane
            MenuBuilder.of(buildList(query)).id(listId).update(player, "list");
        }else if(result.result != null && result.result.startsWith("kick:")){
            String target = result.result.substring("kick:".length());
            Call.infoMessage(player.con, "Kicked: " + target);
        }
    });
}

public static void showPlayerList(Player viewer){
    MenuBuilder.of(buildRoot("")).id(listId).hideOnClick(false).title("Players").show(viewer);
}

private static TableBuilder buildRoot(String query){
    return table()
    .add(defaults().pad(4))
    .add(
        table().growX()
        //note: enter("search") makes the text field fire 'search' when enter is pressed, for convenience
        .add(field(query).id("query").enter("search").hint("Search players...").growX())
        .add(button("Go").clicked("search"))
    )
    .row()
    .add(buildList(query));
}

private static PaneBuilder buildList(String query){
    TableBuilder rows = table();
    for(String name : players){
        if(!query.isEmpty() && !name.toLowerCase().contains(query.toLowerCase())) continue;
        rows.add(image("players").size(32f).padRight(5f))
        .add(label(name))
        .add(button("Kick").padRight(10f).width(150f).clicked("kick:" + name))
        .row();
    }
    return pane().id("list").add(rows);
}
```

The target player's name is baked directly into the `clicked` result string (`"kick:" + name`) since a plain button has nothing else to attach an id-backed value to. `hideOnClick(false)` is set on the initial `show` so the dialog stays open after hitting search or kicking someone, since both are meant to update the list in place rather than close the menu.

### Vote-kick confirmation with a slider threshold

```js
defaults{
  pad: 6
  width: 300
}
label{
  text: "Reason: tomfoolery."
  labelAlign: center
}
row
slider{
  id: threshold
  min: 1
  max: 8
  step: 1
  defaultValue: 3
  text: "Votes needed"
}
row
button{
  text: "Start Vote"
  icon: ok
  clicked: startVote
  fillX: true
  height: 50
}
```

The server reads `result.getFloat("threshold")` when `startVote` is returned.

### Server settings panel with checkboxes and grouped buttons

```js
defaults{
  pad: 8
}
check{
  id: Bingus
  text: "Enable bingus"
  checked: true
}
check{
  id: frogs
  text: "Enable frogs"
  checked: false
}
row
label: "Difficulty"{ //placing it here is shorthand for text
  colspan: 2
  labelAlign: center
  fillX: true
}
row
table{
  colspan: 2
  defaults{
    width: 200
    height: 50
  }
  button: "Easy"{ //also shorthand for text
    group: difficulty
    id: diffEasy //no clicked: here because it shouldn't close the dialog
    style: togglet
  }
  button: "Normal"{
    group: difficulty
    id: diffNormal
    style: togglet
  }
  button: "Insufferable"{
    group: difficulty
    id: diffInsufferable
    style: togglet
  }
}
row
button: "Save"{
  clicked: save
  colspan: 2
  fillX: true
  height: 50
}
```

`group: difficulty` makes the three difficulty buttons mutually exclusive (a `ButtonGroup`), and their `checked` state comes back in `values` for any id'd checkable element, so the server can read which one is currently selected when 'save' is pressed.

## Cell properties

These apply to the *cell* a node occupies in its parent table, mirroring `scene2d` table layout. Boolean properties take no value on the builder API (just call the method); in the DSL they're written as `key: true` or `key: false`.

| Property | Type | Description                                                                                                           |
|---|---|-----------------------------------------------------------------------------------------------------------------------|
| `grow` | bool | Expand and fill in both directions.                                                                                   |
| `growX` | bool | Expand and fill horizontally.                                                                                         |
| `growY` | bool | Expand and fill vertically.                                                                                           |
| `fill` | bool | Fill the cell in both directions (without expanding).                                                                 |
| `fillX` | bool | Fill the cell horizontally.                                                                                           |
| `fillY` | bool | Fill the cell vertically.                                                                                             |
| `expand` | bool | Take up extra available space in both directions.                                                                     |
| `expandX` | bool | Take up extra available horizontal space.                                                                             |
| `expandY` | bool | Take up extra available vertical space.                                                                               |
| `uniform` | bool | Force this cell's size to match other uniform cells in both directions.                                               |
| `uniformX` | bool | Force uniform width with other uniform cells.                                                                         |
| `uniformY` | bool | Force uniform height with other uniform cells.                                                                        |
| `width` | float | Fixed cell width.                                                                                                     |
| `height` | float | Fixed cell height.                                                                                                    |
| `size` | float | Fixed width and height at once.                                                                                       |
| `minWidth` | float | Minimum width.                                                                                                        |
| `maxWidth` | float | Maximum width.                                                                                                        |
| `minHeight` | float | Minimum height.                                                                                                       |
| `maxHeight` | float | Maximum height.                                                                                                       |
| `pad` | float | Padding on all sides.                                                                                                 |
| `padTop` | float | Top padding.                                                                                                          |
| `padLeft` | float | Left padding.                                                                                                         |
| `padBottom` | float | Bottom padding.                                                                                                       |
| `padRight` | float | Right padding.                                                                                                        |
| `align` | string | Alignment within the cell (`top`, `bottom`, `left`, `right`, `center`, `topLeft`, `botLeft`, `topRight`, `botRight`). |
| `colspan` | int | Number of columns this cell spans.                                                                                    |
| `color` | string | Tint color for the cell (hex string or color name, e.g. `"white"` or `"ffaa00"`). Applies to any node's cell regardless of type. |

Note: `defaults{}` blocks apply cell properties to every sibling node added after them within the same table body, but don't reach into nested `table{}`/`pane{}` blocks.

Note: `disabled` (bool) is also applied at the cell level, but only has an effect on elements implementing `Disableable` — `button`, `imageButton`, `field`, `check`, `slider`, and `buttonTable`. It sets the element's initial disabled state.

## Elements

| Node | Purpose                                                                                                                                                               | Example (DSL) |
|---|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|
| `table` | A nested table/container. Supports `background`, `margin`, `wrap` (switches to a `WrapTable` instead of `Table`, which ignores rows/columns).                         | `table{ background: button margin: 10 label: "hi" }` |
| `pane` | Scrollable container wrapping an inner table. Supports `style`.                                                                                                       | `pane{ label: "scrollable content" }` |
| `label` | Text label. Supports `text`, `wrap`, `style`, `labelAlign`. Resolves `@bundleKey` text itself, which can be sourced from bundles in the server assets/bundles folder. | `label: "Hello"` |
| `image` | An image from the texture atlas or an icon. Supports `region`/`icon`, `scaling`, `size`.                                                                              | `image{ region: "ok" size: 300 }` |
| `button` | Text button, optional icon. Supports `text`, `icon`, `style`, `clicked`, `group`, `checked`, `disabled`.                                                                          | `button{ text: "Vote" clicked: vote1 }` |
| `imageButton` | Icon-only button. Supports `icon`, `style`, `clicked`, `group`, `checked`, `disabled`.                                                                                            | `imageButton{ icon: ok clicked: confirm }` |
| `field` | Text input. Supports `text`, `hint`, `maxLength`, `style`, `disabled`, and `id` to read back the value.                                                                           | `field{ id: search hint: "Search..." growX: true }` |
| `check` | Checkbox. Supports `text`, `checked`, `style`, `group`, `disabled`, `id`.                                                                                                         | `check{ id: ranked text: "Ranked only" checked: true }` |
| `slider` | Slider. Supports `min`, `max`, `step`, `defaultValue`, `style`, `disabled`, `id`, `text`. Text can be a format string that contains `{0}` from a bundle.                                                                                                 | `slider{ id: kickVotes min: 1 max: 10 step: 1 defaultValue: 3 text: "Votes: " }` |
| `space` | Empty cell, useful as a spacer.                                                                                                                                       | `space` |
| `buttonTable` | A `Button` that also acts as a container for other nodes (a whole clickable table). Supports `style`, `clicked`, `group`, `margin`, `disabled`.                                             | `buttonTable{ clicked: pick1 label: "Map 1" }` |
| `defaults` | Not a real element; sets cell property defaults for later siblings in this block.                                                                                     | `defaults{ pad: 4 }` |
| `row` | Not a node; ends the current row and starts a new one.                                                                                                                | `row` |

Any node with an `id` set has its element registered by that id. For interactive elements (`field`, `slider`, `check`, checkable `button`/`buttonTable`), that id is what shows up as a key in `MenuResult.values` when any button with a `clicked` result fires.


# Button Styles

Reference for the style names available on `Styles`, usable via `style: "name"` on `button`/`buttonTable` (`TextButtonStyle`) and `imageButton` (`ImageButtonStyle`) nodes.

## Text button styles (button element)

| Name | Description |
|---|---|
| `defaultt` | Default text button style, gray corners at 45 degrees. |
| `flatt` | Flat, square, opaque. |
| `grayt` | Flat, square, opaque, gray. |
| `flatTogglet` | Flat, square, toggleable. |
| `flatBordert` | Flat, square, gray border. |
| `nonet` | No background whatsoever, only text. |
| `logicTogglet` | Similar to `flatToggle`, but slightly tweaked for logic. |
| `flatToggleMenut` | Similar to `flatToggle`, but with a transparent base background. |
| `togglet` | Toggle variant of the default style. |
| `cleart` | Partially transparent square button. |
| `clearTogglet` | Clear, square, orange border, toggleable. |
| `fullTogglet` | Similar to `flatToggle`, but without a darker border. |
| `squareTogglet` | Toggle-able version of `flatBorder`. |
| `logict` | Special square button for logic dialogs. |

## Image button styles (imageButton element)

| Name | Description |
|---|---|
| `defaulti` | Default image button style, gray corners at 45 degrees. |
| `nodei` | Used for research nodes in the tech tree. |
| `emptyi` | No background, tints the image itself when hovered. |
| `emptyTogglei` | Toggleable variant of `emptyi`. |
| `selecti` | Displays a border around the image when selected, used in the placement fragment. |
| `logici` | Pure black version of `emptyi`, used for the logic toolbar. |
| `geni` | Used for the toolbar in map generation filters. |
| `grayi` | Gray, toggleable, no background. |
| `graySquarei` | Gray square background, standard behavior. Equivalent to `grayt`. |
| `flati` | Flat, square, black background. |
| `squarei` | Square border. |
| `squareTogglei` | Square border, toggleable. |
| `grayTogglei` | Square border, toggleable. |
| `clearNonei` | No background unless focused, no border. |
| `cleari` | Partially transparent black background. |
| `clearTogglei` | Toggleable variant of `cleari`. |
| `clearNoneTogglei` | `clearNone`, but toggleable. |

*Note: buttonTable elements can use any of these button styles.*
