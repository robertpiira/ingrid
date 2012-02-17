Hello, I'm Ingrid!
==================

Ingrid is a fluid CSS layout system, whose main goal is to reduce the use of classes on individual units.

Ingrid is a bit less obtrusive and bit more fun to reflow for responsive layouts.

Ingrid is also meant to be an extendable system, easy to customize to your own needs.

Ingrid loves cats :o)

Check out a quick and dirty demo-page at <http://piira.se/projects/ingrid>.

Introduction
------------

So, The basic idea…

    +-------------------[c]-------------------+
    | +-------+ +-------+ +-------+ +-------+ |
    | |       | |       | |       | |       | |
    | |  [u]  | |  [u]  | |  [u]  | |  [u]  | |
    | |       | |       | |       | |       | |
    | +-------+ +-------+ +-------+ +-------+ |
    +-----------------------------------------+

The container [c] needs two class-names:

  1. `.ingrid`
  2. `.in-fourths` (or `.in-thirds` if there are 3 units).
  
Each unit [u] within the container [c] needs the class-name:

  1. `.unit`
  
___________________________________________


To tweak the layout we can combine units like this.

    +-------------------[c]-------------------+
    | +-------+ +-------+ +-----------------+ |
    | |       | |       | |                 | |
    | |  [u]  | |  [u]  | |       [u]       | |
    | |       | |       | |                 | |
    | +-------+ +-------+ +-----------------+ |
    +-----------------------------------------+

In this case the container [c] and units [u] have the same class-names as in the first example.

The difference is that we add the class name `.span-two` on the last unit (making it span the width of two units).

The `.span-x` class-name can be used to combine units in any context (`.in-halves`, `.in-thirds`, `.in-fourths`, etc.).

___________________________________________


Units [f] that need to span the whole width of the container use the class _.field-unit_.

    +-------------------[c]-------------------+
    | +-------------------------------------+ |
    | |                 [f]                 | |
    | +-------------------------------------+ |
    | +-------+ +-------+ +-------+ +-------+ |
    | |       | |       | |       | |       | |
    | |  [u]  | |  [u]  | |  [u]  | |  [u]  | |
    | |       | |       | |       | |       | |
    | +-------+ +-------+ +-------+ +-------+ |
    +-----------------------------------------+


Gutters
-------

The gutters are made by first giving the container [c] negative left and right margins. 

Each unit [u] has a padding on each side that is equal to the containers [c] negative margins.

The gutters are set to a certain width in `ingrid.css`. But these measures can easily be overridden/tweaked to your own preference via your own classes that extend the container or directly in the ingrid CSS file.

The padding for the gutters work with `em`, `%` or pixel units (thanks to the CSS `border-box` box model).


Mental model
------------

With Ingrid we are thinking in form of units as blocks of content/modules that can be stacked horizontally or vertically.

A container with the class of `.in-fifths` would contain five units. There is really nothing that says how these units should be aligned or what widths they should have. 

I believe this model works pretty neatly for reflowing content in a responsive layout.


Details
-------

Ingrid uses `display: inline-block` and `border-box` box model for laying out the individual units.

Border-box makes it easy to set borders and padding (for gutters) directly on units. (More on border-box <http://paulirish.com/2012/box-sizing-border-box-ftw/>.)

`inline-block` is just nice to work with and easy to reflow for different layouts.

The one negative with `inline-block` is the additional white-space that gets added between units. To remove the white-space evenly across different browsers can seem bit hacky. So Ingrid tries her best to get rid of the white-space. But the results are not cross-browser pixel-perfect. But really… Ingrid just doesn't care about pixel-perfection in that sense anymore. (More on `display: inline-block` at <http://robertnyman.com/2010/02/24/css-display-inline-block-why-it-rocks-and-why-it-sucks/>.)

Some nicer details with Ingrid is that we don't need to repeat class names like `.first`, `.last`, `.grid-6`, `.size1of5`, etc. on each unit.

You could also skip the whole `.in-fourths` / `in-fifths` class names that Ingrid provides and make your own semantic class names for width hooks instead.

The container doesn't have to be called `.ingrid`, change all these class-names to anything semantic or unsemantic you like!


Responsive?
-----------

Well, Ingrid is fluid, but there are no built in media query breakpoints. The Ingrid demo-page has a couple of breakpoints just do demonstrate how this could be done.

It's up to you to see what breakpoints make sense in your project and the way you want to structure your CSS / markup. Whether you work with desktop down or mobile first approach, Ingrid should work for both or a mix of these alternatives.


Compability
-----------

Ingrid works just fine with IE8 + and all modern browsers. IE7 might need some extra help on your part for not supporting `border-box` model… IE6 is not supported at all.


Todo
----

* Create a proper demo-page
* Work on the grid nomenclature
* Proper browser testing


License
-------

All code licensed under CC0: <http://creativecommons.org/publicdomain/zero/1.0/>

