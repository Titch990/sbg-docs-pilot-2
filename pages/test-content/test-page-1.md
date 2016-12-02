---
product-id: "P1"
product-long-name: "Product A"
product-short-name: "PA"
title: MJ's test topic
layout: default
---
# MJ's test topic 1

## About {{ page.product-long-name }}

This is the documentation for {{ page.product-long-name }} ({{ page.product-short-name }}).

## Section with a snippet

The remaining content in this section is an included snippet.

{% include /MJ-snippets/test-snippet1.md %}

## Section with product-specific content

This section includes some product-specific content for {{ page.product-short-name }}.

For product A, the next paragraph should start "Product A, Product A, product A! This is the stuff that only applies to product A" and for product B the next sentence should read "Product B, Product B, product B! This is the stuff that only applies to product B".

{% if page.product-id == "P1" %}
  Product A, Product A, product A! This is the stuff that only applies to product A.

  We do have more stuff for product A too. We do have more stuff for product A too. We do have more stuff for product A too. We do have more stuff for product A too. We do have more stuff for product A too.
{% elsif page.product-id == "P2" %}
  Product B, Product B, product B! This is the stuff that only applies to product B.

  There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B. There is load and loads and loads and loads more stuff for product B.
{% endif %}

## Section with a note

{% include body-elements/note.html content="This is my note. This is one paragraph.<br/><br/> This is how to add a second paragraph." %}
