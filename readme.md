#  Style and Theme Guide

1. General
    1. Getting started
    2. Bootstrap
    3. Grunt
    4. LESS Structure
    5. Naming page elements


2. Workflow
    1. Syntax
    2. Selectors Order
    3. Property Order


3. [Technical Tips](tech-tips)

##LESS Structure

Folder structure will usually be set to:


    -- base  
    -- components  
    -- regions  
    -- pages  
    -- utilities  


blocks style should go to the **components** or **regions** folder it depends on the design, but if necessary you can add a **blocks** folder and add all the individual blocks style there.
Same thing goes for **views**, their style is usually in the **pages** folder.













<h2 id="head1"> Getting started <h2>

<hr>
This is the workflow you should adopt for a typical feature.

- Get the latest version of master

```
git pull origin master
```

- Create your own feature branch, prefixed by your initials. Branches should be scoped to one feature and short-lived.

```
git checkout -b iw-feature
```

- Discuss the feature with another developer, they should eventually review your code.

- Do some work

- Push to a remote branch, [rebasing](rebasing) beforehand if you have redundant commits which should be squashed

- Create a Pull Request

- Ask another developer to review the code

- Reply to comments and make amends

- Merge into master once you receive a +1

- Delete your feature branch
