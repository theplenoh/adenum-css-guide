# Adenum CSS Architecture

## Introduction
Adenum CSS Architecture is a CSS organization/architecture guideline with an attempt to emphasize code maintenance, modularity, and readability.

## Motivation to Create a CSS Architecture
Once at a firm, working with a codebase that was basically spagetti code really exhausted me. This is my answer to messy codebases like those. It feels very tidy and clean to have an orderly system of CSS code. I put code maintainability first into consideration; anyone deployed after someone should be able to edit the website code since which part needs to be worked on is very predictable. One can go to the related section. I also wanted to clear up the CSS specificity pollution issues. Adenum CSS Guide / Architecture is also the product of pursuit for code readability and clean markup code. Clean, readable markup code is advantageous for web accesibility and SEO.

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
Layout blocks are the large frames that constitute the layout of a website.

A Layout block differs from a Module block in the way that a Layout block is used only once on a website, whereas a Module block may be used once or more on a website.

CSS ID selectors are used to label Layout blocks&mdash;`#masthead`, `#content`, `#sidebar`, `#footer`. The fact that an ID selector is only allowed for a single element suits well how a Layout block is only used once on a website.

## Modules
Module blocks are reusable components of a website. They may be used once or more in a website.

Module blocks are placed inside a Layout block.

CSS class selectors are used to label Module blocks&mdash;`.description`, `.tag-cloud`, `.pinned`, `.pages`.

CSS declarations here define structural details of reusable blocks on a website.

## Details
Details are CSS properties that describe blocks, including decorative parts such as background images, border styles or micro-adjustments.

An ID selector that specifies which Layout block a Module belongs to comes before the Module name. It serves as a namespace in a way. Everything is globally scoped in CSS, so specifying what Layout block a Module belongs to adds to managed specificity.

It is intended that specificity increases from broader declarations to very particular rules as the parser runs from the top of the stylesheet to the bottom&mdash;CSS Reset, Webfonts, Common, Typography, Layout, Modules, Details, Motions.

Optionally, States and Theme can come between Details and Motions&mdash;CSS Reset, Webfonts, Common, Typography, Layout, Modules, Details, *States*, *Theme*, Motions.

## Motions
The section Motions describe animations and interative parts on the website.
