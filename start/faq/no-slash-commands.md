---
description: Don't see any slash commands in discord when you type / ?
---

# No Slash Commands

There's a handful of reasons that you could not be seeing slash commands when zdiscord is running. including but not limited to:

* First off, check your server console for errors that might of stopped zdiscord from launching completely.
* Make sure that `zconfig.Enabled` in your config.js is set to true as it wont load the bot commands if the bot isn't enabled.
* Make sure that your `zconfig.ServerId` in the config.js is the server id for the discord you're trying to use the slash command in as it will only load them for that server.
* Does the role trying to access the slash commands have the slash commands permission in discord roles?
* Did you invite the bot to your server with the invite link provided? (which includes `&scope=bot%20applications.commands` on the end) You can re-invite the bot with the proper link without kicking it from the server and it'll get the permissions it's supposed to have without having to reconfigure it's roles.
* Finally: In your discord user settings (bottom left gear icon) > Text & Images > Text Box do you have "Use slash commands.." enabled?
