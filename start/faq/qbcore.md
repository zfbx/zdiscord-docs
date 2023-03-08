# QBCore

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
