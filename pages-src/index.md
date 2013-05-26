# Málo.css

an minimalistic CSS framework. **Málo** means **few** in Czech language.

## Credits

Copied, pasted and edited by Mikoláš Štrajt. Heavily based on work of [Vladimir Carrer](http://www.vcarrer.com/). Licensed under MIT license.

Mixed from following libraries:

* [Malo](http://code.google.com/p/malo/) - grid philosophy and code.
* [Better Web Readability Project](http://code.google.com/p/better-web-readability-project/) - styles for comfortable readability. Maybe it tampere some typographic rules, but it's good for reading from screen.

## Grid

Grid is realy simple - it consist of classes `dp100`, `dp50`, `dp33`, `dp25` and `dp20` which serves as columns and class `clearfix` which serves as row. `dp` means div percent.

## Typography

All the typography comes from <abbr title="Better Web Readability Project">BWRP</abbr>, you can find more information about it in interesting article [How we read on web and how can we improve that](http://www.vcarrer.com/2009/05/how-we-read-on-web-and-how-can-we.html).

There are only minor changes from me (thunderbird-style blockquotes, DOS prompt-like code).

## Natural box model

Standard box model as defined by <abbr title="World Wide Web Consorcium">W3C</abbr> is little bit confusing. You set up dimensions of and element and later add some border and padding and... volià - your design is broken.

This is because css property width (or height) is defined *not including* padding and border. Fortunately, there is a possibility to switch to natural box model, which includes border and padding to width (or height) as naive web developer (including mine) would except.

So for column classes (`dp100`, `dp50`, `dp33`, `dp25` and `dp20`) I use box natural box model rather than standard. There is also helper class `natural` which brings natural box model to other elements. This was not included in original malo.css library.

### Live example

<style>
.example { border: 10px dotted red; padding: 20px; width: 200px; }
.box-model-natural {
	-webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
	-moz-box-sizing: border-box;    /* Firefox, other Gecko */
	box-sizing: border-box;         /* Opera/IE 8+ */
}
.box-model-standard {
	/* this is default behaviour */
	-webkit-box-sizing: content-box; /* Safari/Chrome, other WebKit */
	-moz-box-sizing: content-box;    /* Firefox, other Gecko */
	box-sizing: content-box;         /* Opera/IE 8+ */

}
</style>

<div class="example box-model-natural">natural box model</div>
<div class="clearfix"><img src="200px.png"></div>
<div class="example box-model-standard">standard box model</div>

Both red-framed boxes has `border-width : 10px`, `padding : 10px` and `width : 200px`.

----

You can found more information about it on [Paul Irish blog](http://www.paulirish.com/2012/box-sizing-border-box-ftw/).

## More usage info

* [element catalog](catalog.html)
* [class reference](reference.html)

## Real world like examples

This are examples of pages restyled with this framework.

* [markdown syntax page](syntax.html)
* [Lua 5.2 Reference Manual](lua-manual-52.html)

