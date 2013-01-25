Hello, I'm Ingrid 2.0!
==================

Ingrid is a fluid CSS layout system, whose main goal is to reduce the use of classes on individual units.

Ingrid is a bit less obtrusive and bit more fun to reflow for responsive layouts.

Ingrid is also meant to be an extendable system, easy to customize to your own needs.

Check out Ingrid in use at <http://codepen.io/robertpiira/pen/kofpu>.

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

  1. `.container`
  2. `.divide4` (or `.divide3` if there are 3 units).
  
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

The difference is that we add the class name `.span2` on the last unit (making it span the width of two units).

The `.span-x` class-name can be used to combine units in any context (`.divide2`, `.divide3`, `.divide4`, etc.).

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

A container with the class of `.divide5` would contain five units. There is really nothing that says how these units should be aligned or what widths they should have. 

I believe this model works pretty neatly for reflowing content in a responsive layout.


Details
-------

Ingrid uses `display: inline-block` and `border-box` box model for laying out the individual units.

Border-box makes it easy to set borders and padding (for gutters) directly on units. (More on border-box <http://paulirish.com/2012/box-sizing-border-box-ftw/>.)

`inline-block` is just nice to work with and easy to reflow for different layouts.

The one negative with `inline-block` is the additional white-space that gets added between units. To remove the white-space evenly across different browsers can seem bit hacky. So Ingrid tries her best to get rid of the white-space. But the results are not cross-browser pixel-perfect. But really… Ingrid just doesn't care about pixel-perfection in that sense anymore. (More on `display: inline-block` at <http://robertnyman.com/2010/02/24/css-display-inline-block-why-it-rocks-and-why-it-sucks/>.)

Some nicer details with Ingrid is that we don't need to repeat class names like `.first`, `.last`, `.grid-6`, `.size1of5`, etc. on each unit.

You could also skip the whole `.divde4` / `span2` class names that Ingrid provides and make your own semantic class names for width hooks instead.

The container doesn't have to be called `.container`, change all these class-names to anything semantic or unsemantic you like!


Responsive?
-----------

Ingrid 2.0 includes two breakpoints and the css is structured in a mobile first approach.

It's up to you to see what breakpoints make sense in your project. The breakpoints that are included with Ingrid can be modified so that they match your content.


Browser support
---------------

Ingrid works just fine with IE8 + and all modern browsers. IE7 might need some extra help on your part for not supporting `border-box` model… IE6 is not supported at all.


License
-------

All code licensed under CC0: <http://creativecommons.org/publicdomain/zero/1.0/>

