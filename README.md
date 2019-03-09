This creates separators between items with some configurations. It takes elements with display:none into consideration to ignore them and don't add extra separators.

### Making An Instance

```
horizontal_separator = Separator.factory(
{
    mode: "horizontal",
    class: "big red"
})

horizontal_separator.separate("some_container")

vertical_separator = Separator.factory(
{
    mode: "vertical",
    class: "shiny blue"
})

vertical_separator.separate("some_other_container")
```

### Usage

The basic workflow is creating one or several configured Separator instances to use them many times.

The typical structure of a container could be:

```
<div id='my_container' class='flex_row'>
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

Then to create the separators:

```
horizontal_separator.separate("my_container")
```

It could look like:

![](https://i.imgur.com/fAkem2L.jpg)

This can be ran any time, but it won't run automatically, if the content changes you must run the separate function again.

## Why?

A lot of this may be done with CSS, but from personal experience I've found that route lacking for some cases, so I created my own separator mechanism. It might or might not be useful to you.

### Methods

>instance.separate(id or element, options:optional)

It removes any previous separators and rebuilds them.
It takes items with display:none into account to not add extra separators.
If an options object is received, options included there will override provided options from instantiation, but only for that execution.

>instance.remove_separators(id or element)

Removes all separators.

### Options

>mode

Either horizontal or vertical.

>html

The html inside the separators. 
If nothing is defined it uses a default html stucture.
The default could be enough for some cases.

>class

The class or classes to add to the separator element.

>height

The height of the separator item.
Only applicable for horizontal mode.

>width

The width of the separator item.
Only applicable for vertical mode.

>margin_top

The margin-top of the separator item.
Only applicable for vertical mode.

>margin_bottom

The margin-bottom of the separator item.
Only applicable for vertical mode.

>margin_left

The margin-left of the separator item.
Only applicable for horizontal mode.

>margin_right

The margin-right of the separator item.
Only applicable for horizontal mode.

>font_size

The font-size of the separator item.

>line_height

The line-height of the separator item.