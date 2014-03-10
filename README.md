Edenspiekermann CSS Abstractions
============

Current version: `1.2.1`

## Installation

Core CSS abstractions for beginning any project. Use Bower to install using either:

`$ bower install espi-modules --save`

**or:**

Update your `bower.json` dependencies with `"espi-modules": "1.1.0"` and run `$ bower update`

Then `@import` `espi-modules/espi-modules` from wherever your Bower components live, at the top of your `.sass` structure.

## Configuration

The modules included should be fairly self explanatory, and can each be toggled by setting flags to `false` **above** your `@import` to hide certain modules.

Default flags are currently set as follows:

    $include__defaults: true
    $include__forms: true
    $include__block: true
    $include__container: true
    $include__flag: true
    $include__grid: true
    $include__island: true
    $include__media: true
    $include__nav: true
    $include__vcenter: true

Each partial in `/partials` also contains specific variables that can overwritten and customised for your needs (take a look yourself)

## Key Features

### Media Queries

A mixin library for media queries is included in `/vendor/sass-ie` as outlined in [this article](http://jakearchibald.github.io/sass-ie/) - allowing you to easily create a fallback stylesheet for IE8. The mixins available for media queries are as follows, and you should pass unitless pixel values which are then [converted into `ems`](http://blog.cloudfour.com/the-ems-have-it-proportional-media-queries-ftw/).

    +mq-min($width)
    +mq-max($width) 
    +mq-min-max($min-width, $max-width)
    +mq-min-h($height)
    +mq-max-h($height)
    +mq-min-w-min-h($width, $height)
    +mq-min-w-max-h($width, $height)

This builds on the stylesheet pattern in the [Middleman Startup](https://github.com/mattberridge/Middleman-Startup) framework.

### Unit Conversion

Includes Jakob-e's [Unit Conversion library](https://github.com/jakob-e/unitconversion/blob/master/UnitConversion.scss) which offers a stupid amount of Sass functions you may or may not find useful.

### Other Modules

Abstractions like Grid, Nav, Media Object, Flag, Island etc. are all available to do certain jobs and have a variety of modifiers. I haven't got time to document them all right now so if you need clarification, just ask :)

## Further Development

When developing a feature or module in your project, consider whether abstracting it for re-use in future will be helpful. Then either write the code in the Bower package and import it, or write the code in the project and abstract it later.

If you are adding modules to the project please use the **BEM class-naming syntax** and try to include **structure only**. Please keep appearance / aesthetics out of the Bower package as much as possible.
