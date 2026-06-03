# Adenum CSS Guide

## Why Invest So Much Effort in a Language Like CSS?
One might wonder why I put so much work into a language like CSS. I believe there is already a good amount of great work done for other languages like JavaScript/TypeScript, Python, and Java&mdash;conventions, good practices, and design patterns. CSS features global scope and is prone to specificity pollution. As I coded in CSS, I was not truly proud of the CSS codebases I wrote. I just had to cope with such discomfort. For a long time, I thought it was my own lack of understanding and proficiency in CSS. As I discovered later on from blog posts front-end developers wrote, I learned that it is an inherent design problem of CSS. CSS was the only language that I had trouble writing clean, well-structured, trouble-free code. Therefore, I decided to organize and compile my 20 years' experience of dealing with CSS into this CSS guideline/architecture.

## Motivation to Create a CSS Architecture
Once at a firm, working with a codebase that was basically spaghetti code really exhausted me. This is my answer to messy codebases like those. It feels very tidy and clean to have an orderly system of CSS code. I put code maintainability first into consideration; anyone assigned after someone should be able to edit the website code since which part needs to be worked on is so predictable. One can just go to the related section. I also wanted to clear up the CSS specificity pollution issues. Adenum CSS Guide / Architecture is also the product of pursuit for code readability and clean markup code. Clean, readable markup code is advantageous for web accessibility and SEO.

## Credit to SMACSS
Adenum CSS Architecture is from my own experience and thoughts, but SMACSS methodology helped me shape the actual architecture&mdash;its emphasis on good structure, maintainability, modularization, and categorization of CSS code. SMACSS was my favorite CSS methodology among BEM, OOCSS, and SMACSS.

I was roughly developing my own CSS code structure by having these sections in the `style.css` file: `CSS reset`, `common/foundation`, `typography`, `specifics`. Around that period, I think I happened to hear about the SMACSS CSS methodology. I, too, was feeling thirsty for organizing CSS structure. Values SMACSS suggested matched with the values I have been pursuing&mdash;modularization, separated structure, categorization, and maintainability.

Now, I intend to finish writing the Adenum CSS Architecture/Guide document, referring to my own experience and thoughts of building web standards-compliant websites from 2007 to present as well as the SMACSS methodology.

## Copyright
© 2026 Adenum Services.  
All rights reserved.  
Adenum CSS Guide / Architecture is a work by Adenum Services.
