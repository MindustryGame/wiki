# Modding

Mods in Mindustry are composed of a folder or zip file, containg a `mod.json` file, as well as a set of sprites and `.json` files defining new content. 

Make sure you look at [this repository](https://github.com/Anuken/ExampleMod) for an example of a simple mod. It may be simpler to download this example and edit it. Take your pick.

## Creating Your First Mod

First, create a folder for your mod. The name is irrelevant.
Then, create a `mod.json` file that will contain the metadata for your mod. It should look like this:

```json
{
  "name": "Mod Name",
  "author": "your name",
  "description": "the mod's description",
  "version": "1.0"
}
```

This defines what the mod will look like in the 'Mods' menu after it is imported.

## Importing Your Mods

There are two ways to import a mod:
1) Copy-paste the mod's folder into Mindustry's mod folder. On Steam, this is located in Mindustry's Steam installation directory: `steam/steamapps/common/Mindustry/mods`. On other desktop versions, this is located in `%appdata%/Mindustry/mods`. 
2) Zip up the contents of the mod folder (**not** the folder itself - only its contents) and import it through the file chooser in `Main Menu -> Mods -> Import Mod`. If a mod is already zipped up, skip the first step. This is not recommended for mod development, as you will have to re-import the mod every time you change something. 

