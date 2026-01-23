# Adenum CSS Architecture

## Introduction
Adenum CSS Architecture is a CSS organization/architecture guideline with an attempt to emphasize code maintenance, modularity, and readability.

## Example Code
```css
@charset "UTF-8";

/*** =CSS reset ***/
@import url('/styles/reset.css');
/*** =Webfonts ***/
@import url('/styles/webfont-Pretendard.css');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap');



/******************************
 =Common
 ******************************/
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

/******************************
 =Typography
 ******************************/
body {
    font-family: 'Pretendard', 'Noto Sans', sans-serif;
    font-weight: 400;
    line-height: 1.0;
}

/******************************
 =Layout
 ******************************/
header {
    width: 960px;
    margin: 0 auto;
}

/******************************
 =Modules
 ******************************/

/******************************
 =Details
 ******************************/
/* BEGIN::body */
    body {
        background-color: #ffffff;
    }
/* END::body */
/* BEGIN::header */
    header {
    }
/* END::header */

/******************************
 =Motions
 ******************************/
```

## CSS Reset
In this example code, Eric Meyer's classic CSS reset sheet is imported first to reset the default styles of different web browsers. A CSS normalization sheet may be used instead.

## Webfonts
Webfont loading stylesheets, as many as needed, may be imported here.

## Common
Rules that are commonly applied to all blocks throughout the website may be set here. These rules are after the CSS reset sheet has been applied.

## Typography
Visual rhythm of text throughout the website is described here. A separate section from the section Details is assigned to easily edit the typographic rhythm for future maintenance. A new line is used for distinction between different Layout blocks.

## Layout
Layout blocks are the large frames that constitute a website.

A Layout block differs from a Module block in the way that a Layout block is used only once on a website, whereas a Module block may be used once or more on a website.

A CSS ID selector is used to label Layout blocks&mdash;`#masthead`, `#content`, `#sidebar`, `#footer`. The fact that an ID selector is only allowed for a single element suits well how a Layout block is only used once on a website.

## Modules
Module blocks are reusable components of a website. They may be used once or more in a website.

A CSS class selector is used to label Module blocks&mdash;`.description`, `.tag-cloud`, `.pinned`, `.pages`.
