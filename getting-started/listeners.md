---
description: How to work with listeners in SuperCoreAPI
---

# Listeners

In SuperCoreAPI you don't need to register listeners. You just need to initialize the class containing the listeners. To define a class as listener you need to extend it to `SpigotModule` in spigot, or `BungeeModule` in BungeeCord.

## Auto-Register Listeners

```java
package xyz.theprogramsrc.myplugin.listeners;

import xyz.theprogramsrc.supercoreapi.spigot.SpigotModule;

public MySpigotListener extends SpigotModule{

    // Some Listeners Stuff

}
```

{% hint style="info" %}
If you want to manually register the listener you need to add the constructor to the class and add the super argument boolean as false.
{% endhint %}

## Disabling the Auto-Register

If for any reason you don't want to auto-register the listener you can disable the auto-register listener. Take a look into the example:

```java
package xyz.theprogramsrc.myplugin.listeners;

import xyz.theprogramsrc.supercoreapi.spigot.SpigotModule;

public MySpigotListener extends SpigotModule{

    public MySpigotListener(){
        super(false);  // False to disable the auto-register
    }

}
```

The Spigot and Bungee Modules comes with a function to replace the constructor, the method it's executed after registering the listener \(If you disabled the auto-register it will be executed anyway\)

The method executed is called `onLoad()`, you can take a look into the example to check the usage.

```java
package xyz.theprogramsrc.myplugin.listeners;

import xyz.theprogramsrc.supercoreapi.spigot.SpigotModule;

public MySpigotListener extends SpigotModule{

    @Override
    public void onLoad(){
        // Some awesome code
    }

}
```

To register the module just initialize the class like this: `new MyListener()`

