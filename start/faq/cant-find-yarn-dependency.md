# Can't Find Yarn Dependency

This resource requires the cfx yarn resource from [cfx-server-data](https://github.com/citizenfx/cfx-server-data) under `resources/[system]/[builders]/yarn` so to fix this, do one of the following:

* copy the entire cfx-server-data folder into your resources folder
* copy just the `yarn` folder into your resources.

&#x20;Once you do that, restart zdiscord and it will automatically start yarn and build the dependencies it needs.

{% hint style="info" %}
If you want to use the `/screenshot` command, screenshot-basic will require the webpack resource frrom the same `[builders]` directory. So if you use the second option it might be benefitial to copy the whole `[builders]` folder to your resources instead of just yarn
{% endhint %}
