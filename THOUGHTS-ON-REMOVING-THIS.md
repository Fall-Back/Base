Thoughts on Removing this
=========================

I remain uncomfortable about the need for a 'base' repository - there are pro's and cons, of course, but I'm not sure i like the _idea_ of it.

Pro's
-----

* Avoid duplication and keep things DRYer.

Con's
-----

* **Fragmenation.** Need to look in more than one place for a thing and it's not always obvious where it's located.
* **Extra maintenance.** A change to a shared resource means testing everything that depends on it.


Specifics
---------

The mixins `fallback-rem` and `calc` don't appear to used any longer so I'll be able to get rid of the _mixins.scss_ file.

The functions `color_contrast` (and therefore `color_luminance`) don't appear to be used by any FallBack code.
They seem pretty useful and I'm sure I've used them elsewhere, but they don't need to be in here.
Perhaps a mention in the FallBack README would suffice.

The `minus1px` function is used exlusively in media queries in the following repo's:

* Collapse
* Off Canvas
* Over Panel
* Search Form

I'm rethinking these, and they might not be necessary anyway - I need to research / test this.
If a better way can be found, I can get rid of the _functions.scss_ file too.


_base_styles.scss_ isn't really worth it. So little in there and it can be handled differently (e.g. via StartCSS),


That leaves the _icons.scss_ file and the JS files. 

These can probably be put into their own repo's, but that does mean I'll ne _increasing_ the number of dependancies, so I'll need to think carefully about that.