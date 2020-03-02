# HJC-nice-practice (Html, Js, Css)
Collection of some practice/general rule we used to write nice HTML, JS and CSS

## Purpose:
the purpose of this documentation to be the reference for the consistent SCSS/CSS, we have checked the best/most practices regarding CSS and styling in general. It provides a set of standards to help creating a CSS/SCSS document that is easy to read and easy to maintain.
 
## Pre-Processor
 SASS is currently being used to minify and construct our stylesheets.
 - A single, minified css file is the desired outcome, linked in the head of the document.
 - Make the CSS file external, so it is downloaded once and cached.

### Pre-Processor Command:
 - To generate css file from scss you can use a lot of tools, one of most common tool is 'sass command line'.
 - To install 'sass command line' to your device for linux user you can run this command ``` sudo apt install ruby-sass ```, and for other platform or other tools you can look to this url https://sass-lang.com/install.
 - To compile & work in project you need to run this command ``` sass --watch scss:css ```, this command will track any change of scss file, and modify css file direct.
 - To compile css file with compressed option you can run ``` sass --watch scss:css --style compressed ```, and this command its usfall for production version.
 - if you add compress arg, all comments, breaklines ...etc will be removed.
 
## General Rules:
 - There should be **only one .CSS file in the "css" root**, only one main .SCSS file, the hirarchy will be like the following:
    * css - (project's root styles folder)
        * styles.min.css
    * scss - (project root scss folder style)
        * main.scss (main scss file)
        * helpers (like _variables.scss, _mixins.scss)
        * components (like _buttons.scss, _navigation.scss, _dropdown.scss)
        * layout (like _header.scss, _footer.scss, _forms.scss)
        * pages (this will hase any custom/spesfic scss style for spesfic page only like _contact.scss)
        * themes (this will have any defferant theme style if exsits like spesfic them for _admin.scss)
 - All other sass partials **should be prefixed with an underscore and use the .scss file extension** and will be imported depending on the need of that partial.
 - Dont inlcude any unneeded library.
 - All general classes that we need will be added in an indepentedet file (like margins, padding, align center and text colours...)
 - We need to make sure to load js files only at end tags before we close body.
 - Write real comments on every section, and separate sections with comment from comments.
 - We will add a general variables file that contains all the numeric values for the variables and will use those varibles in the classes
 - Sometimes you will need to use JS in order to hook into a module. In that case, a separate class, prefixed with 'js' is recommended (js-class-name)
 - Use w3c validate markup to make sure all is good, it will help us fixing critical issues we see.

## General Comment Rules:
 - JS comment will be // for one line comment, and /* For multiple line comment */
 - CSS comment will be /* comment */
 - Html Comment will be <!-- comment -->
 - Html comment most be added before any main section and for each group / rows / menus / js file / css file..etc
 - Most be set comment before any CSS main section, this comment may be like this: /* ---------------------------------------------------------
 1. Main Sction ---------------------------------------------------------*/
 - We most add comment to describe the job for each custom js file in the top of file.
 - We most add comment to each js method thats describe method job, and params type & value, also return type if set.
 - We most add comment to each constant variable, global variable to describe why or where we need to use this varaible.
 
## HTML General Rules:
 - Make sure to add alt attribute in img tag.
 - Use title attribute with links, I refer to be on all links as we can.
 - Make sure we not using br html tag as we can, and using margin or padding nested.
 - Use Html5 tag in correct position as we can.
 - Make sure all tags is closed, and no one is opened without close it.
 - Use double ("") rather than single quotation marks ('') around attribute values.
 - We need to make sure to use dl tag for any description list as we can(Not required, but its nice to use in right place), for example we can set **address** in in address tag, and inside this tag we put dt with dd that contain address info. 

## JS General Rules:
 - For javascript async job, we need to make sure to use promise/async-await nested of nested function, I know both of them are truth to use, but nested function is old method and its hard to trace, update or maintenance code, promise/async-await is the best now.
 - We need to make sure to declare every variable in javascript with let, const, var keywords, dependence of scope. (we will work in strict mode).
 - Any constant value in javascript most be declared in top level of method, class using const keyword, and we most be make sure this value is const and cant be edited any where.

## SEO Friendly Rules:
 - Add needed meta tag in header (Keywords, Descriptions..)
 - Use headers(h1, h2...h6) carefully and most be hierarchy to let content is more good for seo.
 - Use em, and strong tag nested of i, and b tag. (its good choice for seo too and describe content truly)
 
## CSS Formatting:
 - Use all lowercase when creating a class or variable, or when referencing a div or element(Use dashes over camelCasing in class names)
 - Use single ('') rather than double ("") quotation marks for attribute selectors and property values.
 - Do not use quotation marks in URI values (url()).
 - avoid using **!important** to overrite styles.(**Dont use it as you can!!**)
 - Use number values for font weights, not words.
 - Do not use IDs as selectors(Try to use only classes to style the project)
 - Do not use tag selectors unnecessarily:
  
        // Wrong
        p.example-class {
            font-weight: 700;
        }
    
        // Right
        .example-class {
            font-weight: 700;
        } 
 - When styling html elements, use only a supplied theme or class:
  
         // Wrong 
         h1 {
            font-weight: 700;
         }
           
         //Right 
         .context-style {
            h1 {
                font-weight: 700;
            }
         }
         
 - we need to use Extend/Inheritance to  keep our Sass DRY
 - Import files should be at the end of the selector:
   
        .example-class {
           @include base;
   
           font-weight: 700;
   
           @import "heading";
           @import "subheading";
        }
 
    ### Media Queries:
     - Note: you cant @extend any style withen Media Query, you need to put your code inside it direct.
     
 
 

