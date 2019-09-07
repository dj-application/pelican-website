


## Installation
```
# Install pelican
pip install pelican markdown

# Choose a name for your project (e.g. pelican-website) and directory for your site (fishingbird)
mkdir -p pelican-website/fishingbird
cd pelican-website/fishingbird
```

## Quickstart
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
> Do you want to upload your website using GitHub Pages? (y/
```

## Add content in a markdown file
```
vim content/fish.md
Title: My First Review
Date: 2010-12-03 10:20
Category: Review

Following is a review of my favorite mechanical keyboard.
```

## Generate a site
```
pelican content

# preview your site
pelican --listen

# Navigate to http://localhost:8000/ in your browser.
```
## Reference

  * [Documentation](https://docs.getpelican.com/en/stable/)
  * [Tutorials](https://github.com/getpelican/pelican/wiki/Tutorials)
