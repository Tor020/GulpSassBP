## Setup 
`git clone https://github.com/Tor020/GulpSassBP`

type `npm install` and then `gulp` in directory

gulp command will automatically setup the watch task and compile scss into css in the css folder




### this [The sass CSS archecitecture used here](http://ryanchristiani.com/getting-started-with-gulp-and-sass/) for more info 

### this [The sass CSS archecitecture used here](https://www.sitepoint.com/8-tips-help-get-best-sass/) for more info 

### this [sass cheatsheet](https://devhints.io/sass) sassCheatsheet 

### this [sass cheatsheet with more specifics of harder parts](https://devhints.io/sass) sassCheatsheet 


### Spacers

  configurable by changing the values of $sizeUnit (rem, em, px),
  $marginKey ('m', 'marg', 'margin', etc)
  $paddingKey ('p', 'pad', 'padding', etc)
  $separator ('-', '_', '' for none, etc) and $sizes (whatever keys/values you need)

```
$sizeUnit: rem;
$marginKey: 'm';
$paddingKey: 'p';
$separator: '-';
$sizes: (
    ('none', 0),
    ('xxs', 0.125),
    ('xs', 0.25),
    ('sm', 0.5),
    ('md', 1),
    ('lg', 2),
    ('xl', 4),
    ('xxl', 8),
);
$positions: (
    ('t', 'top'),
    ('r', 'right'),
    ('b', 'bottom'),
    ('l', 'left')
);

@function sizeValue($key, $value) {
    @return if($key == 'none', 0, $value + $sizeUnit);
}

@each $size in $sizes {
    $sizeKey: nth($size, 1);
    $sizeValue: nth($size, 2);
    .#{$marginKey}#{$separator}#{$sizeKey} {
        margin: sizeValue($sizeKey, $sizeValue);
    }
    .#{$paddingKey}#{$separator}#{$sizeKey} {
        padding: sizeValue($sizeKey, $sizeValue);
    }
    @each $position in $positions {
        $posKey: nth($position, 1);
        $posValue: nth($position, 2);
        .#{$marginKey}#{$separator}#{$posKey}#{$separator}#{$sizeKey} {
            margin-#{$posValue}: sizeValue($sizeKey, $sizeValue);
        }
        .#{$paddingKey}#{$separator}#{$posKey}#{$separator}#{$sizeKey} {
            padding-#{$posValue}: sizeValue($sizeKey, $sizeValue);
        }
    }
}
```

```
.m-none { margin: 0; }
.p-none { padding: 0; }
.m-t-none { margin-top: 0; }
.p-t-none { padding-top: 0; }
.m-r-none { margin-right: 0; }
.p-r-none { padding-right: 0; }
.m-b-none { margin-bottom: 0; }
.p-b-none { padding-bottom: 0; }
.m-l-none { margin-left: 0; }
.p-l-none { padding-left: 0; }
.m-xxs { margin: 0.125rem; }
.p-xxs { padding: 0.125rem; }
.m-t-xxs { margin-top: 0.125rem; }
.p-t-xxs { padding-top: 0.125rem; }
.m-r-xxs { margin-right: 0.125rem; }
.p-r-xxs { padding-right: 0.125rem; }
.m-b-xxs { margin-bottom: 0.125rem; }
.p-b-xxs { padding-bottom: 0.125rem; }
.m-l-xxs { margin-left: 0.125rem; }
.p-l-xxs { padding-left: 0.125rem; }
.m-xs { margin: 0.25rem; }
.p-xs { padding: 0.25rem; }
.m-t-xs { margin-top: 0.25rem; }
.p-t-xs { padding-top: 0.25rem; }
.m-r-xs { margin-right: 0.25rem; }
.p-r-xs { padding-right: 0.25rem; }
.m-b-xs { margin-bottom: 0.25rem; }
.p-b-xs { padding-bottom: 0.25rem; }
.m-l-xs { margin-left: 0.25rem; }
.p-l-xs { padding-left: 0.25rem; }
.m-sm { margin: 0.5rem; }
.p-sm { padding: 0.5rem; }
.m-t-sm { margin-top: 0.5rem; }
.p-t-sm { padding-top: 0.5rem; }
.m-r-sm { margin-right: 0.5rem; }
.p-r-sm { padding-right: 0.5rem; }
.m-b-sm { margin-bottom: 0.5rem; }
.p-b-sm { padding-bottom: 0.5rem; }
.m-l-sm { margin-left: 0.5rem; }
.p-l-sm { padding-left: 0.5rem; }
.m-md { margin: 1rem; }
.p-md { padding: 1rem; }
.m-t-md { margin-top: 1rem; }
.p-t-md { padding-top: 1rem; }
.m-r-md { margin-right: 1rem; }
.p-r-md { padding-right: 1rem; }
.m-b-md { margin-bottom: 1rem; }
.p-b-md { padding-bottom: 1rem; }
.m-l-md { margin-left: 1rem; }
.p-l-md { padding-left: 1rem; }
.m-lg { margin: 2rem; }
.p-lg { padding: 2rem; }
.m-t-lg { margin-top: 2rem; }
.p-t-lg { padding-top: 2rem; }
.m-r-lg { margin-right: 2rem; }
.p-r-lg { padding-right: 2rem; }
.m-b-lg { margin-bottom: 2rem; }
.p-b-lg { padding-bottom: 2rem; }
.m-l-lg { margin-left: 2rem; }
.p-l-lg { padding-left: 2rem; }
.m-xl { margin: 4rem; }
.p-xl { padding: 4rem; }
.m-t-xl { margin-top: 4rem; }
.p-t-xl { padding-top: 4rem; }
.m-r-xl { margin-right: 4rem; }
.p-r-xl { padding-right: 4rem; }
.m-b-xl { margin-bottom: 4rem; }
.p-b-xl { padding-bottom: 4rem; }
.m-l-xl { margin-left: 4rem; }
.p-l-xl { padding-left: 4rem; }
.m-xxl { margin: 8rem; }
.p-xxl { padding: 8rem; }
.m-t-xxl { margin-top: 8rem; }
.p-t-xxl { padding-top: 8rem; }
.m-r-xxl { margin-right: 8rem; }
.p-r-xxl { padding-right: 8rem; }
.m-b-xxl { margin-bottom: 8rem; }
.p-b-xxl { padding-bottom: 8rem; }
.m-l-xxl { margin-left: 8rem; }
.p-l-xxl { padding-left: 8rem; }

```


