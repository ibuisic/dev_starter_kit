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
    3. Things to avoid


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

**Use shorthand notation**  
- Shorten hexadecimal colour notation.  
- Define pseudo classes for links in the LoVe/HAte-order: Link, Visited, Hover, Active. You’re best off putting your styles in the order “link-visited-hover-active”, or “LVHA” for short.  
- Define element’s margin, padding or border in TRouBLed-order: Top, Right, Bottom, Left. When using shorthand to specify an element’s margin, padding or border, do it clockwise from the top: Top, Right, Bottom, Left.  

###3. Technical Tips  

- Messing with the grid system and adding style to bootstrap grid classes like `.container` and `.row`.  

- **Divitis** (Keeep wrappers and containers to a minimum) Save your document from structural bloat. Take advantage of the many structural elements to achieve layout. Do not add more div’s. Consider all options before adding additional wrappers (div’s) to achieve an effect when using a little nifty CSS can get you that same desired effect. Move ids and class naming as far up the document tree as you can. Leverage contextual selectors as much as possible. Don’t be afraid to be verbose in your selectors. Longer selectors can make css documents easier to read while also cutting down the chances of developing class- or divitis.

- **Keep properties to a minimum.** Work smarter, not harder with CSS. Under this rule, there are a number of subrules: if there isn’t a point to adding a CSS property, don’t add it; if you’re not sure why you’re adding a CSS property, don’t add; and if you feel like you’ve added the same property in lots of places, figure out how to add it in only one place. But, **Learn to exploit the cascading nature of CSS.** “Say you have two similar boxes on your website with only minor differences – you could write out CSS to style each box, or you could write CSS to style both at the same time, then add extra properties below to make one look different.

- **Avoid unnecessary selectors.** Using less selectors will mean less selectors will be needed to override any particular style — that means it is easier to troubleshoot.

- **Keep CSS hacks to a min** and use well known hacks. We will have a gist box up and running with all known hacks that are safe to use.

- **Use Variables** `variables.less` is should be opened at all times. Use as many variables as you can find in that file. Especially the colors. Avoid writing colors.

- **Use our common naming system** At the start of every project we should create a naming system. We want to avoid names that imply presentational aspects. Otherwise, if we name something right-col, it’s entirely possible that the CSS would change and our “right-col” would end up actually being displayed on the left side of our page. That could lead to some confusion in the future, so it’s best that we avoid these types of presentational naming schemes. Having a naming system for id’s and classes saves you a lot of time when looking for bugs, or updating your document.
