# Adenum CSS Architecture

## Introduction
Adenum CSS Architecture is a CSS organization/architecture guideline with an attempt to emphasize code maintenance and readability.

## Example Code
```css
/*** CSS reset ***/
/*** Webfonts ***/



/*** Common ***/

/*** Typography ***/

/*** Modules ***/

/*** Details ***/
/* BEGIN::body */
    body {
        background-color: #ffffff;
    }
/* END::body */
/* BEGIN::header */
    header {
    }
/* END::header */

/*** Animations ***/
```

## CSS reset
In my case, I import Eric Meyer's CSS reset sheet to reset the default stylesheets of different web browsers. One might use a CSS normalization sheet.

## Webfonts
One may import as many webfont loading stylesheets as he/she needs.
