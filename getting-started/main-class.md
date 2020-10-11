---
description: The main class using SuperCoreAPI
---

# Main Class

### Spigot

To create your main class in spigot you extend your class to `SpigotPlugin` and then add the methods `onPluginLoad()` `onPluginEnable()` `onPluginDisable()`, those are like the methods from the SpigotAPI but they're executed after initializing the features from SuperCoreAPI.

### BungeeCord

In Bungee plugins, it's the same way that Spigot but you need to extend your class to `BungeePlugin` instead of `SpigotPlugin`

### Example:

```java
package xyz.theprogramsrc.myplugin;

import xyz.theprogramsrc.supercoreapi.spigot.SpigotPlugin;

public MySpigotPlugin extends SpigotPlugin{

    @Override
    public void onPluginLoad(){
        // On load stuff
    }
    
    @Override
    public void onPluginEnable(){
        // On enable stuff
    }
    
    @Override
    public void onPluginDisable(){
        // On disable stuff
    }
}
```

