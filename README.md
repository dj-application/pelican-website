## What is Pelican?
Pelican is a Python library that lets you generate static websites from templates.

## Installation
```
# Install pelican
pip install pelican markdown

# Choose a name for your project (e.g. pelican-website) and directory for your site (fishingbird)
mkdir -p pelican-website/fishingbird
cd pelican-website/fishingbird
```

## Generate the initial boilerplate
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

## Add content in a markdown file
```
vim content/fish.md
```

## Generate your site
```
pelican content
```

## Preview your site
```
pelican --listen

# Navigate to http://localhost:8000/ in your browser.
```

## How to add a theme?
```
# Choose a path for to clone pelican-themes directory (e.g. pelican-website/)
git clone --recursive https://github.com/getpelican/pelican-themes ../pelican-themes

# Add a theme in the pelicanconf.py of your site (e.g. fishingbird/pelicanconf.py)
THEME = '../pelican-themes/blue-penguin'
```

## Publishing to Github project page
```
pelican content -o output -s pelicanconf.py
ghp-import output -n 
git push origin gh-pages
```

## What are the files?

  * Makefile - This file defines make commands that perform the most important tasks like generating your site and starting a local http server.
  * pelicanconf.py - This file contains settings to customize your site.
  * publishconf.py - This file contains settings that are only used when you’re ready to publish to the web.
  * content/ - This folder is where you’ll put the templates and files that will be translated into the content of your site.
  * output/ - This folder might not exist until you convert your content into html. By default, the translated website lands here.
  * fabfile.py - This has something to do with fabric which I don’t use.


## Reference

  * [Documentation](https://docs.getpelican.com/en/stable/)
  * [Tutorials](https://github.com/getpelican/pelican/wiki/Tutorials)
  * [Getting Started with Pelican on Github Pages](https://blog.justalfred.com/getting-started-with-pelican-on-github-pages.html)
