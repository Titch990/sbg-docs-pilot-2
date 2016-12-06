---
layout: post
title: "Test Post"
date: 2016-11-09
summary: "This is a test blog post to demonstrate how blog posts are handled by Jekyll and to demonstrate some fundamental Jekyll concepts"
product-name: "Product A"
---

# Level 1 heading

Here's a test blog post. this blog is powered by [Jekyll](http://jekyllrb.com). The post body is written in Markdown.

# What this blog post is about

As I'm learning about Markdown, Jekyll and Liquid (and more) as I write this content, i thought I'd tell you about some of the things you can do with this technology.

## Some markdown stuff

Here are some content elements written in Markdown. Note that Markdown is quite particular about spacing. You need to have a space between the last # in a heading and the first character of the text. You also need to leave blank lines between most things, or Markdown may ignore some of the things!

### Code blocks

This is a code block (note that these are back quotes)

```
a = b;
c = c;
```

To do - work out how to get the newline at the end of each block. It may be `<br/><br/>`?

### Code characters

This sentence has code characters in it ```here```. But then we continue in ordinary text.

### Simple tables

Here's a simple table:

|head1|head2|head3|
|-------|-----|------|
|row 1 cell 1|row 1 cell 2|row 1 cell 3|
|row 2 cell 1 and long, long, long, long text in this cell because I can. What about a second row in the cell?|row 2 cell 2|row 2 cell 3|
|row 3 cell 1|row 3 cell 2|row 3 cell 3|
|row 4 cell 1|row 4 cell 2|row 4 cell 3|
|row 5 cell 1|row 5 cell 2|row 5 cell 3 with some very long text|

Complex tables may need to be coded in HTML or using a JS library.

## The front matter

Jekyll allows you to add YAML front matter to Markdown files. The items defined there can be used as variables in the body of the post (or elsewhere). When the site is built, the values defined in the front matter will be substituted for the placeholder variables. In real life, many of the variables will be defined in external configuration files rather than locally, but here they are used to demonstrate a point.

## Here's a simple variable

To use a variable declared in the front matter of the page, embed it on the page using this syntax `{%raw%}{{ page.<variable> }}{% endraw%}`. In the next paragraph, the value defined in the front matter for the `product-name` variable will be substituted between the quotes.

This is the documentation for "{{ page.product-name }}".

Use ```page.<variable>``` for variables set on the same page. Use ```site.<variable>``` for variables set at the site level. This is just scratching the surface of what you can do with variables.

## A simple snippet using an include

There are (at least) two ways to define boilerplate text that can be inserted in other content. One way is to define an include file in the `/_includes` folder (or in a subfolder) then include the content like this: `{%raw%}{% include test-snippet1.md %}{% endraw%}`. If the snippet is in a subfolder you need to include the subfolder too. For example, if the snippet is in `/_includes/page-snippets`, you will need to specify `{%raw%}{% include /page-snippets/test-snippet1.md %}{% endraw%}`.

The next section (including a level 3 heading) is an included snippet.

{% include /MJ-snippets/test-snippet1.md %}

## A simple snippet using data

The second way to define a snippet is using YAML data in the `/_data` folder (or in a subfolder, as before). Here, you reference the data using

`{%raw%}{{ site.data.<file-name>.<data-item-name> }}{% endraw%}`

For example, if you had the following YAML in `/_data/test.yml`

```
test-snippet-using-yaml:
  This is a test snippet defined in a YAML data file.
```

and you wrote `{%raw%}{{ site.data.test.test-snippet-using-yaml }}{% endraw%}` you would get this:

This is a test snippet defined in a YAML data file.

So let's do that now and see the paragraph above repeated below.

{{ site.data.test.test-snippet-using-yaml }}

## Multi-level YAML data snippet

The YAML data can be multi-level. For example, you could define the following YAML data

```
another-test-snippet:
  second-level-snippet-data:
    This is a second level test snippet.
  more-second-level-data:
    Here is more second level data. This data item has several lines.
    This sentence starts on a new line.
    This is the final line in the second level YAML test snippet data for now.
```

TO DO - the above needs to be split into separate lines.

then reference the second level data in your markdown as `{%raw%}{{ site.data.test.another-test-snippet.second-level-snippet-data }}{% endraw%}` you would get this:

This is a second level test snippet.

## Multiple lines in YAML data files

This I haven't worked out yet, again, it may need `<br/><br/>` or there may be a better way. TO DO.

## Passing variables to snippets

To make snippets even more flexible, you can include variables in snippets and specify the value to use for the variable when you place the snippet on a page. This value could be a hard-coded value, or could itself be a variable defined in the front matter of the page. I've not yet worked out how to do this successfully for YAML data snippets (you need do a bit of fancy footwork using a few escape characters to ensure the variable is substituted after the snippet has been placed on the page) but I know it can be done. It's simple for snippets defined as includes.

TO DO

## and a simple condition

TO DO
