---
title: Alerts
layout: default
---
# MJ's attempt at alerts

This is the raw Markdown that was used to generate Tom J's [alerts page](http://idratherbewriting.com/documentation-theme-jekyll/mydoc_alerts.html).

## About alerts
Alerts are little warnings, info, or other messages that you have called out in special formatting. In order to use these alerts or callouts, reference the appropriate value stored in the alerts.yml file as described in the following sections.

## Alerts

Similar to inserting images, you insert alerts through various includes that have been developed. These includes provide templates through which you pass parameters to easily populate the right HTML code.

```
{%raw%}{% include body-elements/note.html content="This is my note. All the content I type here is treated as a single paragraph." %}{% endraw%}
```

Here's the result:

{% include body-elements/note.html content="This is my note. All the content I type here is treated as a single paragraph." %}
With alerts, there's just one include property:

| Property | description |
|-------|--------|
| content | The content for the alert. |

If you need multiple paragraphs, enter `<br/><br/>` tags. This is because block level tags aren't allowed here, as Kramdown is processing the content as Markdown despite the fact that the content is surrounded by HTML tags. Here's an example with a break:

```
{%raw%}{% include body-elements/note.html content="This is my note. All the content I type here is treated as a single paragraph. <br/><br/> Now I'm typing on a  new line." %}{% endraw%}
```

Here's the result:

{% include body-elements/note.html content="This is my note. All the content I type here is treated as a single paragraph. <br/><br/> Now I'm typing on a  new line." %}
## Types of alerts available

There are four types of alerts you can leverage:

* note.html
* tip.html
* warning.html
* important.html

They function the same except they have a different color, icon, and alert word. You include the different types by selecting the include template you want. Here are samples of each alert:

{% include body-elements/note.html content="This is my last note." %}

<!--- Delete the rest out for now. I tried commenting it out, but even when commented out, the bracket-precent-include directives still looked for the elements to include. I'll put them back later via git diff.
-->
