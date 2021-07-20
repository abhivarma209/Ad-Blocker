Ad-Block
===========

Ad-Block is an ad-blocking extension for Chrome, the main goals are simplicity of implementation and performance.
My thought process was something like this:

1. The last time I blocked ads, it made things slow. I'd like to block ads at native speed.
1. What's the least amount of code necessary to expose the URL-blocking functionality of webRequest?



Instructions
------------
To install, clone the repository locally, open `chrome://extensions/`, check the "Developer mode" box, and use "load unpacked extension" on the directory containing your clone. A better installation mechanism may be available once the extension is more stable.

Once installed, an icon should appear next to your Omnibox. Red means blocking is enabled, blue means disabled; click the icon to toggle. Right-click and go to "options" to customize the URI filters it uses.
Details
-------
This extension can only block external requests (images, Flash, XHR) via the aforementioned URL patterns. It won't remove ad content that is part of the actual text of the HTML page. 

If you're like me and don't really understand how Chrome extensions work, here's the directed graph of this extension. `manifest.json` gives the extension an icon and a set of scripts. Chrome automatically attaches those scripts to a "generated background page" in which they execute; this is what contains the global extension state. 

TODO
----

* The options page needs better CSS (and more UX attention in general)
* It should be possible to merge two sets of filters, e.g., custom filters and a new set of default filters


