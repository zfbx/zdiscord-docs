# Buffer Deprecation Warning

If you see a warning like:

```
[DEP0005] DeprecationWarning: Buffer() is deprecated due to security and usability issues. Please use the Buffer.alloc(), Buffer.allocUnsafe(), or Buffer.from() methods instead.
```

This is fine and nothing to worry about. It's just a warning that future versions may drop support for it. I don't see FiveM updating node again for quite some time so it's nothing to concern yourself with at the moment.

This issue comes from a sub-dependency (node-fetch and whatwg) thinking FiveM is a browser so falling back to use `Buffer()`. I hope future updates of those resources will fix it, currently there's nothing I can do about it without forking entire collections of node modules and changing them. And I don't want the responsibility of keeping them updated especially when they're fairly active repositories.
