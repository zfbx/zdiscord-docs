# isRolePresent

Returns a true/false boolean if a role is present for a role id or array of role-ids

```js
// JAVASCRIPT EXAMPLE
// Source - Discord Role ID
const bool = global.exports.zdiscord.isRolePresent(global.source, "897991948097433681");

// Discord ID - Array of Roles
const bool = global.exports.zdiscord.isRolePresent("142831624868855808", [
    "897991948097433681",
    "897991948097433682"
]);
```

```lua
-- LUA EXAMPLE
-- Source - Discord Role ID
local bool = exports.zdiscord:isRolePresent(source, "897991948097433681");

-- Discord ID - Array of Roles
local bool = exports.zdiscord:isRolePresent("142831624868855808", {
    "897991948097433681",
    "897991948097433682"
});
```
