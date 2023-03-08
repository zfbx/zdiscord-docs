# log

{% hint style="info" %}
Do note that you should only use this sort of event sparingly to alert your in game staff of things of importantance or for passing an announcement from fivem to discord. using this event to log many things that spam like every monetary transaction or item moment (with any discord webhook resource) will cause you to hit discord's api limit and cause your bot to stop working for some time.
{% endhint %}

send a message to a configured Log webhook

```js
// JAVASCRIPT EXAMPLE
// event, message, pingRole, color (optional)
global.exports.zdiscord.log("modlog", "UserA Banned UserB for Reason", true, "#FF0000");

```

```lua
-- LUA EXAMPLE
-- event, message, pingRole, color (optional)
exports.zdiscord:log("modlog", "UserA Banned UserB for Reason", true, "#FF0000");
```
