# Plugins & JVM Mods

Mindustry supports loading `jar` files with Java bytecode on desktop & Android. These function similarly to JS mods, and must supply a single main class to instantiate when the mod is created.

Theoretically, all JVM languages should be supported.

Jar/JVM mods use the same `mod.hjson` meta file that standard mods do, with one addition: The *fully qualified main class* can be specified with `main: "mypackage.MyMod"`. This class should extend `mindustry.mod.Mod`.


If a main class is not specified, it defaults to `modnameinlowercase.ModName + "Mod".`

A simple `mod.hjson` for a Java mod could look like this:

```hjson
name: "Nothing"
author: "Yourself"
main: "nothing.NothingMod"
description: "..."
version: "99.99"
```

See the [example Java mod repo](https://github.com/Anuken/ExampleJavaMod), the [example Kotlin mod repo](https://github.com/Anuken/ExampleKotlinMod) or the [Java mod template](https://github.com/Sonnicon/mindustry-modtemplate) for more information.

## Plugins

Plugins are Java mods that are intended to be run on servers only. Usually, these add *new commands* or *new gamemodes*.
All plugin main classes should extend `mindustry.mod.Plugin`. This makes them implicitly *hidden* - clients will not need to download the plugin to join the server. They are server-side only.

Plugins name their meta file `plugin.[h]json`. The file structure is identical to that of other Java mods - see above for details.

You can see an example plugin [here](https://github.com/Anuken/ExamplePlugin). For a more practical example that can be used on real servers, see [this repo](https://github.com/Anuken/AuthorizePlugin).

## Importing

Unlike JS or JSON mods, JAR mods need to be compiled. This means that they cannot be imported directly from Github - instead, *Github Releases* are used. 

When a user tries to install a JAR mod, Mindustry will check the latest (and *only* the latest) Github release for `.jar` artifacts. When the first artifact is found, it is downloaded to the client. Note that pre-releases are ignored.

I recommend using Github Actions (or any other CI) to automatically build and upload jar artifacts to new releases.

## Capabilities & Security

As jar mods are loaded directly through a URLClassLoader with no sandboxing, they do not have any security limitations. This means:

- All Java APIs can be accessed.
- Reflection can be used to access private/hidden properties.
- Mods have full access to the client's computer, opening the door to potentially malicious actions.
- Mods can change game files or core rewrite bytecode.

Thus, you should *never import jar mods from untrusted sources.* Now, you may be wondering: Why aren't jar mods sandboxed? Isn't that a massive security risk? 

The answer is: *Yes*, it is. However, there are no good alternatives. Even if I implemented a `SecurityManager` to limit mod capabilities, it wouldn't help - Java is inherently insecure, and any reasonably-"secure" sandbox implementation (*if one even exists*) would require disabling reflection in mods, which is unacceptable.

As a point of comparison, Forge (*a popular Java mod loader for Minecraft*) doesn't sandbox mods either.
