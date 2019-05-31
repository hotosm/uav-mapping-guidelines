# HOT Documentation Site Template

Template for creating HOT documentation sites. 

This project uses the [Hugo](https://gohugo.io/) site generator for static HTML generation for Markdown content.

HOT maintains a custom HOT theme for Hugo sites here: [https://github.com/hotosm/hugo-book](https://github.com/hotosm/hugo-book)


To create a new HOT documentation site clone this repo:

```sh
git clone https://github.com/hotosm/hot-docs-template.git 
```

Then clone the HOT hugo-book theme 
```
cd hot-docs-template
git submodule add https://github.com/hotosm/hugo-book themes/book
```

This template automates build and deployment using [CircleCI](https://circleci.com/). To take advantage of this functionality, a github repository and access to CircleCI is required. 


## Building a new site

# Tutorial

1. Clone this repo and create a new github repository to host the site content. 
```
git clone https://github.com/hotosm/hot-docs-template.git my-docs-site
cd my-docs-site
git submodule add https://github.com/hotosm/hugo-book themes/book
git 
```

2. Update site configuration

```toml
languageCode = "en-us"
title = "My Docs Site" <-- site name
theme = "book"
DefaultContentLanguage = "en"
relativeurls = true
enableGitInfo = true

[params]
    BookRepo = "https://github.com/hotosm/my-docs-site"  <-- GitHub repo address
    BookShowToC = false
    BookEditPath = "/edit/master/content/"

[imaging]
    resampleFilter = "box"
    quality = 75
```

3. Set up CircleCI integration

      i. Launch your github repo as a project on CircleCI

      ii. Add an SSH key to the github repository with 'write' access. follow this guide:
          [https://circleci.com/docs/2.0/add-ssh-key/](https://circleci.com/docs/2.0/add-ssh-key/)
      
      iii. Add the SSH keygen fingerprint to the circleCI .circleci/config.yml file in your repo
      e.g. 
      ```
          - add_ssh_keys:
              fingerprints:
                - "b4:94:b8:6b:f4:0b:b5:0e:40:ba:1c:f7:b8:d9:d4:4c"
      ```


## In-depth guide/Customizing your site

### Configuration

Site level settings are stored in the [config.toml](./config.toml) at the root of this project. Other than customizing some features of the site you need to change the ``` title ``` and ``` BookRepo ``` keys.

```toml
languageCode = "en-us"
title = "HOT Toolbox" <-- change me
theme = "book"
DefaultContentLanguage = "en"
relativeurls = true
enableGitInfo = true

[params]
    BookRepo = "https://github.com/hotosm/toolkit-site"  <-- change me
    BookShowToC = false
    BookEditPath = "/edit/master/content/"

[imaging]
    resampleFilter = "box"
    quality = 75
```


### Content

All Markdown content goes in the content directory. At minimum a site should have an ```_index.md``` file at the root of the content directory and a ```pages/``` directory with at least one markdown content page.  

* The ```_index.md``` file serves as the main landing page of the site or the / route of the page. 
* The ```pages/``` directory holds all pages listed in the file menu on the left of the page. 


The structure should be as follows:
```
content/
├── _index.md
└── pages/
    └── about.md
    └── contact.md

```

This content would create the following pages:

_index.md ---> https://example.com/

about.md ---> https://example.com/pages/about

contact.md ---> https://example.com/pages/contact


#### Alternative Content structures

Hugo provides other ways to organize content in two other ways: Leaf Bundles and Branch Bundles

Read more about page bundling here:
[https://gohugo.io/content-management/page-bundles/](https://gohugo.io/content-management/page-bundles/)


#### Front Matter

By default the name of the file in the /content/pages directory will be listed in the menu and in the URL with spaces escaped with dashes `-`. 

e.g. ```content/pages/how-i-spent-my-summer-vacation.md``` will show as How I Spent My Summer Vacation in the menu and as 
example.com/pages/how-i-spent-my-summer-vacation

You can change the title of the content in the Markdown front matter with the "title" parameter. e.g.


how-i-spent-my-summer-vacation.md
```md
---

title: Summer Essay - How I Spent My Summer Vacation

---

# Article Title

Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
sed do eiusmod tempor incididunt ut labore et dolore magna 
aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
...
```


#### Table of Contents

By defualt in the main project config.toml file a right hand side Table of Contents is disabled.  If you need this enabled project-wide you can change this value to ``` true ``` in the TOML file or override in individual Markdown file by adding the ```  ``` option to the front matter. Table of contents will create a list of anchor points from the markdown header elements 
(``` # ## ### ### ```) and clicking them will auto scroll you to that section of the page. 

e.g
```md
---

title: Summer Essay - How I Spent My Summer Vacation
bookShowToC: True

---
```


Alternatively if you wish to have the Table of Contents always on by default across the site you can add a ``` params ``` ``` BookShowToC ``` value in the site config.toml

e.g. 
```toml
[params]
  BookShowToC = true
```


#### Page Order

Hugo will use the MarkDown document's name as its first method of sorting content. e.g. about.md will come before contact.md.  You can override this and at your own sort order to documents by using the ``` weight ``` option in the frontmatter. For the weight value lower ranks higher so 1 will come before 2 before 3 etc. Weighting is scoped to the directory it is within, when using nested structure the order will only relate to the content order within that section.

```md
---

title: Summer Essay - How I Spent My Summer Vacation
weight: 1

---

# Article Title

Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
sed do eiusmod tempor incididunt ut labore et dolore magna 
aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
...
```



### Search

Full text search is supported using [lunr.js](https://lunrjs.com/).  Multi language support is limited to those supported by [lunr-languages](https://github.com/MihaiValentin/lunr-languages). If content is provided in that language a search index will not be created and the search bar will not appear in the nav bar.


### Multi-language Sites

This template allows for building multi-language sites by simply creating directories for each language needed, following the same directory structure as a single language site. an example folder structure is as follows:

```
content/
├── english/
│   ├── _index.md
│   └── pages
|       └── about.md 
└── french/
    ├── _index.md
    └── pages
        └── à-propos.md 
```


Then in your site config.toml tell Hugo how to find these directories:

```toml
[languages]
  [languages.en]
    contentDir = "content/english"
    languageName = "English"
    weight = 10
  [languages.fr]
    contentDir = "content/french"
    languageName = "Français"
    weight = 20
```

This will default the site to English but allow you to access the French content but suffixing a /fr to the base URL.

e.g.

https://example.com/pages/about

https://example.com/fr/pages/a-propos


### CircleCI

CircleCI manages the build and deployment process to allow continuous deployment of the site on new changes. In the default configuration listed here CircleCI will only fire on commits on the master branch and will deploy to the gh-pages branch.  Both these branches are required for this configuration to properly function.  If you wish to skip the build and deploy process on a commit simply add ``` [ci skip] ``` to you commit message in git. e.g.

```
git commit -m "added new content [ci skip]"
```

### Local development

To build this site locally an installation of Hugo is required. Hugo binaries for all platforms are available here:

[https://github.com/gohugoio/hugo/releases](https://github.com/gohugoio/hugo/releases)


Clone this repo with the ``` --recurse-submodules ```:

```sh
git clone --recurse-submodules https://github.com/hotosm/my-documentation-repo.git
```

change directory into the cloned repo and run Hugo

```sh
cd my-documentation-repo
hugo serve
```

This builds and runs a local webserver with hot-reloading for local content development.

If the default port is available you can navigate to the built development site at http://localhost:1313 in your browser.
If 1313 is already in use by another program hugo will choose another port and return it to the stdout of your terminal
e.g.

```sh
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at //localhost:58696/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```


### Contributing