# Adenum CSS Architecture

## Introduction
Adenum CSS Architecture is a CSS organization/architecture guideline with an attempt to emphasize code maintenance, modularity, and readability.

## Example Code
```css
@charset 'utf-8';

/*** CSS reset ***/
@import url('/styles/reset.css');
/*** Webfonts ***/
@import url('/styles/webfont-Pretendard.css');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap');



/*** Common ***/
html, html * {
    box-sizing: border-box;
}
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    overflow: hidden;
    padding: 0;
    margin: -1px;
    border: 0;
    clip: rect(0, 0, 0, 0);
}
mark {
    background-color: transparent;
    color: inherit;
}

/*** Typography ***/
body {
    font-family: 'Pretendard', 'Noto Sans', sans-serif;
    font-weight: 400;
    line-height: 1.0;
}

/*** Layout ***/
header {
    width: 960px;
    margin: 0 auto;
}

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

## Common
Rules that are commonly applied to all blocks throughout the website may be set here. These rules are after the CSS reset sheet has been applied.
