# tedit-2

Remake of the classic Tedit using modern web platform features

## Service Workers

When Tedit was originally made, service workers weren't a thing and I simulated them by implementing a full HTTP server on top of the chrome packaged app TCP primitive.  Now I can do much better with service workers and it will even work in websites!

## Filesystem Access

In old Tedit, filesystem access was only possible in chrome packaged apps.  Now it's part of the web platform as `window.showOpenFilePicker()`

- https://wicg.github.io/file-system-access/

## Async/Await

In old tedit, I (ab)used generator functions to block on I/O.  The regenerator code transform was used for runtimes that didn't yet support generator functions.

But the language has long since added native support for proper async/await with good support.

## Sandbox and Wasm

Now that wasm is a thing and there are even tiny JS engine implementations that can be run in wasm such as https://bellard.org/quickjs/, a much better sandbox can be used for modules in the tedit build system.

## Installable PWA

Chrome Packaged apps are deprecated, but good news, PWA apps are gaining support and can be used to make the web version installable.

## CORS enabled smart https

This particular blocker has never been resolved.  The most popular git repository (github) still refuses to add CORS headers to their https git endpoints.  This means it is still not possible to clone directly from github to a web based editor.

There is still the propritary github API that tedit supported, but it's changed enough that the old code is completely broken.  It could be updated and is currently in use in popular projects like github1s and gitpod.

## New lit protocol.

The luvit.io ecosystem has been using a new websocket based git protocol for years in production.  It can be added to tedit as a way to live-mount git repos using an open protocol.  It's unlikely github will add support for such a protocol, but a custom public repository can be hosted for this.

Also this protocol could be adapted for use over P2P networks using webrtc data channel to share repositories with peers.  A public server can facilitate the P2P connections and optionally act as an always on peer for paying customers to help fund the open server.
