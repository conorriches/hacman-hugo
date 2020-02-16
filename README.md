
# Hackspace Manchester website
:computer: hacman.netlify.com

---

## Non-technical folk - please read this section

### Do you want a change to the content (images, copy etc)? 
Post what URL you'd like changes to, and what changes you want to the [forum](list.hacman.org.uk).

### Do you want a change to how the site looks?
Please post your idea on the [forum](list.hacman.org.uk), being as specific as possible.  

### Any bugs?
Also please post on the forum with details on how we can make the bug appear, what browser you're using, and what device you're using.

---



This site uses [Hugo](https://gohugo.io/) and a fork of the [Paper CSS](papercss-hugo-theme.netlify.com/) theme.



## Development
This site is statically generated, meaning that we have our data, and when we build the site, it spits out a fully formatted, complete, HTML website.

### Install Hugo
https://gohugo.io/getting-started/installing

### Making changes

#### Editing the content

To edit the content, look in the `content` directory - all files are stored in Markdown.

Benefits are:
* Standardised styles, no hacking in one off styles
* Write markdown using your code editor, [this online tool](https://stackedit.io/app#) or something like Google Docs then hand it to a site admin.
* There is a predefined set of shortcodes for things like alerts and buttons - [check them out here](https://papercss-hugo-theme.netlify.com/papercss-shortcodes/)

#### Frontmatter / Meta content

Our Markdown files use [Frontmatter](https://gohugo.io/content-management/front-matter/) to add meta content. 

Example meta content for an area:
```
+++
    title = "Visual Arts"
    layout = "single"
    description = "This is where painting, laser cutting, 3D printing, photography, large format printing happen and where lots of stationery live."

    [[resources]]
        name = "header"
        src = "/header.jpg"
+++
```


Example meta content for a tool:
```
+++
    title = "CNC Machine"
    type = "tools"
    layout = "single"
    training_required = true
    area = "woodworking"
    danger_level="2"
+++
```


This means, for example, a tool can define what area it lives in and therefore an area page can automatically output the tools that live there without having to update two pages. Neat.

Featured images are also used - see the resources array, just set the name to be "header". 

*Please read the section on File Structure below!*

#### Menus
The main menu is defined in `config.toml`

### File structure
The file structure within the `content` folder relates to the URL structure that's produced when `hugo build` is run:
* `content/areas/visual_arts` maps to the URL `<domain.com>/areas/viual_arts`
* If you're at the end of a path (a leaf node) then you can call a file `index.md`
* If you're at a branch node, call the main file `_index.md` or it will catch every path under the branch.
* Assets (like images) live in the same folder as the content they relate to.
  
### Examples
* `content/about/_index.md` will map to `<domain.com>/about/`
*  `content/about/board.md` will map to `<domain.com>/about/board`


#### Editing the theme
To edit the theme, you want to edit the sub repo hacman-paper, which is not in this repo.


#### Scripts
* `hugo build` will build the site and produce fully formed HTML.
* `hugo server -D` to run the development server which will mean the site auto updates as you make changes


## Hosting
The site is currently hosted on Netlify. This is great because we just hand it our repo, it reads `netlify.toml` and then it builds the site every time someone merges into master. 


## Further Reading
### Hugo:
* [Page bundles](https://gohugo.io/content-management/page-bundles/)
* [Front matter](https://gohugo.io/content-management/front-matter/)
* [Sections](https://gohugo.io/content-management/sections/)
  

### Theme:
* [paperCSS - the theme we foked off](papercss-hugo-theme.netlify.com/)