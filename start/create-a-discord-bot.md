---
description: basics to create a discord bot application on discord.com
---

# Create a Discord Bot

At the heart of zdiscord is a discord api application and it's required to have zdiscord function. I'm going to walk you through the basic of creating one here. Along the way I will point out various things you will want to make note of for later.

1. Open the [Discord developer portal](https://discord.com/developers/applications) and log into your account.
2. Click the "New Application" button.
3. In the popup, enter a name for the application, read and agree to the terms then click the "Create" button.

{% hint style="info" %}
On the "General Information" page, after pressing "Create", you will see "APPLICATION ID", you'll want to copy this id and save it for later.
{% endhint %}

4. Click "Bot" from, the left menu, then click "Add Bot" and "Yes, do it!" when it pops up. _You may be required to enter a 2FA Code at this step._
5. _On this page you can edit the icon for your new bot and the name that it will have when it replies in your server._

{% hint style="info" %}
On the "Bot" page you will see "TOKEN" and a button to "Copy" or "View" it. Copy the token and paste it into a notepad or something for your record, you will need it later in setup. **DO NOT SHARE THIS.** This token is essentially the password for your bot and you don't want anyone to get their hands on it
{% endhint %}

6. under the "Privileged Gateway Intents" category, toggle on the 3 intents and click "Save Changes" like the image below

<figure><img src="../.gitbook/assets/chrome_em37oBxaRN.png" alt=""><figcaption></figcaption></figure>

7. Invite your new bot to your discord server. To do this, take the application id I had you save earlier and replace where it says "APPLICATION-ID" with that id in the link below. [https://discord.com/api/oauth2/authorize?client\_id=APPLICATION-ID\&permissions=8\&scope=bot%20applications.commands](https://discord.com/api/oauth2/authorize?client\_id=APPLICATION-ID\&permissions=8\&scope=bot%20applications.commands)\
   Going to this link (after replacing the id) with give you a window to invite the bot you just created to your discord server. Select the server you want to invite the bot to from the dropdown, continue and Authorize.

{% hint style="info" %}
if you get a message saying something like "Value "APPLICATION-ID" is not snowflake.", that would mean you didn't replace the id properly.
{% endhint %}

8.  Finally the token I had you copy earlier that is super secret, you'll want to paste that into your zdiscord config.js in `zconfig.BotToken` it should look something like:\


    ```javascript
    zconfig.BotToken = "MNz4TAMwMTI1MjAwMTkygzODMA.GSF4S0.Lx7fLN2gePLARbEPS_xIQmQuij2xpl3BgD4roo";
    ```

{% hint style="info" %}
**Do not share this token with other bots.** Doing so will break slash commands. every bot needs it's own bot application and token to function properly (this includes txadmin)
{% endhint %}
