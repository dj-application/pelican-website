## What is Pelican?
Pelican is a Python library that lets you generate static websites from templates.

## 1. Installation
```
# Install pelican
pip install pelican markdown

# Choose a name for your project (e.g. pelican-website) and directory for your site (fishingbird)
mkdir -p pelican-website/fishingbird
cd pelican-website/fishingbird
```

## 2. Generate the initial boilerplate
```
pelican-quickstart

> Where do you want to create your new web site? [.]
> What will be the title of this web site? Fishing Birds
> Who will be the author of this web site? j
> What will be the default language of this web site? [en]
> Do you want to specify a URL prefix? e.g., https://example.com   (Y/n) n
> Do you want to enable article pagination? (Y/n) Y
> How many articles per page do you want? [10]
> What is your time zone? [Europe/Paris]
> Do you want to generate a tasks.py/Makefile to automate generation and publishing? (Y/n) Y
> Do you want to upload your website using FTP? (y/N) n
> Do you want to upload your website using SSH? (y/N) n
> Do you want to upload your website using Dropbox? (y/N) n
> Do you want to upload your website using S3? (y/N) n
> Do you want to upload your website using Rackspace Cloud Files? (y/N) n
> Do you want to upload your website using GitHub Pages? (y/N) y
```

## 3. Add content in a markdown file
```
vim content/fish.md
```

## 4. Generate your site
```
pelican content
```

## 5. Preview your site
```
pelican --listen

# Navigate to http://localhost:8000/ in your browser.
```

## 6. Optional:
## 6.1 How to add a theme?
```
# Choose a path for to clone pelican-themes directory (e.g. pelican-website/)
git clone --recursive https://github.com/getpelican/pelican-themes ../pelican-themes

# Add a theme in the pelicanconf.py of your site (e.g. fishingbird/pelicanconf.py)
THEME = '../pelican-themes/bootstrap2'
```

## 6.2  How to add theme as git module
```
# Add a .gitmodules and a directory `themes/` in the project perclican-website
git submodule add git@github.com:getpelican/pelican-themes.git themes

# Commit
git commit -am 'Add theme as a submodule'

# Check whether the themes is listed as a submodule
git submodule status
'565dc8959ad2573c4a9245eaaec73916c782f6d9 theme (heads/master)'

# Check available themes
cd themes
git submodule status

# Initialize the bootstrap2 theme
git submodule init bootstrap2

# Update the submodule
git submodule update
cd ..
```
```
# Add the theme path in the pelicanconf.py of your site (e.g. fishingbird/pelicanconf.py)
THEME = '../themes/bootstrap2'
```

## 7. Publish to Github project page
```
# Add your SITE_URL in pelicanconf.py (e.g. fishingbird/pelicanconf.py)
SITEURL = 'https://dj-application.github.io/pelican-website/'
```
```
cd fishingbird
pelican content -o output -s pelicanconf.py
ghp-import output -n
git push origin gh-pages
```

## 8. What are the files?
  ------------
     ├── License.md
     ├── README.md
     ├── fishingbird
     │   ├── Makefile
     │   ├── content
     │   ├── output
     │   ├── pelicanconf.py
     │   ├── publishconf.py
     │   └── tasks.py
     ├── requirements.txt
     └──  themes


   * Makefile - This file defines make commands that perform the most important tasks like generating your site and starting a local http server.
   * pelicanconf.py - This file contains settings to customize your site.
   * publishconf.py - This file contains settings that are only used when you’re ready to publish to the web.
   *  content/ - This folder is where you’ll put the templates and files that will be translated into the content of your site.
   *  output/ - This folder might not exist until you convert your content into html. By default, the translated website lands here.


## 9. Reference
  * [Tutorials](https://github.com/getpelican/pelican/wiki/Tutorials)
  * [Documentation](https://docs.getpelican.com/en/stable/)
  * [python-livereload](https://github.com/lepture/python-livereload#script-example-sphinx)
  * [Using LiveReload with Pelican](https://merlijn.vandeen.nl/2015/pelican-livereload.html)
  * [Getting Started with Pelican on Github Pages](https://.justalfred.com/getting-started-with-pelican-on-github-pages.html)
  * [ migrated to Pelican and GitHub pages](https://dirtyhandscoding.github.io/posts/-migrated-to-pelican-and-github-pages.html)
