# AGL Handbook

## Editing Content

All of the site content is in the `_sections/` folder. The simplest way is to browse wihtin github to the section file to edit, and edit in your web browser via github. Github also allows for adding new section files. Note that the files are in markdown format with metadata in headers.

### Internal Page Navigation

There is a special section "internal_nav" which controls the red links that navigate to sections. To change the list of sections, simply open `includes/section_nav.html` and change the list starting on line 2. Note that the list is pipe (|) delimited, so the list in quotes should look like `"About Agile|Next Section Title|Third Link"`. Each title should correspond to the exact section title specified in the respective `_sections/` file.

### Markdown

Markdown is a simple text formatting. Editing in github allows you to preview how it will look. More info:
 * [Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
 * [Official Docs](https://help.github.com/categories/writing-on-github/)

_Note on raw HTML:_ You can mix raw HTML within a markdown document, but _cannot_ put markdown within that HTML. In other words...

... this is fine

```
  # My Header
  <ul>
    <li>an item</li>
    <li><em>another</em> item</li>
  </ul>
  [My link](http://google.com)
```

... this is not fine (the asterisks will be displayed on the rendered page)

```
# My Header
<ul>
  <li>an item</li>
  <li>*another* item</li>
</ul>
[My link](http://google.com)
```

### Section Metadata

Each section has a yaml header, such as the below.

```markdown
---
title: GOV.UK on Agile
order: 400
style: black
youtube_video_id: 0XpAtr24uUQ
---
```

The metadata you can provide are:
 * __title (required):__ The section title that will appear as the section header.
 * __order (required):__ Sort order, as compared to other sections, with lower numbers shown first. To insert a section between About Agile (100) and History (200), set the order of the new section to 150.
 * __style (optional):__ Section styling, which defaults to white background. Options: white, black, grey.
 * __youtube_video_id (optional):__ If present, this will embed a video after section content. The id is the alphanumeric code such as "0XpAtr24uUQ". This can be found in the video's URL, e.g. the bit after `v=` in `https://www.youtube.com/watch?v=0XpAtr24uUQ`.

## Contributing

__Note to admins: as soon as you merge/save content into the master branch, it will be published to the live site.__

## Creating a Fork 

To make a small update, it is generally simplest to browse to and edit one of the markdown files within the `/_sections/` directory. GitHub will do some auto-magic to create a "fork" and a "pull request" behind the scenes to represent the simple edit of a single file. However, you may be doing something more complicated, such as making a batch of edits to many files and/or using more complex formatting that you want to preview.

Creating your own fork of the site makes sense for these more complex cases. Simply click the 'Fork' icon near the top-right of this page. In your forked repo (which is located at a url similar to https://github.com/YOURUSERNAME/handbook), go to the settings to use the **master** branch for GitHub Pages. See a [video walkthrough of updating the setting](https://youtu.be/DDhQ57cgC6s) if you haven't done so before. You can now make changes on your own fork and preview the changes to the handbook at a url similar to https://YOURUSERNAME.github.io/handbook.

## Maintaining the Template

To make changes to the overall page template to stay in coordination with the overall AGL site, edit `layouts/agl.html`. This would include major style changes or updated top-level navigation, footer info, etc.

## Running Locally

The site is built using Jekyll, the standard tool for github pages. See [github pages docs](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/) for more info on running locally. This is not necessary for most content work, but is highly recommended for any template changes.
