# Adenum CSS Architecture

## Introduction
Adenum CSS Architecture is a CSS organization/architecture guideline with an attempt to emphasize code maintenance, modularity, and readability. It is a guideline that preserves classical values of web standards&mdash;semantic markup and use of the ID selector&mdash;and cleverly combines modern managing techniques such as layered CSS sections.

## Example Code
```css
@charset "UTF-8";

/*** =CSS Reset ***/
@import url("/styles/reset.css");
/*** =Webfonts ***/
@import url("/styles/webfont-Pretendard.css");
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap");
/*** =Only applied to IE11 ***/
@import url("/styles/ie11-patch.css");



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

    a {
        color: inherit;
        text-decoration: inherit;
    }
    a:hover {
        color: #4c89c6;
        text-decoration: underline;
    }

/******************************
 =Typography
 ******************************/
    body {
        font-family: 'Noto Sans', sans-serif;
        font-size: 14px;
        font-weight: 400;
        line-height: 1.0;
        color: #666;
    }

    #masthead {
        font-size: 13px;
        color: #fff;
    }
    #masthead a {
        color: inherit;
        text-decoration: none;
    }
    #masthead h1 {
        font-family: 'Open Sans', sans-serif;
        font-size: 36px;
        font-weight: 700;
        line-height: 44px;
    }
    #masthead .subtitle {
        font-size: 13px;
        line-height: 20px;
        letter-spacing: -0.01em;
    }
    #masthead .links {
        letter-spacing: -0.01em;
    }
    @media screen and (max-width: 1023px) {
        #masthead h1 {
            font-size: 29px;
        }
        #masthead .subtitle {
            font-size: 12px;
            line-height: 10px;
        }
    }

    #content .post-entry {
        font-family: 'Pretendard', sans-serif;
    }
    #content .post-entry h2 {
        font-size: 20px;
        font-weight: 500;
        color: #333;
    }
    #content .post-entry-body p {
        margin: 1.0em 0;
        line-height: 1.6;
    }

    #sidebar {
        font-family: 'Pretendard', sans-serif;
    }
    #sidebar .pages {
        font-size: 13px;
    }

/******************************
 =Layout
 ******************************/
    body {
        position: relative;
    }

    #masthead {
        width: 100%;
    }
    #masthead > .wrap-inner {
        position: relative;
        width: 960px;
        height: 110px;
        margin: 0 auto;
    }
    #masthead .gnb {
        display: none;
    }
    @media screen and (max-width: 1023px) {
        #masthead > .wrap-inner {
            width: 100%;
            height: 80px;
        }
    }

    #container {
        display: flex;
        align-items: stretch;
        width: 960px;
        min-height: calc(100vh - 110px);
        margin: 0 auto;
    }
    @media screen and (max-width: 1023px) {
        #container {
            width: 100%;
        }
    }
    #content {
        width: 710px;
        padding: 30px 0 30px;
    }
    @media screen and (max-width: 1023px) {
        #content {
            width: 100%;
            padding: 15px 15px 30px;
        }
    }
    #sidebar {
        width: 220px;
        margin-left: 30px;
        padding: 30px 15px 30px;
    }
    @media screen and (max-width: 1023px) {
        #sidebar {
            width: 290px;
            height: 100%;
            padding: 0 15px 30px;
        }
    }

/******************************
 =Modules
 ******************************/
    .description {
        font-size: 11px;
        line-height: 1.2;
    }
    .pages {
        margin: 10px 0;
    }

    .post-entry {
        margin-bottom: 40px;
    }

/******************************
 =States
******************************/
    .is-open {
        display: block !important;
    }

/******************************
 =Details
 ******************************/
/* BEGIN::body */
    body {
        background: #fff;
    }
/* END::body */
/* BEGIN::#masthead */
    #masthead {
        background: transparent url('/images/header-bg.png') 50% 0 repeat-x;
    }
    #masthead .wrap-inner {
        background: transparent url('/images/header-bg.png') repeat-x;
        background-position-y: 50%;
        background-position-x: 0;
    }
    #masthead .logo {
        padding-top: 27px;
    }
    #masthead .links {
        position: absolute;
        top: 0;
        right: 0;
        padding-top: 71px;
    }
    #masthead .links > ul {
        display: flex;
    }
    #masthead .links > ul > li > a {
        display: block;
        padding: 6px 6.5px;
        text-transform: uppercase;
    }
    @media screen and (max-width: 1023px) {
        #masthead > .wrap-inner {
            background-position-y: calc(50% + 10px);
        }
        #masthead .logo {
            flex-shrink: 0;
            padding-top: 12px;
            padding-left: 15px;
        }
        #masthead .gnb {
            display: block;
            position: absolute;
            top: 0;
            right: 0;
            width: 70px;
            height: 80px;
        }
        #masthead .links {
            position: absolute;
            width: 1px;
            height: 1px;
            overflow: hidden;
            padding: 0;
            margin: 1px;
            border: 0;
            clip: rect(0, 0, 0, 0);
        }
        #masthead .gnb .btn-menu {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 24px;
            height: 16px;
            margin-top: -24px;
            margin-left: -24px;
            padding: 25px;
            border: 0 none;
            cursor: pointer;
            clip: auto;
            background-color: transparent;
        }
        #masthead .gnb .btn-menu > span {
            position: absolute;
            top: 0;
            left: 50%;
            width: 24px;
            height: 3px;
            margin-top: 25px;
            margin-left: -12px;
            background-color: #fff;
            font-size: 0;
        }
        #masthead .gnb .btn-menu > span::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            width: 24px;
            height: 3px;
            margin-top: -7px;
            margin-left: -12px;
            background-color: #fff;
        }
        #masthead .gnb .btn-menu > span::after {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            width: 24px;
            height: 3px;
            margin-top: 7px;
            margin-left: -12px;
            background-color: #fff;
        }
    }
/* END::#masthead */
/* BEGIN::#content */
    #content .post-entry h2 {
        padding: 7px 0;
    }
    #content .post-entry header {
        border-bottom: 1px solid #ccc;
        margin-bottom: 0.45em;
    }
    #content .post-entry header > div {
        display: flex;
        justify-content: space-between;
        padding: 0.25em 0 0.45em;
    }
    #content .post-entry-info dl > * {
        display: inline-block;
    }
    #content .post-entry-info dd {
        margin-right: 0.25em;
    }
    #content .post-entry-info dd > time {
        font-family: 'Noto Sans', sans-serif;
        font-size: 0.95em;
    }
    #content .post-entry-mgmt ul > * {
        display: inline-block;
    }
    #content .post-entry-mgmt li {
        margin-right: 0.25em;
    }
/* END::#content */
/* BEGIN::#sidebar */
    #sidebar {
        background-color: #f7f7f7;
    }
    #sidebar .ctrl {
        display: none;
    }
    #sidebar .pages li > a {
        display: inline-block;
        padding: 5px 0;
    }
    #sidebar-overlay {
        display: none;
    }
    @media screen and (max-width: 1023px) {
        #sidebar {
            display: none;
            position: absolute;
            z-index: 100;
            top: 0;
            right: 0;
        }
        #sidebar .ctrl {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            height: 80px;
        }
        #sidebar .ctrl a {
            position: absolute;
            display: block;
            width: 28px;
            height: 28px;
            margin-top: 3px;
            margin-right: 5px;
        }
        #sidebar .ctrl a img {
            width: 28px;
            height: auto;
            padding: 3.5px;
        }
        #sidebar-overlay {
            display: none;
            position: absolute;
            z-index: 10;
            width: 100vw;
            height: 100%;
            background-color: #ccc;
            opacity: 0.65;
            top: 0;
            right: 0;
        }
    }
/* END::#sidebar */

/******************************
 =Animations
 ******************************/

/*** =Scaffolding ***/
#footer, #sidebar-overlay {
    display: none;
}
```

