Thoughts on Removing this
=========================

I remain uncomfortable about the need for a 'base' repository - there are pro's and cons, of course, but I'm not sure I like the _idea_ of it.

Pro's
-----

* Avoid duplication and keep things DRYer.

Con's
-----

* **Fragmenation.** Need to look in more than one place for a thing and it's not always obvious where it's located.
* **Extra maintenance.** A change to a shared resource means testing everything that depends on it.


Reasons for it's existance
--------------------------

For clarity - here's my thought process on why I had this in the first place:

Originally, each FallBack pattern was _meant_ to be self-contained; usable in any project without dependancies.
It remains questionable if this was a fools errand in the first place, but the _idea_ was sound.

Then, it became obvious I would be duplicating some functions, styles and JS etc., so this Base repository was set up to house those things.

However, as time has progessed further, my ideas for the patterns have changed, including the need for them to be self-contained so a Base repository is becoming less useful.

In addition to this, but the developement of StartCSS, it's becoming less likely that _I_ will ever want start a project without that, so StartCSS is _becoming_ my base starting point.
Coupled with the fact that standalone patterns are probably not realistically achievable, it makes more sense to include StartCSS as the base dependancy, rather than the Base repo.



Specifics
---------

The mixins `fallback-rem` and `calc` don't appear to used any longer so I'll be able to get rid of the _mixins.scss_ file.

The functions `color_contrast` (and therefore `color_luminance`) don't appear to be used by any FallBack code.
They seem pretty useful and I'm sure I've used them elsewhere (I think on NPEU stuff), but they don't need to be in here.
Perhaps a mention in the FallBack README would suffice.

The `minus1px` function is used exlusively in media queries in the following repo's:

* Collapse
* Off Canvas
* Over Panel
* Search Form

I'm rethinking these, and they might not be necessary anyway - I need to research / test this.
If a better way can be found, I can get rid of the _functions.scss_ file too.
(Although StartCSS has some functions so I could just put them in there if I moved to using StartCSS as a base).


_base_styles.scss_ isn't really worth it. So little in there and it can be handled differently (e.g. via StartCSS),


That leaves the _icons.scss_ file and the JS files. 

These can probably be put into their own repo's, but that does mean I'll be _increasing_ the number of dependancies, so I'll need to think carefully about that.

Possibly rename this to 'shared'?

I want to make StartCSS completely independant. This seems doable, and having a 'shared' repo would be something other patterns can include.