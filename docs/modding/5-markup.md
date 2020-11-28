# Markup

The text renderer uses a simple makeup language for coloring text.

-   `[name]` sets the color by name, there's a few [built-in colors](#built-in-colors);
-   `[#rrggbb]` / `[#rrggbbaa]` sets the color by hex value, with each value being anything from `00` to `ff`:
    -   `rr` is the red value,
    -   `gg` is the green value,
    -   `bb` is the blue value,
    -   `aa` is the alpha value;
-   `[]` sets the color back to the previous color;
-   `[[` escapes the left bracket, so you can write `[[red]` to write and it'll render as `[red]`.

Notes:

-   errors/unknown colors will be silently ignored.

Example:

    [red]red
    [#ff0000]full-red
    [#ff000066]half-red
    [#ff000033]half-half-red
    [#00ff00]green
    []half-half-red



### Built-in Colors

    [clear]clear
    [black]black
    [white]white
    [lightgray]lightgray
    [gray]gray
    [darkgray]darkgray
    [blue]blue
    [navy]navy
    [royal]royal
    [slate]slate
    [sky]sky
    [cyan]cyan
    [teal]teal
    [green]green
    [acid]acid
    [lime]lime
    [forest]forest
    [olive]olive
    [yellow]yellow
    [gold]gold
    [goldenrod]goldenrod
    [orange]orange
    [brown]brown
    [tan]tan
    [brick]brick
    [red]red
    [scarlet]scarlet
    [coral]coral
    [salmon]salmon
    [pink]pink
    [magenta]magenta
    [purple]purple
    [violet]violet
    [maroon]maroon