## CSS Reset
In the example code, Eric Meyer's classic CSS reset sheet is imported first to reset the default styles of different web browsers. A CSS normalization sheet may be used instead.

## Webfonts
Webfont loading stylesheets, as many as needed, may be imported here.

## Common
Rules that are commonly applied to all blocks throughout the website may be set here. These rules are after the CSS reset sheet has been applied.

## Typography
Visual rhythm of text throughout the website is described here. A separate section from the section Details is assigned to easily edit the typographic rhythm for later maintenance. A new line is used for distinction between different Layout blocks.

## Layout
Layout blocks are the large frames that constitute the layout of a website.

A Layout block differs from a Module block in the way that a Layout block is used only once in a website, whereas a Module block may be used once or more on a website.

CSS ID selectors are used to label Layout blocks&mdash;`#masthead`, `#content`, `#sidebar`, `#footer`. The fact that an ID selector is only allowed for a single element suits well how a Layout block is only used once in a website.

## Modules
Module blocks are reusable components of a website. They may be used once or more in a website.

Module blocks are placed inside a Layout block.

CSS class selectors are used to label Module blocks&mdash;`.description`, `.tag-cloud`, `.pinned`, `.pages`.

CSS declarations here define structural details and common decorative properties of reusable blocks in a website.

## States
States defined here can be overridden by details in the next section. That is why the section States precedes the section Details.

States are general properties that represent the state of an element&mdash;`.is-open`, `.is-closed`, `is-active`, `is-hidden`.

## Details
Details are CSS properties that describe blocks, including decorative parts such as background images, border styles or micro-adjustments.

An ID selector that specifies which Layout block a Module belongs to comes before the Module name. It serves as a namespace in a way. Everything is globally scoped in CSS, so specifying which Layout block a Module belongs to contributes to managed specificity.

It is intended that specificity increases from broader, more general declarations to very particular rules as the CSS parser runs from the top of the stylesheet to the bottom&mdash;CSS Reset, Webfonts, Common, Typography, Layout, Modules, Details, Animations.

Optionally, the section Theme can come between Details and Motions, and the section States can be placed between Modules and Details&mdash;CSS Reset, Webfonts, Common, Typography, Layout, Modules, *States*, Details, *Theme*, Animations.

## Animations
The section Animations describe animations and interactive parts on the website.

## Scaffolding
The section Scaffolding contains temporary code used during development. It may include code that hides blocks that have not yet been worked on, since unfinished blocks can be distracting and visually unpleasant.