### Colors 
[Color Mixing Utility for Sass](https://codepen.io/Tor020/pen/ooQZzz?editors=0110)

http://jackiebalzer.com/color

https://robots.thoughtbot.com/controlling-color-with-sass-color-functions

```
darken($color, 5%)
lighten($color, 5%)
saturate($color, 5%)
desaturate($color, 5%)
grayscale($color)
adjust-hue($color, 15deg)
compliment($color)    
invert($color)
fade-in($color, .5)   
fade-out($color, .5)  
rgba($color, .5)      
```

### Overview 

```
Methods in this module are accessible from the SassScript context. For example, you can write
$color: hsl(120deg, 100%, 50%)
and it will call #hsl.
The following functions are provided:
Note: These functions are described in more detail below.
```

### RGB Functions 

```
rgb($red, $green, $blue) : Creates a Color from red, green, and blue values.
rgba($red, $green, $blue, $alpha) : Creates a Color from red, green, blue, and alpha values.
red($color) : Gets the red component of a color.
green($color) : Gets the green component of a color.
blue($color) : Gets the blue component of a color.
mix($color1, $color2, [$weight]) : Mixes two colors together.
```

### HSL Functions 

```
hsl($hue, $saturation, $lightness) : Creates a Color from hue, saturation, and lightness values.
hsla($hue, $saturation, $lightness, $alpha) : Creates a Color from hue, saturation, lightness, and alpha values.
hue($color) : Gets the hue component of a color.
saturation($color) : Gets the saturation component of a color.
lightness($color) : Gets the lightness component of a color.
adjust-hue($color, $degrees) : Changes the hue of a color.
lighten($color, $amount) : Makes a color lighter.
darken($color, $amount) : Makes a color darker.
saturate($color, $amount) : Makes a color more saturated.
desaturate($color, $amount) : Makes a color less saturated.
grayscale($color) : Converts a color to grayscale.
complement($color) : Returns the complement of a color.
invert($color, [$weight]) : Returns the inverse of a color.
```

### Opacity Functions 

```
alpha($color) / opacity($color) : Gets the alpha component (opacity) of a color.
rgba($color, $alpha) : Changes the alpha component for a color.
opacify($color, $amount) / fade-in($color, $amount) : Makes a color more opaque.
transparentize($color, $amount) / fade-out($color, $amount) : Makes a color more transparent.
```

### Other Color Functions 

```
adjust-color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha]) : Increases or decreases one or more components of a color.
scale-color($color, [$red], [$green], [$blue], [$saturation], [$lightness], [$alpha]) : Fluidly scales one or more properties of a color.
change-color($color, [$red], [$green], [$blue], [$hue], [$saturation], [$lightness], [$alpha]) : Changes one or more properties of a color.
ie-hex-str($color) : Converts a color into the format understood by IE filters.
```

### String Functions 

```
unquote($string) : Removes quotes from a string.
quote($string) : Adds quotes to a string.
str-length($string) : Returns the number of characters in a string.
str-insert($string, $insert, $index) : Inserts $insert into $string at $index.
str-index($string, $substring) : Returns the index of the first occurrence of $substring in $string.
str-slice($string, $start-at, [$end-at]) : Extracts a substring from $string.
to-upper-case($string) : Converts a string to upper case.
to-lower-case($string) : Converts a string to lower case.
```

### Number Functions 

```
percentage($number) : Converts a unitless number to a percentage.
round($number) : Rounds a number to the nearest whole number.
ceil($number) : Rounds a number up to the next whole number.
floor($number) : Rounds a number down to the previous whole number.
abs($number) : Returns the absolute value of a number.
min($numbers...) : Finds the minimum of several numbers.
max($numbers...) : Finds the maximum of several numbers.
random([$limit]) : Returns a random number.
```

