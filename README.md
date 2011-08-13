# jQuery fullscreen event plugin, version 0.2.0

This plugin provides a technique for detecting if a browser is in fullscreen mode.

# Usage

Add `jQuery` and `jquery.fullscreen.js` to your HTML document. No explicit initialization is required, this plugin handles that automatically. Afterwards, bind a fullscreen event to the `window` object. Example:

    $(window).bind("fullscreen-on", function(e) {
        console.log("we're on fullscreen now");
    });

The following events are provided:

* `fullscreen-toggle` is triggered whenever the fullscreen state changes. The event handling function takes the following form:
        
        $(window).bind("fullscreen-toggle", function(e, state) {
            ...
        });

    where `state` represents the fullscreen state as a `boolean` value;

* `fullscreen-on` is triggered when the browser enters fullscreen;
* `fullscreen-off` is triggered when the browser exits fullscreen.
* `fullscreen-key` is triggered when detecting pressing the shortcut key for toggling the browser's fullscreen state (working only on Chrome and Firefox). The event handling function takes the following form:

        $(window).bind("fullscreen-key", function(e, shortcut, longform) {
            ...
        });

    where `shortcut` represents the pressed keys as a `string` value, and `longform` represents its longform textual representation;

If you need to check the current fullscreen state, grab the `fullscreen-state` data property from the `window` object, as follows:

    var isFullScreen = $(window).data('fullscreen-state');

If you need to check the shortcut key and corresponding longform, grab the `fullscreen-key` data property from the `window` object, as follows:

    var data = $(window).data('fullscreen-keys'); // returns an object in the form of { shortcut: "...", longform: "..." }

The `example.html` document details examples for all events.

# Caveats

* There is no cross-browser way to programmatically trigger the fullscreen state.
* This has only been tested in Safari (OS X), Google Chrome, Opera, and Firefox. Support for more browsers is coming soon.

# License

(The MIT License)

Copyright © 2011 Rui Lopes

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the ‘Software’), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED ‘AS IS’, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
