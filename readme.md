#  Style and Theme Guide

1. General
    1. Getting started
    2. Bootstrap
    3. Grunt
    4. LESS Structure
    5. Naming page elements


2. Workflow
    1. Syntax
    2. Selector and Property Order


3. Technical Tips
    1. Things to avoid


##1. General



###1. Getting Started

There will be a main theme and a git repo created.  

Clone the repo:

    git clone git@circlewf.com:sitename.git

Navigate to the theme folder install grunt and dependencies:

    npm install
    npm install -g grunt-cli


###2. Bootstrap

Bootstrap files can be included via CDN or added to the theme.
A started sub-theme will be created with all bootstrap LESS files sorted, you can clone it into the theme folder.

###3. Grunt

- watch

- test

- build

- icons

###4. LESS Structure  

Master stylesheet `style.less` is located in the root of the LESS folder.
All created LESS files and all Bootstrap LESS files are imported in that file.
Comment out all the Bootstrap components that are not used.

Variables, mixins and reset files are loaded first. Pages and overrides are imported last.

All the reusable classes should be located in the `utilites.less` file.
Typography styles are located in the `type.less` file.

Folder structure will usually be set to:

    -- base  
    -- components  
    -- regions  
    -- pages  
    -- utilities  

blocks style should go to the **components** or **regions** folder it depends on the design, but if necessary you can add a **blocks** folder and add all the individual blocks style there.
Same thing goes for **views**, their style is usually in the **pages** folder.


##2. Workflow  
###1. Syntax

Important guidelines:
2 spaces are used for indentation  
Curly brackets go in the same line as the selector  
Do not use brackets for invoked selectors, write `.hide` instead off `.hide()`.


Other guidelines:

Only use the `&:extend` directive to extend placeholders and re-usable classes, not other selectors
Limit nesting to 2 level deep.
Avoid large numbers of nested rules.  

Don't over-abstract  
Write code to be readable and understandable, not to save bytes.



Comments are encouraged and should follow the below pattern:

    //----------------------------------------------------------
    // Section or component Title
    //
    // Description
    //----------------------------------------------------------

    .button{
        color: red
        // Create a larger hit area
        padding: 20px
    }


###2. Selector and Property Order

Write and nest your style the same way as you see them in the DOM. From top to bottom.

Properties within selectors should follow this order:

Mixins
Extends
Position
Box model
Typography
Decorative
For example:

    .component{
        .css-arrow(property)
        &:extend(.class)
        position
        top
        right
        z-index
        display
        width
        height
        margin
        padding
        border
        font-style
        font-weight
        line-height
        background
        box-shadow
        opacity
        outline
    }

##3. Technical Tips  


###1. Things to avoid

- Messing with the grid system and adding style to bootstrap grid classes like `.container` and `.row`.  
-


###1. Things to watch out for

- **Divitis** Keep containers and wrappers to a minimum. Save the document from a structural bloat. Do not add more div's, write more CSS.
-
