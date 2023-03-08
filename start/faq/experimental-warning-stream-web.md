# Experimental Warning (stream/web)

If you see a warning saying:

```
(node:4560) ExperimentalWarning: stream/web is an experiemental feature. This feature could change at any time..
```

This is nothing to worry about. The warning is caused by the use of undici, a package used by discord.js. Because FiveM is using an older version of nodejs this warning shows for some reason sometimes but in newer versions this feature is no longer experimental. If FiveM updates their version of node again this error will go away but until that time there's nothing I can do about this error.

if it bothers you to no end, you can try adding `--no-warning` to your launch args for FiveM to make it stop warning. You might miss other important warnings if you do this however so it's not the best idea.
