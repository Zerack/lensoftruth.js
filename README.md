lensoftruth.js
==============

Lens of Truth is a jQuery plugin designed to assist javascript debugging when using HTML data-* attributes. By default, jQuery internalizes data attributes when set, meaning that they don't actually show up in the DOM for debugging. While some mature developer tools (and extensions) can make these properties visible, I wanted a solution that would work in any browser without the need for detailed development extensions.

Thus, I created lensoftruth.js to intercept calls to $.data(), and update the DOM appropriately if the call was intended to set a value. The plugin does not actually alter any of the workings of $.data() - all subsequent access to any set values will still use the internal jQuery cache. The only effect is that when an attribute is set (for example $.data('myAttribute')), it results in an attribute like data-lot-myAttribute being added to the node(s) in question.

lensoftruth.js supports all of the data() function parameters that jQuery supports, and is super lightweight. I have purposefully not provided a minified version of the script, since this is not designed to be used in production.

Usage
------
Include lensoftruth.js after your preferred version of jQuery.

        <script src="lensoftruth.js"></script>
That's it! Now just use $.data() to see it in action!