# User documentation #

Tranquilpeak theme is comptabile with Hexo v3.0.0 or higher

This documentation will help you to install tranquilpeak-hexo-theme and configure it to use all features which it provides.  

If you want to report a bug or ask a question, [create an issue](https://github.com/LouisBarranqueiro/tranquilpeak-hexo-theme/issues/new).

## Summary ##

- [Requirements](#requirements)
- [Installation](#installation)
- [Hexo configuration](#hexo-configuration)
    * [Enable post assets folder](#enable-post-assets-folder)
    * [Archives configuration](#archives-configuration)
    * [Enable RSS feed](#enable-rss-feed)
- [Tranquilpeak configuration](#tranquilpeak-configuration)
    * [Sidebar](#sidebar)
    * [Author](#author)
    * [Customization](#customization)
    * [Miscellaneous](#miscellaneous)
    * [Enable pages](#enable-pages)
        * [Enable all-categories page](#enable-all-categories-page)
        * [Enable all-tags page](#enable-all-tags-page)
        * [Enable all-archives page](#enable-all-archives-page)
- [Front-matter settings](#front-matter-settings)
- [Running](#running)  

## Requirements ##

1. **Node** : v0.10.35 or higher. Download [Node](https://nodejs.org/download/)
2. **Hexo CLI** : v0.1.4 or higher. Run `npm install hexo-cli -g`

## Installation ##

1. Download the latest version built and ready for production here : [tranquilpeak-hexo-theme-built-for-production-1.0.5]
(https://github.com/LouisBarranqueiro/tranquilpeak-hexo-theme/releases/download/v1.0.5/tranquilpeak-hexo-theme-built-for-production-1.0.5.zip) or choose an other version here : [all releases](https://github.com/LouisBarranqueiro/tranquilpeak-hexo-theme/releases)
2. Rename the folder in `tranquilpeak` and place it in `themes` folder of your Hexo blog

## Hexo configuration ##

Modify the theme in `_config.yml` by changing `theme` variable  to `tranquilpeak`
  
If it's your first time using Hexo, please check [Hexo official documentation](https://hexo.io/docs/)

### Enable post assets folder ###

If you want to take advantage of cover image, thumbnail image, and image gallery features, you hate to enable post assets folderby setting `post_asset_folder` to  `true`in `_config.yml`.

### Archives configuration ###

You can choose the style of listing for archives, category and tag pages by adding this lines in `_config.yml`  

``` yaml
# Archives
## 1: Enable pagination
## 0: Disable pagination
archive: 1
category: 1
tag: 1
```

- **0** : Disable pagination  
- **1** : Enable pagination  

Example :  
A category page look like this with `category: 1` :  
![archives 1](http://louisbarranqueiro.github.io/tranquilpeak-hexo-theme/2015/05/02/Check-official-user-documentation/archives-1.png)  

The same page with `category: 0`:  
![archives 0](http://louisbarranqueiro.github.io/tranquilpeak-hexo-theme/2015/05/02/Check-official-user-documentation/archives-0.png)  

### Enable RSS feed ###

1. Execute `npm install hexo-generator-feed --save` in your Hexo blog folder  
2. Add this lines in `_config.yml` :  

``` yaml
feed:
    type: atom
    path: atom.xml
    limit: 20
```
- **type** : Feed type
- **path** : Feed path (Default: atom.xml/rss2.xml)
- **limit** : Maximum number of posts in the feed (Use `0` or `false` to show all posts)

If you want more informations on this plugin : [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed)

## Tranquilpeak configuration ##

Complete `theme/tranquilpeak/_config.yml` with your informations.

### Sidebar ###

The sidebar is powerful and easily configurable.
DON'T modify variables name `sidebar`, `title`, `url` and `icon`.  
Others variables name which refer to the name of a menu or a link can be edited. Example : `menu`, `home`, `categories`, etc...  
You can add groups of links and links much as you want  
You just have to respect the indentation : `groups of links` -> `link` -> `title`, `link`, `icon` 

``` yaml
sidebar:
    menu:
        home:
            title: Home
            url: /
            icon: home
        categories:
            title: Categories
            url: /all-categories
            icon: bookmark
        tags:
            title: Tags
            url: /all-tags
            icon: tags
        archives:
            title: Archives
            url: /all-archives
            icon: archive
        about:
            title: About me
            url: /#about
            icon: question
    author_links:
        # github:
        #     title: GitHub
        #     url: https://github.com/
        #     icon: github
        # stack_overflow:
        #     title: Stack Overflow
        #     url: http://stackoverflow.com/users/
        #     icon: stack-overflow
        # twitter:
        #     title: Twitter
        #     url: https://twitter.com/
        #     icon: twitter
        # facebook:
        #     title: Facebook
        #     url: https://www.facebook.com/
        #     icon: facebook
        # google_plus:
        #     title: Google +
        #     url: https://plus.google.com/
        #     icon: google-plus
        # linked_in:
        #     title: Linked In
        #     url: https://www.linkedin.com/profile/
        #     icon: linkedin
        # mail:
        #     title: Mail
        #     url: mailto://
        #     icon: envelope-o
    rss:
        rss:
            title: RSS
            url: /atom.xml
            icon: rss
```

- **title** : Title of your link displayed
- **url** : URL of the link. If the URL is internal, domain name is not necessary
- **icon** : Name of the font awesome icon class without the `fa-` (Go to [font-awesome icons](http://fontawesome.io/icons/) to find class name of icon)

### Author ###

``` yaml
# Author
author:
    email:
    bio:
    job:
    location:
    picture:
```

- **email** : Your mail address. This address will be used to get your gravatar image if you activate gravatar option
- **bio** : A short biography. Display on your about card
- **job** : Your job
- **location** : Your location
- **picture** : Your profile picture. Overwritten by your gravatar image if gravatar option is enabled

### Customization ###

**Change the default cover image to have an unique blog :)**  
  
``` yaml
# Customization
gravatar_image: 1                
thumbnail_image: 1               
read_more_message: Continue readiing
go_to_message: Go to the website 
cover: cover.png                 
favicon:                         
image_gallery: 1                 
```

- **gravatar_image** : Enable gravatar image. Using `author.email` value. (disable: 0, enable: 1). Overwrite `author.picture` everywhere in the blog
- **thumbnail_image** : Display thumbnail image of each post on index pages (disable: 0, enable: 1)
- **read_more_message** : Message displayed after the `<!-- more -->` tag or after 300 characters in post
- **go_to_message** : Message displayed after the `<!-- more -->` balise or after 300 characters for post with link layout
- **cover** : Your blog cover picture located in folder `source/assets/images/`. Change the default cover image to have an unique blog
- **favicon** : Your favicon located in folder `source/assets/images/`
- **image_gallery** : Display an image gallery at the end of a post which have `photos` variables

### Miscellaneous ###

``` yaml
# Miscellaneous
google_analytics:
```

- **google_analytics** : Your Google analystics web property ID : UA-XXXXX-X

### Enable pages ###

Tranquilpeak provides you 3 pages to display all posts title and date by tags, by categories, by date and an about page. To enable one of this pages, 
read following step.

#### Enable all-categories page ####

To enable `all-categories` page :  
1. Run `hexo new page "all-categories"`. A new folder named `all-categories` will be created in `source/`  
2. Replace `source/all-categories/index.md` content with :
 
``` markdown
title: "all-categories"
layout: "all-categories"
---
```

New page will be reach at : `/all-categories`. On this page, users will be able to search and filter categories.

#### Enable all-tags page ####

To enable `all-tags` page :  
1. Run `hexo new page "all-tags"`. A new folder named `all-tags` will be created in `source/`  
2. Replace `source/all-tags/index.md` content with :
 
``` markdown
title: "all-tags"
layout: "all-tags"
---
```

New page will be reach at : `/all-tags`. On this page, users will be able to search and filter tags.

#### Enable all-archives page ####

To enable `all-archives` page :  
1. Run `hexo new page "all-archives"`. A new folder named `all-archives` will be created in `source/`  
2. Replace `source/all-archives/index.md` content with :
 
``` markdown
title: "all-archives"
layout: "all-archives"
---
```  

New page will be reach at : `/all-archives`.  
On this page, users will be able to search and filter posts.  
**Search pattern** : YYYY/MMM/DD

## Writing posts ##

### Front-matter settings ###

Tranquilpeak introduces 2 new variables to configure precisly the style of your post : `thumbnailImage` and `coverImage`.  
  
Example :  
``` markdown
thumbnailImage: image-1.png
coverImage: image-2.png
photos:
    - image-3.jpg
    - image-4.png
comments: false
```

- **thumbnailImage** : Image displayed in index view.
- **coverImage** : Image displayed in large at the top of your post in post view. If thumbnail image is not configured, cover image is also used as thumbnail image.
- **photos** : Images displayed in an image gallery at the end of the post. If thumbnail image is not configured and cover image too, the first photo is used as thumbnail image.
- **comments** : Disable the comment of the post.

The relative path of images entered is : `source/_posts/{YOUR_POST_TITLE}/`, you just have to enter the name of the image without domain name and path like written just above.  
Of course, you can set external url.

## Running ##

Run `hexo server` and start writing! :)
