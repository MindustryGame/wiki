# Markup

The text renderer uses a simple markup language for coloring text.

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

    [clear]clear (#00000000)
    [black]black (#000000FF)
    [white]white (#FFFFFFFF)
    [lightgray]lightgray (#BFBFBFFF)
    [gray]gray (#7F7F7FFF)
    [darkgray]darkgray (#3F3F3FFF)
    [blue]blue (#0000FFFF)
    [navy]navy (#00007FFF)
    [royal]royal (#4169E1FF)
    [slate]slate (#700090FF)
    [sky]sky (#87CEEBFF)
    [cyan]cyan (#00FFFFFF)
    [teal]teal (#007F7FFF)
    [green]green (#00FF00FF)
    [acid]acid (#7FFF00FF)
    [lime]lime (#32CD32FF)
    [forest]forest (#228B22FF)
    [olive]olive (#6B8E23FF)
    [yellow]yellow (#FFFF00FF)
    [gold]gold (#FFD700FF)
    [goldenrod]goldenrod (#DAA520FF)
    [orange]orange (#FFA500FF)
    [brown]brown (#8B4513FF)
    [tan]tan (#D2B48CFF)
    [brick]brick (#B22222FF)
    [red]red (#FF0000FF)
    [scarlet]scarlet (#FF341CFF)
    [coral]coral (#FF7F50FF)
    [salmon]salmon (#FA8072FF)
    [pink]pink (#FF69B4FF)
    [magenta]magenta (#FF00FFFF)
    [purple]purple (#8000FFFF)
    [violet]violet (#EE82EEFF)
    [maroon]maroon (#B03060FF)
