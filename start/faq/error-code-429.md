# Error: code 429

If you get an error saying "Error 429" in the server console when trying to start zdiscord or just randomly at any point, this is a warning from the discord API telling you that you are being rate limited for spamming the API too much.\
What would be considered spamming the api too much?

* Overdoing it with webhook logs. having a log for every time money or items are moved and all the conversation going on in chat and anything else that could end up sending over 10 messages/webhooks per second.
* Restarting zdiscord 1000 times in a day
* Someone else on the same host doing the same as discord sometimes will group a whole chunk of a datacenter as if it's one, this also can happen on a shared VPS.

When this happens the only thing you can really do is wait out the timeout time. You should never use discord as a platform to log events for your FiveM server, instead you should use a proper logging system like datadog or store the data yourself in a database and make a way to access and sort it. It's perfectly okay however to use discord for pinging mods about a transaction that's like over $100k or whatever seems really suspicious for your server so you can have a mod look into it quickly before your economy is destroyed.
