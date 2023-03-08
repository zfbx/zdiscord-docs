---
description: Steps required for a functioning zdiscord
---

# Setup

### Requirements

* [cfx-server-data](https://github.com/citizenfx/cfx-server-data) in your resources (yarn (`[system]/[builders]/yarn/`) at least)
* Optional: [screenshot-basic](https://github.com/citizenfx/screenshot-basic) if you want the /screenshot command to work

#### Steps

1. Get a bot application if you haven't already [Guide Here](https://discordjs.guide/preparations/setting-up-a-bot-application.html)
2. **IMPORTANT: Enable ALL intents** on the **bot** page of step 1 ([Picture example](https://zfbx.github.io/zdiscord/images/intents.png)) \*If you don't do this.. your bot will NOT work.
3. Add the bot to your server - To do this copy the following link and replace `YOUR-BOT-ID` with your bots application id then follow the invite process to your discord from the link\
   **https://discord.com/api/oauth2/authorize?client\_id=`YOUR-BOT-ID`\&permissions=8\&scope=bot%20applications.commands**\
   **NOTE: If the bot is already in your server you might need to run the link above again anyways to make sure it can get the needed slash command scope (unrelated to permissions)**
4. Copy the resource into your fiveM resources directory and make sure the folder is named `zdiscord` (not zdiscord-djs, zdiscord-main or anything else)
5. Double check that you have the [cfx-server-data](https://github.com/citizenfx/cfx-server-data) resource in your resources (or yarn `[system]/[builders]/yarn/` at the very least)
6.  In your `server.cfg` do the following:\
    6a. Add `ensure zdiscord` (after qb-core and/or [convars](https://zfbx.github.io/zdiscord/convars) you may have)\
    6b. Add the following anywhere in your .cfg:

    ```
    add_ace resource.zdiscord command allow
    add_ace group.zdiscordstaff zdiscord.staffchat allow
    ```

    **NOTE:** _Make sure you always load your heavy assets (cars, maps, clothing) **before** your scripts. zdiscord can stop working if enough heavy assets are loaded after and cause the server to pause (or hang) for more than 10 seconds_
7. Adjust the `config.js` variables to how you'd like them. (Optionally use [Convars](https://zfbx.github.io/zdiscord/convars))
8. **If you missed step 2, go back and do it.. or else IT WONT WORK!**
9. If you run into any errors check out the [FAQ](https://zfbx.github.io/zdiscord/faq) where a lot of common problems are listed and answered
