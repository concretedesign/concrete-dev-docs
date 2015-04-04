## CSS

Use Sass.

### Components

Your sass should live in a component folder along with your markup and logic.  Global styles can live in a central area.

### Class Naming Conventions

As borrowed from The Sass Way: http://thesassway.com/advanced/modular-css-naming-conventions

Objects (or components) are typically nouns. They normally have their own file, and take the form of:

```css
.noun {}              // examples: .button, .menu, .textbox, .card
```

Parent-Child relationships are also nouns:

```css
.noun {}              // parent: .card
.noun-noun {}         // child: .card-player
```

Subclasses are often preceded by an adjective describing the type of object:

```css
.noun-adjective {}    // examples: .card-baseball, .card-baseball-rookie
```

And modifiers are almost always adjectives (or are used descriptively):

```css
.is-state {}          // state: .is-selected, .is-hidden
.adjective {}         // examples: .left, .right, .block, .inline
```

Utility classes are used in special cases to override classes:

```css
.u-sr-only {}
.u-hidden {}
```

### Variables Naming Conventions

For colours, best practice dictates that colour names shouldn't be used in variable names. The following naming structure is recommended:

* brand-primary
* brand-secondary
* brand-tertiary

For shades of colour, use scalable language:

* brand-primary-lighter
* brand-primary-light
* brand-primary
* brand-primary-dark
* brand-primary-darker

If you're using Sass 3.3 (or later), consider using Sass maps to structure your colours:

```css
// create your colour palette
$palette: (
  primary: (
    opaque: rgba(x, 0, 0, .1),
    light:  rgb(x, 0, 0),
    base:  rgb(x, 0, 0),
    dark:  rgb(x, 0, 0)
  ),
  secondary: (
    opaque: rgba(x, 0, 0, .1),
    light:  rgb(x, 0, 0),
    base:  rgb(x, 0, 0),
    dark:  rgb(x, 0, 0)
  )
);

// use a Sass function to reference your colours
@function palette($colour, $tone: 'base') {
  @return map-get(map-get($palette, $colour), $tone);
}

// reference your colour
.page-title {
  color: palette(primary, dark);
  background-color: palette(primary, light);
  border-color: palette(primary);
}
```

### Number Values

```css
.btn {
  padding: 1.0em;   // wrong
  padding: 0.9em;   // wrong
  padding: 1em;     // right
  padding: .9em;    // right
}
```

### References

* https://medium.com/@fat/mediums-css-is-actually-pretty-fucking-good-b8e2a6c78b06
* http://thesassway.com/advanced/modular-css-naming-conventions