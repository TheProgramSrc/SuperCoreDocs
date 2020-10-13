---
description: Create custom commands with SuperCoreAPI
---

# Commands

When you use Commands in SuperCoreAPI you don't need to add them to your `plugin.yml` file nor register them, you just need to initialize the class. To define a class as a command you need to extend it to `SpigotCommand` for Spigot, or `BungeeCommand` for BungeeCord.

## Spigot Command Example

```java
package xyz.theprogramsrc.myplugin.commands;

import xyz.theprogramsrc.supercoreapi.spigot.commands.CommandResult;
import xyz.theprogramsrc.supercoreapi.spigot.commands.SpigotCommand;
import xyz.theprogramsrc.supercoreapi.spigot.utils.SpigotConsole;

public MySpigotCommand extends SpigotCommand{

    @Override
    public String getCommand() {
        return "mycommand"; // Define the command to execute
    }

    /*
     * The onPlayerExecute(Player, String[]) method it's executed when a player
     * execute the command. The return object is a CommandResult, the types are:
     * - NO_PERMISSION: Sends a no permission message
     * - NO_ACCESS: Sends a no access message
     * - NOT_SUPPORTED: Sends a message that says the command can only be executed in the console
     * - INVALID_ARGS: Sends a invalid arguments message
     * - COMPLETED: No action is executed
     */
    @Override
    public CommandResult onPlayerExecute(Player player, String[] args) {
        if(!player.hasPermission("example.permission")){
            return CommandResult.NO_PERMISSION; // Send no permission message
        }

        if(!player.hasPermission("example.access")){
            return CommandResult.NO_ACCESS; // Send no access message
        }

        if(!isOnlyForConsole){
            return CommandResult.NOT_SUPPORTED; // Send a not supported message
        }
        return CommandResult.COMPLETED; // No message is sent
    }

    @Override
    public CommandResult onConsoleExecute(SpigotConsole console, String[] args) {
        return CommandResult.NOT_SUPPORTED; // Send a not supported message
    }

}
```

{% hint style="info" %}
The imports for `CommandResult` and `SpigotConsole` are needed to handle the execute methods.
{% endhint %}

## Bungee Command Example

SOON

