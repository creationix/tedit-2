# tedit-2

Remake of the classic Tedit using modern web platform features

## Service Workers

When Tedit was originally made, service workers weren't a thing and I simulated them by implementing a full HTTP server on top of the chrome packaged app TCP primitive.  Now I can do much better with service workers and it will even work in websites!

## Filesystem Access

In old Tedit, filesystem access was only possile in chrome packaged apps.  Now it's part of the web platform as `window.showOpenFilePicker()`

- https://wicg.github.io/file-system-access/

## Async/Await

In old tedit, I (ab)used generator functions to block on I/O.  The regenerator code transform was used for runtimes that didn't yet support generator functions.

But the language has long since added native support for proper async/await with good support.

## Sandbox and Wasm

Now that wasm is a thing and there are even tiny JS engine implementations that can be run in wasm such as https://bellard.org/quickjs/, a much better sandbox can be used for modules in the tedit build system.

## Installable PWA

Chrome Packaged apps are deprecated, but good news, PWA apps are gaining support and can be used to make the web version installable.
