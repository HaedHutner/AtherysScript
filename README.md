# AtherysScript

AtherysScript is a plugin for the SpongeAPI, developed for use on the
A'therys Horizons minecraft server.

It is designed with extensibility in mind, with the ability to both add
extensions to the API implementation present in the plugin by default,
and provide own implementations in the form of other languages.

The primary purpose of a script on a server is to provide simple
functionality, which can be modified easily thanks to the more
accessible language it is written in.

The default implementation of AtherysScript is JavaScript, using the
Nashorn script engine.

### NOTE:

AtherysScript is **NOT** meant to be a replacement or alternative to
Sponge plugins. If you want to create highly complex functionality in
your server, please learn how to make a Sponge plugin. For more
information, see here:
[Creating a Plugin](https://docs.spongepowered.org/stable/en/plugin/index.html).

## How does it work?

Documentation at present is sparse, and this is being worked on.

When you add this plugin to your mods folder, on first start up it will
look for a folder in the root directory of your minecraft server
( on the same level as your minecraft server jar ).

The exact name of this folder is configurable and can be found in the
plugin config. If the plugin does not find this folder, it will create it.
Once it is create it, the ScriptService will automatically look through it
and load all files present in the scripts folder as a script file.
Please ensure there are **only** script files in the folder, else you
may get unexpected errors in the console.

Upon discovering a script file, the ScriptServer will register it as
a script, and run it.

An example script looks a little somethign like this:

```javascript
    onScriptStart( function(event) {
        info("This script has started");
    });

    onScriptStop( function(event) {
        info("This script has stopped");
    });
```

Documentation on event hooks and all available functions to ease the
creation of a script can be found on the wiki ( which is currently a
WIP ).