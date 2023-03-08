---
description: Frequently Asked Questions
---

# FAQ

###

### "ENABLE INTENTS" Error

zdiscord **needs** `Presence Intent` and `Server Members Intent` from the discord bot [settings](https://discord.com/developers/applications) to be enabled for basic functionality. Without these the bot is unable to check if a user is in your discord server or if they have the required roles to join the server if using the whitelist feature.

Under the "Bot" section of the discord settings towards the bottom you'll see 2 toggles under the "Privileged Gateway Intents" section, They both need to be enabled like show below:&#x20;

### Can't find yarn dependency

This resource requires FiveM's yarn module from [cfx-server-data](https://github.com/citizenfx/cfx-server-data) under `(resources/[system]/[builders]/yarn)` so either add those resources to your resource folder or just put the yarn one in your resources and zdiscord will enable it for itself so you don't need to include it in your cfg.

**Note:** If you want to use the /screenshot command which uses [screenshot-basic](https://github.com/citizenfx/screenshot-basic) you will also need the webpack resource also under `[builders]`. So consider having that one ready too if you end up just copying the single resource.

### QBCore commands not showing

For QBCore support you either have to `ensure qb-core` before this resource or have qb-core as a dependency in the fxmanifest.lua which will essentially start qb-core automatically before it but the former suggestion is more recommended since some dependency requirements can act up.

### QBCore commands aren't loading

If you're using an older version of QBCore that uses the old `QBCore:GetObject` event you will have to update the server.js replacing lines \~20-23 which look like:

```js
try {
    var QBCore = global.exports["qb-core"].GetCoreObject();
    if (QBCore) zlog.info("QBCore found! Supported QB commands will be loaded.");
} catch { QBCore = false; }
```

With this:

```js
var QBCore = false;
TriggerEvent("QBCore:GetObject", (obj) => { QBCore = obj; });
if (QBCore) zlog.info("QBCore found! Supported QB commands will be loaded.");
```

**Note:** Not all commands are backwards compatible with the previous version of QBCore as it would be very hard to support many versions of backwards compatibility so I recommend updating to a more recent version of QBCore :) _(Plus if you're using qbus it's a leak and you shouldn't be anyways)_

### Bot status message updates slow

By default the bot status updates every 30 seconds to prevent abusing the discord API, you can lower this to probably 10 seconds at the lowest without problems by changing the last line in `/events/ready.js` where it's `30000` to `10000` (it's in milliseconds)

### Experimental Warning

You may see a warning like:

```
(node:4560) ExperimentalWarning: stream/web is an experiemental feature. This feature could change at any time..
```

This is fine, don't worry about it. The warning is caused by the use of undici (an addon used by discord.js) for using a newer nodejs feature that is now released on version 17+ of node but fivem as of writting this is using version 16 so there's not much I can do, it shouldn't cause any issues the way it's being used. if it bothers you a ton you could try adding `--no-warning` to your launch args for FiveM but you might miss other important warnings.

### Buffer Deprecation Warning

**This was patched in version 7.0.0 of zdiscord and FiveM artifact 4980+. Update to these or later to make this go away.**

You may see a warning like:

```
[DEP0005] DeprecationWarning: Buffer() is deprecated due to security and usability issues. Please use the Buffer.alloc(), Buffer.allocUnsafe(), or Buffer.from() methods instead.
```

This is fine.. it's just a warning that future versions may drop support for it. I don't see FiveM updating node again for quite some time so it's nothing to concern yourself with at the moment. This issue comes from a sub-dependency (node-fetch and whatwg) thinking FiveM is a browser so falling back to use `Buffer()`. I hope future updates of those resources will fix it, currently there's nothing I can do about it without forking entire collections of node modules and changing them. And I don't want the responsibility of keeping them updated especially when they're fairly active repositories.

### Could not find dependency /server:4890

When trying to start zdiscord you get an error that says `Could not find dependency /server:4890 for resource zdiscord`. This means you aren't running [FiveM artifacts](https://runtime.fivem.net/artifacts/fivem/build\_server\_windows/master/) version 4890 or later. updating to a version number higher than 4890 will fix this error and allow the resource to start.

### New chat messages / announcements aren't popping up when received

cfx chat by default has modes you can toggle between with a keybind (default: L) and if you change it to "WHEN ACTIVE" it'll show when new messages arrive

#### How to use custom chat

You really shouldn't use a custom chat but rather theme the default but IF you did.. you can change the functionality of the chat in zdiscord by modifying the function `chatMessage` in `utils.js` as all messages in game are forwarded through there
