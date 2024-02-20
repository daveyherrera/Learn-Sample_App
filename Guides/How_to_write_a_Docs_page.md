# Creating a new docs page

Please follow this guide whenever you want to create a new docs.anthology.com page.

1. Create a Branch of the main one.

First, make sure you have followed our readme on the devdocs repo to create your local version of the site.

Once you have done this, and your site is live locally, you can start creating a new page.

## Where do I locate my new docs file

Depending on what you are trying to create and your target audience is, if, for example, your main audience are learn administrators, you can go to Learn > Admin and create your md file there. If Ally, then, go to the Ally folder within your local repo clone.
If you need further guidance on this, please ask to any of us on developers@anthology.com so we can help you out finding the best place for your file.

## What about a blog

Blogs can be used as well whenever we see it fit, for example, roadmaps are part of our blogs, they do not have a specific structure, they want to provide good information that may or may not happen. In this case it is precise to always talk about the forward looking statement

## Forward looking statement

Please use this text just as it is with a title that says "Forward looking statement" for at least 6 seconds reading it, again, as it is.

"Statements regarding our product development initiatives, including new products and future product upgrades, updates or enhancements, represent our current intentions but may be modified, delayed, or abandoned without prior notice, and there is no assurance that such offering, upgrades, updates, or functionality will become available unless and until they have been made generally available to our customers."

## Where do I place my Images and Videos?

### About images metadata, location and size

- Please make sure to place them on the folder located in ../anthologydevdocs/static/assets/img
- When naming them, please use the following convention: name-of-the-article-number-of-the-image.jpg for example: creating-dummy-data-1.jpg
- Always use an ALT for all images describing what the image contains
- Do not use images that are too height, consider using wide images.
- Do not use images bigger than 4mb. Use an image compressor for that: https://www.resizepixel.com/edit?act=reduce

### About videos metadata, location and size

- All videos should be uploaded to youtube. No exception.
- You can show your face, that is optional
- It is required to use your own voice on the recording explaining. If you see it fit, use an automated voice over synced with the actions.
- Do not use copyright material, images, music or content not owned or produced by Anthology.
- When a video is uploaded it will produce an iframe that can be used to place it on the md file. use the width of 560 and height of 315 or auto.
- If you talk about a feature on any of our products that may or may not be launched, You need to show our "Forward looking statement" on the video for at least 6 seconds while reading it.

It should look like this:

```html
<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/TbMmFuPu9Pg"
  title="The Python and the Postman - DevCon 2020"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; fullscreen; web-share;"
  allowfullscreen></iframe>
```

## When creating a new .md file for docs

### About docs.anthology.com

Our docs.anthology.com site uses docusaurus which uses react as the engine to render the webpages. We use markdown files to write the documentation, so any cheat sheet should always be helpful when writing a new document.

### About the md files

All the md files require to have in the content the following:

- Front matter

```md
---
layout: post
title: 'REST Tutorials'
id: tutorials
categories: Learn REST getting-started
Author: Mark Kauffman
sidebar_position: 9
published: ''
edited: ''
---
```

- The layout refers to the template used for the content, it always uses post, unless you write a blog, in that case, layout must be removed.
- title is the document title, it is the h1 of the document. There must be only one h1 per file, and that is this one
- id is the url of the file, do not use spaces, use dashes to separate words, but **keep it simple**
- categories are not currently being used, however, it always shows the path in separate words where the file is located.
- Author is your name, as the author. Also, whenever you are creating a new file for the first time, we will create your handle in our yaml to add you. Also, this can have several names separated by comma.
- sidebar_position is the position in the menu vertically where the content will be organized.
- published and edited use the format YYYY-MM-DD

Right after the front matter, you need to place this line to display the published and edited date just as it is:

```javascript
<VersioningTracker frontMatter={frontMatter} />
```

At the very end of your document, you need to add this line to display the information of the author or authors:

```javascript
<AuthorBox frontMatter={frontMatter} />
```

### About the voice used when writing a document

We don't use a formal voice when writing, we do want our documents to be professional but a bit playful, a small joke or little pun won't hurt nobody, however, those should be pretty casual and fall into the "dad joke" category and not for so long.

No h1s are allowed, only title within the front matter, and as mentioned before the structure should be the same always.

To start, you need to describe your problem, indicate the version of the product this problem is happening if applies, then, talk a bit on how you managed to get to the solution and then, describe your solution. Keep it simple, but be eloquent.

### About adding code

#### Code blocks with backticks

It is possible to use code blocks, all you have to do is use three backticks with no spaces between them and close the code using the same:

````html
```html
<html>
  Remember the backticks do not need spaces between them to work
</html>
```
````

#### Code Highlight

It is also possible to highlight the code based on the language you are using, just write the name in lowercase after the three opening backticks and it will highlight it automatically. You can follow this guide: https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks

# To publish your page

To publish your doc page within docs.anthology.com, please submit a new issue in the Contributions repository ([Here](https://github.com/anthology-inc/community-contribution/issues/new/choose)) using the template to **Publish a Docs page** including the necessary information requested in the template.
