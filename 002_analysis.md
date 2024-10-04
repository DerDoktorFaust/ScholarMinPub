---
layout: default
title: Analysis
number: 002
---

# Analysis

Now analyze your historical subject. (1000 words). You can include images, videos and PDFs that pertain to your subject using the examples below. To add more, simply copy, paste, and change the title of your item to correspond with your media file.

# Embedding a Single Image

{% assign media = site.media_metadata | where_exp: "item", "item.title == 'Image_№2_from_Introduction'" %}
{% include media.html pages=media %}

# Embedding a Single Video
{% assign media = site.media_metadata | where_exp: "item", "item.title == 'Kill_the_Sexist'" %}
{% include media.html pages=media %}

# Linking to a PDF File

[Download PDF file]({{ site.baseurl }}/media_files/pdfs/newspaper1942.pdf)